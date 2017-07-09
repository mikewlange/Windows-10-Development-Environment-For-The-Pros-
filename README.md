## Modern Random Programmer Setup. 

## Automate it!
Below, you can see the all the things I need to actually go and work on stuff. If you like all those things, you can automate the installation thanks to the magic of [Boxstarter](http://boxstarter.org/). Simply start PowerShell as Administrator and run:

```
START http://boxstarter.org/package/nr/url?https://raw.githubusercontent.com/felixrieseberg/windows-development-environment/master/boxstarter
```

# Configure Windows
Set-WindowsExplorerOptions -EnableShowHiddenFilesFoldersDrives -EnableShowProtectedOSFiles -EnableShowFileExtensions -EnableShowFullPathInTitleBar

Update-ExecutionPolicy Unrestricted

cinst -y Microsoft-Hyper-V-All -source windowsFeatures

# Packages
cinst -y cmder -pre
cinst -y hyper
cinst -y Gow

## Node, npm
cinst -y nodejs.install

## Git
cinst -y git.install
cinst -y poshgit
cinst -y git-credential-winstore
cinst -y github

## Node, npm
cinst -y nodejs.install
npm install -g npm-windows-upgrade

## Editors
cinst -y visualstudiocode

## Visual Studio 2015
cinst -y visualstudio2015community
if (Test-PendingReboot) { Invoke-Reboot }

## Ruby, Go, Python
cinst -y ruby
cinst -y ruby.devkit

cinst -y golang

cinst -y python
cinst -y pip
cinst -y easy.install

## Docer and stuff
 https://download.docker.com/win/stable/DockerToolbox.exe
 
## Virtual Box 
cinst -y virtualbox
cinst -y virtualbox.extensionpack
cinst -y vagrant

##open SSh
cinst -y win32-openssh

## Cloud 
npm install -g azure-cli
## The Devil
cinst awscli
cinst awstools.powershell

##Goog App Engine CLI
choco install gcloudsdk

##Heroku - The BEst
https://cli-assets.heroku.com/branches/stable/heroku-windows-amd64.exe

##
npm install serverless -g

#### Deployment and Build
GULP
choco install gulp-cli
GRUNT
npm install -g grunt-cli

if (Test-PendingReboot) { Invoke-Reboot }

## Basics
cinst -y vlc
cinst -y GoogleChrome
cinst -y 7zip.install
cinst -y sysinternals
cinst -y DotNet3.5
# cinst -y DotNet4.0 -- not needed on windows 8
# cinst -y DotNet4.5 -- not needed on windows 10
# cinst -y PowerShell -- not needed on windows 10
if (Test-PendingReboot) { Invoke-Reboot }

# Pinning Things
Install-ChocolateyPinnedTaskBarItem "$env:programfiles\Google\Chrome\Application\chrome.exe"

# Let's get Updates, too
Install-WindowsUpdate -acceptEula

### Developer Frameworks and Opesource Stuff that are must haves for me
### Electron 
for cross platofrm windows dev
````
cinst electron
Simetimes we have to 
choco install composer

## FROFILING
choco install newrelic
```
