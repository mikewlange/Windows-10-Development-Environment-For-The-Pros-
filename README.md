## Bash installation on a new Windowns 10 Machine - w

## Automate it!
Below, you can see the all the things I need to actually go and work on stuff. If you like all those things, you can automate the installation thanks to the magic of [Boxstarter](http://boxstarter.org/). Simply start PowerShell as Administrator and run:

```
START http://boxstarter.org/package/nr/url?https://raw.githubusercontent.com/felixrieseberg/windows-development-environment/master/boxstarter
```

## The Goods

* CORE SHIT
 * [IIS and Whatnot] (#whatnot)
 * [Package Management](#package-management-chocolatey)
 * [Terminal](#terminal-cmder-with-powershell-support)
 * [Bash Tools](#bash-tools-wget-curl-etc-gow)
 * [Node.js](#node)
 * [npm](#npm)
 * [Git](#git)
 * [Atom, Sublime, VS Code](#code-editors-atom-sublime-vs-code)
 * [Ruby](#ruby)
 * [Go](#go)
 * [Python](#python)
 * [DevOps: VirtualBox, Vagrant, Docker](#devops-virtualbox-vagrant-docker)
    * [SSH](#ssh)
    * [Azure Cli](#azure-cli)
    * [AWS Cli](#aws-cli)
 * [Basic Tools](#basic-tools)

#### Package Management: Chocolatey
Chocolatey is a powerful package manager for Windows, working sort of like apt-get or homebrew. Let's get that first. Fire up CMD.exe as Administrator and run:

```
@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
```

Once done, you can install packages by running `cinst` (short for `choco install`). Most packages below will be installed with Chocolatey.

###### Bonus: Use Windows 10 & OneGet
Windows 10 comes with [OneGet](https://github.com/OneGet/oneget), a universal package manager that can use Chocolatey to find and install packages. To install, run:

```
Get-PackageProvider -name chocolatey
```

Once done, you can look for all Chrome packages by typing `Find-Package -Name Chrome` or install it by typing `Install-Package -Name GoogleChrome`.

#### Terminal: CMDer (with PowerShell Support)
The PowerShell in Windows 10 got a bunch of upgrades, but it's even better if used with [CMDer](https://github.com/bliker/cmder/) or [Hyper](https://hyper.is/), both poweful toosl to do more command-line things with. CMDer is the old-school veteran, while Hyper hasn't been around for long. Try both and see what you like more! Install with:

```
cinst cmder -pre
cinst hyper
```

Even if you don't want to use CMDer, you should enable your PowerShell to execute scripts. You're a developer - the terminal is your friend.

```
Set-ExecutionPolicy Unrestricted -Scope CurrentUser
```

If you want to go even futher, check out the attached PowerShell Profile in this repository. It's my personal one and might not be perfect for you, but it makes my personal life a lot easier. You can edit your PowerShell profile with your favorite editor by calling `$PROFILE`, so if you're using Visual Studio Code, call `code $PROFILE` (or `vim $PROFILE` - you get the idea).

#### Bash Tools (wget, curl, etc): Gow
Gow (Gnu On Windows) is the lightweight alternative to Cygwin. It uses a convenient Windows installer that installs about 130 extremely useful open source UNIX applications compiled as native win32 binaries. It is designed to be as small as possible, about 10 MB, as opposed to Cygwin which can run well over 100 MB depending upon options.

```
cinst Gow
```

#### Node
A bunch of tools are powered by Node and installed via npm. This applies to you even if you don't care about Node development. If you want to install tools for React, Azure, TypeScript, or Cordova, you'll need this.

```
cinst nodejs.install
```

#### NPM
You just installed Node, which means that you also installed a slightly outdated version of npm. npm@3 is currently in development and offers a bunch of benefits for Windows users. You probably want to upgrade to npm@3.

```
npm install -g npm-windows-upgrade
npm-windows-upgrade
```

#### Version Control: Git, Subversion, Mercurial
Obviously. If you want Git to be able to save credentials (so you don't have to enter SSH keys / passwords every single time you do anything), also install the Git Credential Manager for Windows.

```
cinst git.install
cinst poshgit

# Restart PowerShell / CMDer before moving on - or run
$env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")

cinst Git-Credential-Manager-for-Windows
cinst github
```

If you're using Mercurial or Subversion, install with:
```
cinst subversion
cinst mercurial
```

#### Code Editors: Atom, Sublime, VS Code
I won't join the war debating which editor is the best, but if you're looking for an editor and not a full IDE, chances are that you'll end up using one of those three.

cinst jetbrainstoolbox


```
cinst SublimeText3
cinst sublimetext3-contextmenu
cinst SublimeText3.PackageControl
cinst SublimeText3.PowershellAlias

cinst Atom
cinst visualstudiocode
```

##### Visual Studio 2015
If you're a .net deveoper on a windows machine buy Visual Studio. Expecially if you only program c#/asp.net and what not. 
````

#### GO 
The languange. I'll put an expesive setup here. 
'''

```
#### Python
Python is a complex world with a bunch of flavors, but Python 3, pip, and easy_install should have you prepared for most things.

```
cinst python
cinst pip
cinst easy.install
````

#### Ruby
becuase you'll run to run gems - other peoples hard work. 
```
cinst ruby
cinst ruby.devkit
``

### DevOps
This stuff is really only relevant if you're interested in DevOps - but if you are, you should probably install the stuff below. It's not likely that you need any of the things below unless you're directly working with it, because none of those things are expected to be installed on a Unix machine.

#### Docker, VirtualBox, Vagrant
If you want to run Docker machines and images, you might not need VirtualBox. In fact, installing VirtualBox on your system isn't always the best idea, given that it messes with a few system components.

Docker released a version for OS X and Windows that no longer requires VirtualBox to be installed - and instead uses the default Hypervisor that comes with the operating system (on Windows, that's Hyper-V). You can [read more about the beta over on Docker's blog](https://docs.docker.com/docker-for-windows/).

```
cinst docker-for-window
```
or win not running 
wget https://download.docker.com/win/stable/DockerToolbox.exe

Virtualbox - monetimes ya need it
```
cinst virtualbox
cinst virtualbox.extensionpack
cinst vagrant
```

#### SSH
If you installed CMDer or Gow as indicated above, you're already set - simply run `ssh` from CMD, CMDer, or PowerShell. If you didn't, use the official Microsoft port of OpenSSH:

```
cinst win32-openssh
```

#### Azure Cli
Super duper useful if you're working with Azure at all.
```
npm install -g azure-cli
```

#### AWS Cli
Super duper useful if you're working with Amazon Web Services at all.
```
cinst awscli
cinst awstools.powershell
```
The Goog
### GOOGLE CLI
choco install gcloudsdk

### IMB Bluemix API
https://console.bluemix.net/docs/starters/install_cli.html

### The Cloud Services if you really want to get shit done
### My Helo - Heroko
``` I've deployed 100's of production apps . Many only after working on them after a few weeks. Never have I gone from code to production than with heroku. That nclues all learning curs. I've used every cloud service and cloud service providor out there. These guys and gals are the best. 
https://cli-assets.heroku.com/branches/stable/heroku-windows-amd64.exe

#### SERVERLESS
npm install serverless -g


#### DATABASES;
choco install heidisql

#### Deployment and Build
GULP
choco install gulp-cli
GRUNT
npm install -g grunt-cli

### Basic Tools
You'll recognize many of these names. Nothing here is crazy unique, it's just stuff you probably want installed to have a well-running machine.
### WHATNOT
IIS
Dism /Online /Enable-Feature /FeatureName:IIS-DefaultDocument /All
Dism /Online /Enable-Feature /FeatureName:IIS-ASPNET45 /All
```
cinst vlc
cinst GoogleChrome
cinst 7zip.install
cinst sysinternals
cinst DotNet3.5
```


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
