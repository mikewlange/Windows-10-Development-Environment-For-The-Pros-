# Windows 10 Modern Developer Setup
[![N|Solid](https://i.imgur.com/TjqgfC6.png)](https://www.fart.school) <br>

I'm sharing this as I needed to set up a Windows 10 dev box the other day. I haven't used windows for dev in 7 years and I have to be agile enough to work in any language on almost every modern platform with minimul config and I'm pretty happy with this set up, so here you go. Most of it can be done right in the terminal. but don't just go copy and pasteing, research what everything is if you do not know. 

This started as a fork of something - but now completly different. Thanks for making my life easier mystery person.. 

## Configure Windows
Set-WindowsExplorerOptions -EnableShowHiddenFilesFoldersDrives -EnableShowProtectedOSFiles -EnableShowFileExtensions -EnableShowFullPathInTitleBar

Update-ExecutionPolicy Unrestricted

cinst -y Microsoft-Hyper-V-All -source windowsFeatures

## other package managers
cinst -y cmder -pre
cinst -y hyper 
cinst -y Gow 

## For the love of git
cinst -y git.install
cinst -y poshgit 
cinst -y git-credential-winstore
cinst -y github

## Editors
cinst -y visualstudiocode
Sublime 3 = nest exitor availible for multi language programming. get it. but VScode is close on its tail. 

## IDE's
https://www.jetbrains.com/ - best 50$ a month you can spend on your career, a close 2nd is 
http://www.adobe.com/creativecloud.html   

## Ruby, Go, Python
cinst -y ruby
cinst -y ruby.devkit
cinst -y golang
cinst -y python
cinst -y pip
cinst -y easy.install
choco install composer (if you have to use php)

## Node, npm
cinst -y nodejs.install
npm install -g npm-windows-upgrade

## Docker
 https://download.docker.com/win/stable/DockerToolbox.exe
 
## Virtual Box and Vagrant
cinst -y virtualbox 
cinst -y virtualbox.extensionpack
cinst -y vagrant

## m$ Cloud 
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

## Deployment and Build
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
cinst -y win32-openssh
if (Test-PendingReboot) { Invoke-Reboot }

#### Pinn it
Install-ChocolateyPinnedTaskBarItem "$env:programfiles\Google\Chrome\Application\chrome.exe"

let's get Updates, too
Install-WindowsUpdate -acceptEula

## Electron 
cinst electron
Simetimes we have to 
choco install composer

## FROFILING
choco install newrelic

## My Machine Learning Stack
https://github.com/mikewlange/cheatsheets-ai-fork - Big list and neural network descriptions. 
https://github.com/NVIDIA/caffe
https://github.com/torch
https://github.com/torch/cutorch
https://github.com/rhiever/tpot

## Other stufff
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
Automate this instalation thanks to the magic of [Boxstarter](http://boxstarter.org/). Simply start PowerShell as Administrator and run:

```
START ... figure it out! :)
```
