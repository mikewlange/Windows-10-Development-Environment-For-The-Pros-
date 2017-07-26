## Modern Random Programmer Setup. 
I'm sharing this as I needed to set up a Windows 10 dev box for modern laguage agnostic deveopment. I've been off windows for almost 10 years. I thought it would be good to write down. 

I use Mac or ubuntu for commercial work. But msoft nailed it with in 10. woudn'tswitch back, but it's now my ML machine. But I'm qite satified with my (incomplete) setup beow. 

This is a fork of something - but completly different. But I did steal the idea to write this here. Thanks for making my life easier mystery person.. 

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

## Ruby, Go, Python, Lua, Java, C
cinst -y ruby
cinst -y ruby.devkit
cinst -y golang
cinst -y python
cinst -y pip
cinst -y easy.install

## Docker and stuff
 https://download.docker.com/win/stable/DockerToolbox.exe
 
## Virtual Box 
cinst -y virtualbox
cinst -y virtualbox.extensionpack
cinst -y vagrant

## open SSh
cinst -y win32-openssh

## Cloud 
npm install -g azure-cli

## The Devil
cinst awscli
cinst awstools.powershell

## The Wonderful
choco install gcloudsdk
cinst gcloud, gsutil and bq 

## The Brilliant 
https://cli-assets.heroku.com/branches/stable/heroku-windows-amd64.exe

## ServerLess
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
cinst -y DotNet4.x
if (Test-PendingReboot) { Invoke-Reboot }

# Pinning Things
Install-ChocolateyPinnedTaskBarItem "$env:programfiles\Google\Chrome\Application\chrome.exe"

# Let's get Updates, too
Install-WindowsUpdate -acceptEula

### Developer Frameworks and Opesource Stuff that are must haves for me
### Electron 
cinst electron
Simetimes we have to 
choco install composer

## FROFILING
choco install newrelic

### My Machine Learning Stack
https://github.com/mikewlange/cheatsheets-ai-fork - Big list and neural network descriptions. 
https://github.com/NVIDIA/caffe
https://github.com/torch
https://github.com/torch/cutorch
https://github.com/rhiever/tpot

## Sometimes
https://github.com/mikewlange/leaf
https://github.com/autumnai/collenchyma
https://github.com/nikolaypavlov/MLPNeuralNet
https://github.com/mikewlange/neon
https://github.com/mikewlange/pattern
https://github.com/Theano/Theano
https://github.com/tensorflow/tensorflow
https://github.com/scikit-learn/scikit-learn
https://github.com/harvardnlp/im2markup


## Automate it!
Below, you can see the all the things I need to actually go and work on stuff. If you like all those things, you can automate the installation thanks to the magic of [Boxstarter](http://boxstarter.org/). Simply start PowerShell as Administrator and run:

```
START ... figure it out! :)
```
