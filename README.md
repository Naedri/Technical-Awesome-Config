# Technical-Awesome-Config

## Required softwares

### Windows

For windows, you can use the following bash script with [PowerShell.exe](https://docs.chocolatey.org/en-us/choco/setup#install-with-powershell.exe) to quickly install the above softwares with [chocolatey](https://docs.chocolatey.org/en-us/#what-is-chocolatey) (a software management for windows). You can look for other softwares at this [page](https://community.chocolatey.org/packages?q=+&moderatorQueue=&moderationStatus=all-statuses&prerelease=false&sortOrder=package-download-count).

```
#!/bin/bash

#===================================
# chocolatey.org
# Run `Get-ExecutionPolicy`. If it returns `Restricted`, then run `Set-ExecutionPolicy AllSigned` or `Set-ExecutionPolicy Bypass -Scope Process`
#===================================
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

#===================================
# dev tools
#===================================
choco install -y nodejs.install
choco install -y vscode
choco install -y postman

#===================================
# git
#===================================
choco install -y git.install
```

#### Additional useful softwares

```
#!/bin/bash

#===================================
# dev tools
#===================================
choco install -y cmder

choco install -y jdk11
choco install -y intellijidea-community

choco install -y insomnia-rest-api-client

choco install -y anaconda3

choco install -y r.project
choco install -y r.studio

#===================================
# git and tools and configuration
#===================================
choco install -y gitextensions

#===================================
# desk tools
#===================================
choco install -y notepadplusplus.install
choco install -y typora
choco install -y libreoffice-fresh

choco install -y sumatrapdf
choco install -y pdfsam.install

choco install -y 7zip.install

choco install -y obs-studio.install
choco install -y gimp
choco install -y inkscape

#===================================
# web tools
#===================================
choco install -y firefox
choco install -y chromium

#===================================
# communication tools
#===================================
choco install -y thunderbird
choco install -y slack
choco install -y figma
```

### Unix

TBD

## Software configuration

### [Git](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)

```
#===================================
# git configuration to use VS Code as your Git core editor, difftool and mergetool
#===================================
git config --global core.editor notepad
git config --global merge.tool vscode
git config --global mergetool.vscode.cmd 'code --wait $MERGED'
git config --global diff.tool vscode
git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'
```

### [VSCode pluggin](https://code.visualstudio.com/docs/editor/extension-marketplace#_command-line-extension-management)

```
#===================================
# vscode command line extension management
#===================================
code --install-extension Huuums.vscode-fast-folder-structure
code --install-extension aaron-bond.better-comments
code --install-extension dbaeumer.vscode-eslint
code --install-extension eamodio.gitlens
code --install-extension esbenp.prettier-vscode
code --install-extension ethansk.restore-terminals
code --install-extension formulahendry.auto-rename-tag
code --install-extension formulahendry.code-runner
code --install-extension nemesv.copy-file-name
code --install-extension quicktype.quicktype
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension visualstudioexptteam.vscodeintellicode
code --install-extension waderyan.nodejs-extension-pack
```

Then install add the [_.vscode_]() folder to your workspace.
