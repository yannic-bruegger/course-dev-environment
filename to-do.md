# Notizen und Agenda für den Workshop
- [Notizen und Agenda für den Workshop](#notizen-und-agenda-für-den-workshop)
  - [Introduction](#introduction)
  - [Getting Started](#getting-started)
  - [Package Manager](#package-manager)
  - [Installation Scripts](#installation-scripts)
  - [Configuration Files](#configuration-files)
  - [Config-Dateien ins Repo übernehmen](#config-dateien-ins-repo-übernehmen)
  - [Kurzer Exkurs: VSCode Extensions](#kurzer-exkurs-vscode-extensions)
  - [Sharing is caring](#sharing-is-caring)
  - [**PAUSE**](#pause)
  - [Project (Präsi)](#project-präsi)
  - [Shared Settings](#shared-settings)
  - [Dev-Container](#dev-container)
  - [The little things](#the-little-things)
  - [**PAUSE?**](#pause-1)
  - [Finale Diskussion](#finale-diskussion)

## Introduction

- [ ] Willkommen
- [ ] Wer bin ich?
- [ ] Was will ich hier?
  - Aufmerksamkeit und ggf. Verständnis schaffen
  - Den Werkzeugkasten jeder/jedes zuhörenden erweitern
  - Eine Plattform zum teilen von Erfahrungen und Tools bieten
- [ ] Was will ich nicht?
  - Keinem etwas vorschreiben. Dafür ist das Thema zu spezifisch
  - Mitmachen kann und will ich nicht erzwingen. Es ist bei so einem Thema valide "sich berieseln zu lassen" und nachher zu schaue, ob man etwas adaptiert.

## Getting Started

- [ ] Definieren des Begriffs "Development Environment"
  - **Frage (Optional)**: Was würdet ihr mir zeigen wenn ich sage "Zeig mir mal deine Entwicklungsumgebung!"? 
  - **Frage**: Was ist eine "Entwicklungsumgebung" für dich? (Mini-Diskussion)
  - Vorstellung meiner Interpretation
- [ ] Vorstellen, wie ich meine Entwicklungsumgebung bisher verwaltet habe.
- [ ] Grobe Zeitaufteilung erklären
  - Diskussionen werden auch zwischengestreut
  - Pausen ansprechen
  - Mögliche Verschiebung der Aufteilung

## Package Manager

- [ ] Was sind [Package Manager](https://en.wikipedia.org/wiki/Package_manager)?
- [ ] **Frage**: Wer nutzt Package Manager (und welche)?
  - [apt](https://ubuntu.com/server/docs/package-management), [pamac](https://wiki.manjaro.org/index.php?title=Pamac)
  - [Homebrew](https://brew.sh/)
  - [winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/)
- [ ] **Demo:** Wie nutzt man einen Package Manager
  - Zeige winget (als Admin ausführen)
    - ``winget search <empty>``
    - ``winget search <searchstring>``
    - ``winget install <software>``
    - ``winget uninstall <software>``
  - Zeige Pamac
    - ``pamac search <empty>``
    - ``pamac search git``
    - ``pamac install git``
  - Verweis auf [Homebrew](https://brew.sh/)

## Installation Scripts

- [ ] Git installieren
- [ ] Repo erstellen ``~/.my-config``
- [ ] Repo mit einfacher ``README.md`` initialisieren
- [ ] Software aussuchen und in ``osname/software`` speichern
  - git
  - vscode
  - docker
  - albert
  - zsh
  - stretchly
- [ ] Installationsscript erstellen ``osname/setup.sh``
  - ``pamac install $(cat software) --no-confirm``
  - Docker setup https://docs.docker.com/engine/install/linux-postinstall/
- [ ] Comitten :)

## Configuration Files

- [ ] Aufzeigen der typischen Speicherorte für Konfigurationsdateien ``(~ = $HOME)``
  - Linux u. MacOS
    - ~
    - ~/.config
  - Windows
    - %Appdata%

- [ ] Beispiel VSCode
  - **Windows** %APPDATA%\Code\User\settings.json
  - **macOS** $HOME/Library/Application Support/Code/User/settings.json
  - **Linux** $HOME/.config/Code/User/settings.json
- [ ] Beispiel Git
  - ``~/.gitconfig``

## Config-Dateien ins Repo übernehmen

- [ ] Im Repo den Ordner .config anlegen
- [ ] Ausgewählte Config-Dateien in den Ordner kopieren
- [ ] Benennungsschema erläutern
  - Name der Software
  - Endung wie im Original
- [ ] Kurzer Exkurs: SymLinks?
- [ ] Im Setup-Script Symlinks für alle Anwendungen erstellen 
  - ``ln -sf ~/.my-config/config/.gitconfig ~/.gitconfig``

## Kurzer Exkurs: VSCode Extensions

- [ ] Extensions nicht in den Settings.json
- [ ] Extensions auslesen und in Datei im Repo schreiben ``code --list-extensions > install-code-extensions.sh``
- [ ] Ggf. extensions aussortieren.
  - Diskussion über immer benötigte Extensions. (Themes etc.)
- [ ] Extensions Installer-Script erstellen (``code --install-extension`` vor jede Extension schreiben)
- [ ] Testen
- [ ] Dem Repo hinzufügen und im Setup-Script ausführen

## Sharing is caring

- [ ] Trend erklären und auf Links hinweisen
  - https://dotfiles.github.io/
  - https://www.youtube.com/watch?v=r_MpUP6aKiQ
  - https://wiki.archlinux.org/title/Dotfiles
- [ ] Auf GitHub hochladen
- [ ] README.md um Installationssteps erweitern
```sh
git clone <git-url> ~/.my-config
cd  ~/.my-config/arch
chmod +x setup.sh install-code-extensions.sh
./setup.sh
```
- [ ] **OPTIONAL** Komplette installation vorführen

## **PAUSE**

## Project (Präsi)
- Disclaimer: Fokus auf VSCode

## Shared Settings

- [ ] leeres Repo mit README.md aufsetzen
- [ ] Shared Settings einrichten
  - **Frage**: Welche Einstellungen könnten hier relevant sein?
  - Indentation
  - Line Endings
  - ...?

## Dev-Container
- [ ] **Exkurs (optional):** Container + Docker
- [ ] Setup DevContainer
  - manuelles Setup
    - ``./.devcontainer`` anlegen
    - ``./.devcontainer/devcontainer.json``
    - ``./.devcontainer/Dockerfile``
  - automatisiertes Setup vorstellen
  - Hinzufügen von Extensions
    - Recommendations
    - Add to devcontainer
- [ ] Ausblick Dev-Container können noch mehr!

## The little things
- [ ] ``npx npkill``
- [ ] [``nvm``](https://github.com/nvm-sh/nvm)

## **PAUSE?**

## Finale [Diskussion](discussions.md)