# Visual Studio Code

## Extension "Bucket List"
- https://github.com/mtbaqer/vscode-better-folding

## ToC

- [Allgemein](#allgemein)
  - [:rotating_light: Error Lens](#rotating_light-error-lens)
  - [:lipstick: Live Server](#lipstick-live-server)
  - [:chart_with_upwards_trend: :rotating_light: Output Colorizer](#chart_with_upwards_trend-rotating_light-output-colorizer)
  - [:lipstick: Open in New Window](#lipstick-open-in-new-window)
  - [:busts_in_silhouette: Live Share](#busts_in_silhouette-live-share)
  - [:chart_with_upwards_trend: Resource Monitor](#chart_with_upwards_trend-resource-monitor)
  - [:monocle_face: wav-preview](#monocle_face-wav-preview)
- [Programmier-/Markup-/Scriptsprachen](#programmier-markup-scriptsprachen)
  - [CSharp](#csharp)
    - [:thought_balloon: C](#thought_balloon-c)
  - [:thought_balloon: Terraform](#thought_balloon-terraform)
  - [TypeScript](#typescript)
    - [:rotating_light: TSLint](#rotating_light-tslint)
    - [:rotating_light: Interface generator](#rotating_light-interface-generator)
  - [XML/YAML/JSON](#xmlyamljson)
    - [:thought_balloon: XML](#thought_balloon-xml)
    - [:thought_balloon: YAML](#thought_balloon-yaml)
  - [Markdown](#markdown)
    - [:lipstick: Markdown Emoji](#lipstick-markdown-emoji)
    - [:lipstick: Markdown Checkboxes](#lipstick-markdown-checkboxes)
    - [:thought_balloon: Markdown All in One](#thought_balloon-markdown-all-in-one)
  - [Java](#java)
    - [:card_index_dividers: :building_construction: Project Manager for Java](#card_index_dividers-building_construction-project-manager-for-java)
    - [:building_construction: Maven for Java](#building_construction-maven-for-java)
    - [:thought_balloon: Language Support for Java(TM) by Red Hat](#thought_balloon-language-support-for-javatm-by-red-hat)
    - [:building_construction: Gradle for Java](#building_construction-gradle-for-java)
    - [:thought_balloon: Debugger for Java](#thought_balloon-debugger-for-java)
  - [EJS - :thought_balloon: EJS Language Support](#ejs---thought_balloon-ejs-language-support)
  - [Configs](#configs)
    - [:thought_balloon: DotENV](#thought_balloon-dotenv)
  - [CSS / SCSS / LESS](#css--scss--less)
    - [:thought_balloon: SCSS Everywhere](#thought_balloon-scss-everywhere)
    - [:lipstick: Color Info](#lipstick-color-info)
    - [:thought_balloon: hex-rgba-converter](#thought_balloon-hex-rgba-converter)
    - [:art: BEM Helper](#art-bem-helper)
- [Source Controls](#source-controls)
  - [:card_index_dividers: GitLens — Git supercharged](#card_index_dividers-gitlens--git-supercharged)
  - [:card_index_dividers: Git: Git Graph](#card_index_dividers-git-git-graph)
  - [:card_index_dividers: Git: Conventional Commits :tickets:](#card_index_dividers-git-conventional-commits-tickets)
- [Deployments/Builds/Pipelines/CI](#deploymentsbuildspipelinesci)
  - [:electric_plug: Remote - SSH](#electric_plug-remote---ssh)
  - [:recycle:	CircleCI](#recyclecircleci)
- [VSCode Modding](#vscode-modding)
  - [:lipstick: Studio Icons](#lipstick-studio-icons)
  - [:lipstick: Peacock](#lipstick-peacock)
  - [:lipstick: Customize UI](#lipstick-customize-ui)
- [Projekt und Arbeitsorganisation](#projekt-und-arbeitsorganisation)
  - [:card_index_dividers: Project Manager](#card_index_dividers-project-manager)
  - [:card_index_dividers: Monorepo Workspace](#card_index_dividers-monorepo-workspace)
  - [Github](#github)
    - [:inbox_tray: Github Pull Requests and issues](#inbox_tray-github-pull-requests-and-issues)
  - [Jira](#jira)
    - [:tickets: Jira and Bitbucket (Atlassian Labs)](#tickets-jira-and-bitbucket-atlassian-labs)
    - [:tickets: Flow / Jira Commit prefix](#tickets-flow--jira-commit-prefix)
  - [:card_index_dividers: Todo Tree](#card_index_dividers-todo-tree)
  - [:bookmark: Bookmarks](#bookmark-bookmarks)
- [ThirdParty Verbindungen](#thirdparty-verbindungen)
  - [:electric_plug: Docker](#electric_plug-docker)
  - [:electric_plug: SQL Manager](#electric_plug-sql-manager)


**Legende**

Extensions, die euch helfen bei/mit:
- :art: Code-Struktur
- :building_construction: Build Tools
- :thought_balloon: Programmier-/Markup-/Scriptsprachen
- :lipstick: Nice-To-Haves
- :recycle:	Continous Integrations und Automatisierung
- :card_index_dividers: Projekt- und Arbeitsorganisation
- :rotating_light: Fehlersuche und Coding allgmein
- :tickets: Arbeit mit Ticketsystemen
- :card_index_dividers: Lesezeichen und Jump-Marks in Projekten
- :busts_in_silhouette: Teamarbeit
- :electric_plug: Remote-Systeme verwalten
- :chart_with_upwards_trend: Analytics
- :monocle_face: Preview-Support für Dateien

## Allgemein

### :rotating_light: Error Lens

Zeigt die Errors gleich neben der fehlerhaften Zeile im Code an. Sehr, sehr geiles Ding! :)

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens

### :lipstick: Live Server

Mal schnell einen statischen File-Tree als WebServer hosten? Klar, hier geht's lang:

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer

### :chart_with_upwards_trend: :rotating_light: Output Colorizer

Färbt Logfiles ein, um eine bessere Übersicht zu bekommen.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer

### :lipstick: Open in New Window
Nützliche Extension um aus dem Explorer bestimmte Dateien in einem neuen Fenster zu öffnen, fügt ein neues Kontextmenü-Element hinzu.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=onatm.open-in-new-window

### :busts_in_silhouette: Live Share

Ideal um gemeinsam zu programmieren. Geteilte Terminals, Browser, Server-Instanzen usw. Ist bei der Bearbeitung des Projekts ähnlich zu Google Docs Bearbeitung - Man sieht mehrere Cursor, für jeden Bearbeiter und alle können gleichzeitig verschiedene Stellen im Code bearbeiten.

Ideal auch als Mob/Pair-Programming Session-Tool!

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare
### :chart_with_upwards_trend: Resource Monitor

Zeigt euch die aktuellen Stats eures Rechners in der Status-Leiste unten an. CPU und RAM immer im Blick!

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=mutantdino.resourcemonitor

### :monocle_face: wav-preview

Ermöglicht es euch, WAV-Files innerhalb von VSCode anzusehen und zu analysieren.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=sukumo28.wav-preview
## Programmier-/Markup-/Scriptsprachen

### CSharp

#### :thought_balloon: C#

Must-Have für alle C# Entwickler. Ob .NET Core, .NET Standard - völlig egal.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp

### :thought_balloon: Terraform

Aktiviert Support für Terrform-Projekte in Visual Studio Code

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform

### TypeScript

#### :rotating_light: TSLint

Extension für Projekte, die noch TSLint nutzen. Zeigt euch alle Lint-Warnings inline an.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-tslint-plugin
#### :rotating_light: Interface generator

Generiert Interfaces aus Klassen. Simple as that.
  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=dotup.dotup-vscode-interface-generator


### XML/YAML/JSON

#### :thought_balloon: XML

Fügt Sprach-Support für XML hinzu.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=redhat.vscode-xml

#### :thought_balloon: YAML

Fügt Sprach-Support für YAML hinzu.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml
### Markdown

#### :lipstick: Markdown Emoji

Fügt den Support für Emoji-Snippets wie `:arrow_lower_right:` oder `:thought_balloon:` in der Preview hinzu.

:info: Ggf. funktioniert es nach einem Neustart - Die Erstinstallation hat bei mir nicht gegriffen.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=bierner.markdown-emoji

#### :lipstick: Markdown Checkboxes
Macht, was der Title sagt: Wandelt die `- [ ] Todo1` Snippets in Checkboxen um

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=bierner.markdown-checkbox

#### :thought_balloon: Markdown All in One

Sehr hilfreiches Extension Pack für Markdown. Hilft und  vereinfacht die Bearbeitung von *.md files ungemein. Liste, Formatierung, etc - Alles kein Problem mehr. Sogar eine automatisch synchronisierte Table of Contents gibt's out of the box!

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one
### Java

#### :card_index_dividers: :building_construction: Project Manager for Java

Projektmanagement für Java Developers :)

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-dependency

#### :building_construction: Maven for Java

Maven Toolset für Visual Studio

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven
#### :thought_balloon: Language Support for Java(TM) by Red Hat

Must-Have: Fügt Linting, Intellisense und Co. für Java zu VSCode hinzu :)

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=redhat.java

#### :building_construction: Gradle for Java

Gradle Toolset für Visual Studio

- :arrow_lower_right: **Download** https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-gradle

#### :thought_balloon: Debugger for Java

Ein Debugger-Adapter für Java-Projekte. Macht es möglich, Java zu debuggen.

  - :arrow_lower_right: **Download** https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-debug

### EJS - :thought_balloon: EJS Language Support

Syntax Highlighting und IntelliSense für EJS Files :).

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=DigitalBrainstem.javascript-ejs-support

### Configs

#### :thought_balloon: DotENV
Syntax Highlighting für dotenv files.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv

### CSS / SCSS / LESS

#### :thought_balloon: SCSS Everywhere

Aktiviert Code Completion für SCSS Klassen in einigen Dateiformaten, wie z.B. HTML.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=gencer.html-slim-scss-css-class-completion
#### :lipstick: Color Info

"RGB to Hex" oder umgekehrt ist einer deiner beliebtesten Google-Suchbegriffe, wenn du UIs baust? Dann ist die hier etwas für dich. Die Extension zeigt dir einen Inline-Colorpicker an, wo dann auch alle möglichen Farbformate aufgelistet sind.

#### :thought_balloon: hex-rgba-converter

Wie `Color Info`, übernimmt aber nur das Konvertieren von RGB zu Hex und umgekehrt. Kann als Keyboard-Shortcut konfiguriert, oder über die Command Bar getriggert werden.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=medzhidov.hex-rgba-converter
- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=bierner.color-info

#### :art: BEM Helper

Unterstützt euch dabei, HTML-Basierte Dateien im BEM format zu strukturieren. Was ist BEM? Eine Convention, CSS-Klassen strukturiert zu benennen. Macht es vor allem einfacher, SCSS-Files zu strukturieren!

- :man_student: **Mehr zu BEM:** http://getbem.com/naming/
- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=Box-Of-Hats.bemhelper

## Source Controls

### :card_index_dividers: GitLens — Git supercharged

Eine richtig mächtige Extension um detailliert mit Git umzugehen. Am nützlichsten finde ich die Git Blames neben der Code-Zeile. Schaut's euch an, es kann viel, wovon ich wahrscheinlich gerade mal 10% nutze :D

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens

### :card_index_dividers: Git: Git Graph
Kennt ihr Tower oder SourceTree? Wenn Ihr in VSCode eine Graph-Ansicht eures Git-Repos fehlt, ist das genau das richtige für euch!

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph

### :card_index_dividers: Git: Conventional Commits :tickets:

Ihr fragt euch immer, wie man vernünftige Changelogs generiert? Ohne, dass dabei Fake- oder Maintenance-Commits aussen vor bleiben? Dann helfen euch `Conventional Commits`. Im Grunde genommen einfach eine Methode/Naming Convention für Commit messages, die aber einfach "parse-bar" sind, weil sie systematisch aufgebaut sind.

  - :man_student: **Mehr zu Conventional Commits**: https://www.conventionalcommits.org/en/v1.0.0/#summary
  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits

## Deployments/Builds/Pipelines/CI

### :electric_plug: Remote - SSH

Ihr arbeitet mit Remote-Boxen und SSH? Dann hilft euch diese Extension. Mit ihr könnt ihr ganz einfach Projekte in Visual Studio Code öffnen, als wärt ihr lokal auf der Maschine!

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh
  -
### :recycle:	CircleCI

Wenn ihr CicleCI als Continous Integration Pipeline Service nutzt, ist diese Extension nicht schlecht, um die Builds im Auge zu halten.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=jodyh.circleci-vscode

## VSCode Modding

### :lipstick: Studio Icons

Fügt die klassischen Visual Studio Icons in eurem Visual Studio **Code** Dateiexplorer ein.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=jtlowe.vscode-icon-theme

### :lipstick: Peacock

Ändert die Rahmenfarbe von Visual Studio Code. Perfekte Ergänzung zu eurem Theme :)

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=johnpapa.vscode-peacock

### :lipstick: Customize UI

Erlaubt es euch, das VSCode-Interface zu ändern.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=iocave.customize-ui

## Projekt und Arbeitsorganisation

### :card_index_dividers: Project Manager

Ein absolutes must-have, wenn ihr mit mehreren Projekten arbeitet. Speichert eure Projekte und greift per Shortcut auf die Liste zu! Projekte wechseln war noch nie so einfach!

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager

### :card_index_dividers: Monorepo Workspace

Nützliche Extension, wenn mit Mono-Repos gearbeitet wird. Hilft dabei, konkrete Projekte aus dem Repo in einem einzelnen Fenster zu öffnen, und mehr.

Unterstützt Lerna, Yarn, Pnpm und Rushjs

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=folke.vscode-monorepo-workspace

### Github

#### :inbox_tray: Github Pull Requests and issues

Ermöglicht euch, innerhalb von Visual Studio Github Pull Requests zu erstellen, zu verwalten und zu reviewen.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github

### Jira

#### :tickets: Jira and Bitbucket (Atlassian Labs)

Wenn du mit Jira arbeitest, ist das hier eine richtige Erleichterung: Die Extension rendert einige Views von Jira (Tickets, Boards, etc.) inline in VSCode. Kein Browser mehr nötig, und die Tickets lassen sich wie gewohnt in der Tableiste auf festpinnen.

Das zuletzt geöffnete Ticket findet sich dann als Info in der Statusleiste unten für einen schnellen Zugriff.

Richtig nice: Es gibt einen Start Work Button, der für das Ticket

1. den richtigen Status einstellt
1. als Branch erstellt
1. dich als Assignee einsetzt

Und Time Tracking gibt's natürlich auch ;)

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=Atlassian.atlascode

#### :tickets: Flow / Jira Commit prefix

Habe ich eine ganze Weile benutzt, bevor ich Conventional Commits benutzt habe: Fügt euren Commit messages das Ticket als Prefix hinzu.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=emilianox.flow-jira-commit-prefix


### :card_index_dividers: Todo Tree

Zeig alle TODOs oder ähnliche Kommentare im Source-Code in einer gesonderten Liste an.

   - :arrow_lower_right: **Downloads:** https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree
### :bookmark: Bookmarks

Monster-Codebase am Start? Du verwaltest viele Projekte gleichzeitig? Dann wird das hier etwas für dich sein. `Bookmarks` lässt dich im Code bestimmte Stellen mit Lesezeichen versehen. Anschließend findest du in einem Panel in der Sidebar besagtes Lesezeichen. Have fun!

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks

## ThirdParty Verbindungen

### :electric_plug: Docker

Verwaltet Images & Container innerhalb von Visual Studio Code. Starten, Stoppen, Löschen, Anlegen und vieles mehr ist hier möglich.

  - :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker

### :electric_plug: SQL Manager

SQL Client für VSCode! **Must-Have**, wenn's um die Arbeit mit Datenbanken geht.

- :arrow_lower_right: **Download:** https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-database-client2
