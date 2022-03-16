# Bash Profile

- [Aufbau](#aufbau)
- [Bash completions](#bash-completions)
- [AWS](#aws)
- [Bash styling](#bash-styling)
- [NPM Aliases](#npm-aliases)
- [NVM](#nvm)
- [Linux Utils](#linux-utils)
- [MacOS Utilities](#macos-utilities)
- [CircleCI](#circleci)
- [Github](#github)
- [Git](#git)
- [Lerna](#lerna)
- [Make](#make)

## Aufbau

Ich habe mir ein "modulares" `.bash_profile`-File erstellt, dass ich beliebig erweitern kann. Im grunde genommen, gibt es einen Eintrag in meinem `.bash_profile`, der Zeug aus dem `~/.bash`-Ordner lädt. Der sieht folgendermaßen aus:

```sh
source ~/.bash/_index.sh
```

Dort wird eben, die `~/.bash/_index.sh` geladen. So kann ich immer den `.bash` Ordner sichern, und dort ist alles drin :). Gleiches Prinzip gibt's dann dort auch.

```sh
set -o allexport
[[ -f ~/.bash/.env ]] && source ~/.bash/.env
[[ -f ~/.bash/.env ]] && source ~/.bash/load-temp-env.sh
set +o allexport

# source ~/.bash/.....
# source ~/.bash/.....
# source ~/.bash/.....
# source ~/.bash/.....

reload-profile() {
  source ~/.bash/_index.sh
}

load-env() {
  if [ -z "$1" ]; then
    echo "ERROR! You must provide a file!"
  fi

  FILENAME=$(realpath $1)
  echo "Adding $FILENAME to temporary environment until unloaded with 'unload-env [filename]'"
  echo "source $FILENAME" >> ~/.bash/.tempenv
  source ~/.bash/_index.sh
}

unload-env() {
  if [ -z "$1" ]; then
    echo "ERROR! You must provide a file!"
  fi

  FILENAME=$(realpath $1)
   echo "Removing $FILENAME from temporary environment"
   node -e "require('fs').writeFileSync('$HOME/.bash/.tempenv', require('fs').readFileSync('$HOME/.bash/.tempenv').toString().replace(new RegExp('\n?source $FILENAME'.replace('/', '\\/')), ''));"
  awk '!/source ${FILENAME}/' ~/.bash/.tempenv > temp && mv temp ~/.bash/.tempenv
  source ~/.bash/_index.sh
}
```

`load-env` und `unload-env` sind zum laden von dotenv files. Das `.bash`-System ist in der Lage temporär `.env` files zu laden und solange zu behalten, bis sie unloaded werden.

## Bash completions

Bash completions, die ich i.d.R. nutze:

- [aws-logs](https://gist.github.com/rce/746ded6cdd0308ff8f5f5512b7b0be4b)
- nvm
- git - [Siehe hinterlegte Datei](./.git-completion.bash)
- make (siehe [Make](#make))
- awsume
  ```sh
  _awsume() {
    local cur prev opts
    COMPREPLY=()
    cur="${COMP_WORDS[COMP_CWORD]}"
    prev="${COMP_WORDS[COMP_CWORD-1]}"
    opts=$(awsume-autocomplete)
    COMPREPLY=( $(compgen -W "${opts}" -- ${cur}) )
    return 0
  }
  complete -F _awsume awsume
  ```
  
## AWS

```
# Echo'ed das aktuell verwendete AWS-Profil
get-aws-login() {
  if [ -z "$AWSUME_PROFILE" ]; then
    echo "No AWS login"
  else
    echo $AWSUME_PROFILE
  fi
}
```

## Bash styling

Ich habe mir meine prompt etwas umgestyled. So wird folgendes angezeigt:

Erste Zeile
- Uhrzeit
- Username@Rechnername:Verzeichnis

Zweite Zeile
- Aktueller Git-Branch (erfordert git_branch)
- Aktueller AWS Account, wenn eingeloggt. (erfordert get-aws-login)

```sh
## Shell prompt formatting:
export PS1='\[\033[0;32m\][\t] \[\033[0m\033[0;32m\]\e[0;36m\e[0;33m\u\[\033[0;36m\]\[\033[0m\]@\[\033[0;36m\]\h\[\033[0m\]:\w\[\033[0;32m\] #\n\[\033[0;32m\]└─\[\033[0m\033[0;32m\] \$\[\033[0m\033[0;32m\] $(git_branch || echo "(no branch info)") / $(get-aws-login) ▶\[\033[0m\] '
```

## NPM Aliases

```sh
# Zeigt die aktuelle NPM-Paket Version des CWD an.
# Erfordert NPM und JQ
alias package-version='npm info $(cat package.json | jq -r ".name") && echo "Local version "+$(cat package.json | jq -r ".version") '
```

## NVM
```sh
# NVM Autoswitcher
find-up () {
    path=$(pwd)
    while [[ "$path" != "" && ! -e "$path/$1" ]]; do
        path=${path%/*}
    done
    echo "$path"
}

cdnvm(){
    cd "$@";
    nvm_path=$(find-up .nvmrc | tr -d '[:space:]')

    # If there are no .nvmrc file, use the default nvm version
    if [[ ! $nvm_path = *[^[:space:]]* ]]; then

        declare default_version;
        default_version=$(nvm version default);

        # If there is no default version, set it to `node`
        # This will use the latest version on your machine
        if [[ $default_version == "N/A" ]]; then
            nvm alias default node;
            default_version=$(nvm version default);
        fi

        # If the current version is not the default version, set it to use the default version
        if [[ $(nvm current) != "$default_version" ]]; then
            echo "No .nvmrc found, changing node version to default";
            nvm use default;
        fi

        elif [[ -s $nvm_path/.nvmrc && -r $nvm_path/.nvmrc ]]; then
        declare nvm_version
        nvm_version=$(<"$nvm_path"/.nvmrc)

        # Add the `v` suffix if it does not exists in the .nvmrc file
        if [[ $nvm_version != v* ]]; then
            nvm_version="v""$nvm_version"
        fi

        # If it is not already installed, install it
        if [[ $(nvm ls "$nvm_version" | tr -d '[:space:]') == "N/A" ]]; then
            echo "Installing node version $nvm_version";
            nvm install "$nvm_version";
        fi

        if [[ $(nvm current) != "$nvm_version" ]]; then
            echo "Found .nvmrc, Changing node version to $nvm_version";
            nvm use "$nvm_version";
        fi
    fi
}
alias cd='cdnvm'
```

## Linux Utils

```sh
# Holt sich die mit dem Internet verbundenen Netzwerkadapter
get-inet() {
  route | grep '^default' | grep -o '[^ ]*$' | head -1
}

# Netmask des mit dem Internet verbundenen Adapters ausgeben lassen
get-netmask() {
  ip -o -f inet addr show | grep $(get-inet) | awk '/scope global/ {print $4}'
}

# Liste der im mit dem Internet verbundenen Netzwerk befindlichen Rechner auflisten
list-hosts() {
  nmap -sn $(get-netmask)
}
```

## MacOS Utilities

```sh
# Überschreibt "ls":
# - Färbt Dateien und Verzeichnisse ein
# - Listet Verzeichnisse als Erstes auf.
# - Aktiviert menschenlesbare Dateigrößen
alias ls='ls --color -h --group-directories-first'

# Zeigt die aktuelle Temperatur von CPU und GPU an.
alias show-temperature='sudo powermetrics --samplers smc |grep -i "PU die temperature"'

# Zeigt den aktuellen Takt von CPU und GPU an.
alias show-frequency='sudo powermetrics |grep -i "frequency as fraction"'

# Synonym zu "ipconfig /flushdns" für Windows.
alias flushdns="sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder"
```

## CircleCI

Die CircleCI CLI ist etwas nervig gestaltet. Jedes mal, wenn etwas ausgeführt wird, will sie updaten. Um dem zu entgehen, habe ich folgenden alias gebastelt:

```sh
alias cci="circleci --skip-update-check"
```


## Github

```sh
# Erstellt einen Pull Request für das Repo im CWD
# Usage: gh-pr <autor> <targetBranch>
gh-pr() {
  URL=$(gh pr create -f -r $1 -B $2)
  echo $URL | pbcopy
  echo $URL
  echo "Copied PR URL to Clipboard!"
}
```

## Git

Zusätzlich zur [bash completion](./.git-completion.bash) nutze ich noch folgenden alias:

```sh
# Setzt den angegebenen Dateinamen/pfad/muster in die gitignore ein.
# Usage: giti <filename>
giti() {
  echo $1 >> .gitignore
}
```

## Lerna

```sh
# Führt `lerna add` für das aktuelle Projekt aus
alias lerna-add='lerna add --scope $(jq ".name" -r < package.json)'

# Führt `lerna exec` für das aktuelle Projekt aus
alias lerna-exec='lerna exec --scope $(jq ".name" -r < package.json)'

# Führt `lerna remove` für das aktuelle Projekt aus
alias lerna-remove='lerna exec --scope $(jq ".name" -r < package.json) -- yarn remove '
```

## Make

```sh
complete -W "\`grep -oE '^[a-zA-Z0-9_.-]+:([^=]|$)' ?akefile | sed 's/[^a-zA-Z0-9_.-]*$//'\`" make
```

