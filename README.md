# Contents

-   [MacOS Environment Setup](#macos-environment-setup)
    -   [Git](#git)
    -   [NVM](#nvm)
    -   [Node.js](#nodejs)
    -   [Yarn / Npm](#yarn--npm)
    -   [RVM](#rvm)
    -   [CocoaPods](#cocoapods)
    -   [Watchman](#watchman)
    -   [RNV](#rnv)
    -   [JDK](#jdk)
-   [Windows Environment Setup](#windows-environment-setup)
    -   [Git](#git-1)
    -   [NVM Windows](#nvm-windows)
    -   [Node.js](#nodejs-1)
    -   [Yarn / Npm](#yarn--npm-1)
    -   [Watchman](#watchman-1)
    -   [Chocolatey](#chocolatey)
    -   [JDK](#jdk-1)
    -   [RNV](#rnv)
-   [Tools / IDEs (Development)](#tools--ides-development)
    -   [iTerm2](#iterm2)
    -   [Visual Studio Code](#visual-studio-code)
    -   [Android Studio](#android-studio)
    -   [Xcode](#xcode)
    -   [Tizen Studio](#tizen-studio)
    -   [webOS Studio](#webos-studio)
    -   [Postman](#postman)
    -   [Sourcetree](#sourcetree)
-   [Miscellaneous tools](#miscellaneous-tools)
    -   [Figma](#figma)
    -   [Slack](#slack)
    -   [Github](#github)
    -   [Transporter](#transporter)
    -   [ConEmu](#conemu)


# MacOS Environment Setup

Recommended environment setup for every developer

Follow this guide to set up your development machine smoothly

-   Tip: Install the [iTerm2 terminal tool](#iterm2) as the first thing for a more convenient setup process`

## Git

Version control system

Two most convenient ways to install Git are:

-   Using XCode developer tools

    -   Open terminal
    -   Run 
    ```
    git --version
    ```
    -   Prompt opens asking to install developer tools
    -   After installation verify the setup using 
    ```
    git --version
    ```

-   Using homebrew (the package management system for Mac https://brew.sh/)

    -   Run 
    ```
    brew install git
    ```
    -   After installation verify the setup using 
    ```
    git --version
    ```

Afterwards, follow the documentation to authenticate your git setup either with a personal access token or with a SSH key

Docs reference: https://docs.github.com/en/github/getting-started-with-github/getting-started-with-git/caching-your-github-credentials-in-git

## NVM

Node.js version manager, used to switch between various node versions for development purposes

To install nvm:

-   Since macOS 10.15, the default shell is zsh and nvm will look for .zshrc to update, none is installed by default. Create one with 
```
touch ~/.zshrc
```

-   Run 
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```

-   Restart terminal

-   After installation verify the setup using 
```
nvm --version
```

Docs reference: https://github.com/nvm-sh/nvm

## Node.js

Node.js is a JavaScript runtime

To install node.js use the node version manager, which was installed previously

-   Run the following to install the recommended node version
```
nvm install 14.15.5
``` 

More information regarding node.js versioning using the nvm tool can be found by running `nvm`

## Yarn / Npm

Yarn and Npm are package managers

Recommended package manager to use is yarn. The npm package manager comes bundled with Node.js, which was installed previously

To install yarn:

-   Run 
```
npm install --global yarn
```

-   After installation verify the setup using 
```
yarn --version
```

## RVM

Rvm is a Ruby package manager

To install rvm and setup the script source afterwards:

-   Run 
```
curl -sSL https://get.rvm.io | bash -s stable
```

-   Run 
```
echo "source $HOME/.rvm/scripts/rvm" >> ~/.bash_profile
```

-   Restart terminal
-   Install a version of Ruby by running 

```
rvm install 2.6
```

-   Restart terminal and run the following to verify setup
```
rvm list
``` 

Docs reference: https://rvm.io/rvm/install#installation

## CocoaPods

CocoaPods is a dependency manager for Swift and Objective-C Cocoa projects

To install CocoaPods:

-   Run 
```
sudo gem install cocoapods
```

-   After installation verify the setup using 
```
sudo gem which cocoapods
```

More information can be found in https://cocoapods.org/

## Watchman

Watchman is a file watching service used to record file changes (for development)

To install Watchman using homebrew:

-   Run 
```
brew update
```

-   Run 
```
brew install watchman
```

Docs reference: https://facebook.github.io/watchman/docs/install.html#buildinstall

## RNV

Renative is the universal development SDK to build multi-platform projects with react native

To install rnv:

-   Run 
```
npm install rnv -g
```

-   After installation verify the setup using 
```
rnv --version
```

Docs reference: https://renative.org/docs/intro-installation

### RNV Developement

To develop and expand RNV functionality clone https://github.com/pavjacko/renative repository to your local machine.

> If you have previously installed rnv with `npm` or `yarn` you should run either `npm uninstall -g rnv` or `yarn global remove rnv`

To use local version of rnv on your local machine open the project in the terminal and run `yarn bootstrap`. This action will allow for use of `rnv` in any terminal, just like after a global install using a package manager.

If you are using another project and it also uses rnv make sure to run `yarn link rnv` to tell package manager to use local version and not the one defined in the project. Moreover, you can run `yarn watch` in renative project to watch for changes in the renative code, it will automatically update rnv used in your project.

> For Windows you will also need to add yarn bin folder to your Path variable in order to link it properly. The default path is `C:\Users\YOUR_USERNAME\AppData\Local\Yarn\bin` 

Docs reference: https://renative.org/docs/guide-develop

## JDK
Java Development Kit needs to be installed when developing for Android, to do that run

```
brew install --cask adoptopenjdk/openjdk/adoptopenjdk8
```

# Windows Environment Setup

Recommended environment setup for every developer on windows machine is a little different compared to macOS. Most importantly no iOS simulators or builds are possible on this operating system, nevertheless you can develop for android, web and windows itself so there is no reason to discard it.

Follow this guide to set up your development machine smoothly

## Git

On Windows git can be installed with the instalation of most IDEs, version management tools (ex. Sourcetree), however as a standalone install you need:

-   Download Windows installer https://git-scm.com/downloads
    -   Run the Windows installer for Git
    -   In 'Select Components' uncheck 'Git GUI Here' and check 'Add a Git Bash Profile to Windows Terminal'
    -   Select 'Use Visual Studio Code as Git's default editor' in the default editor selection window (Optional, you can use another tool you're comfortable with)
    -   In 'Configure the line ending conversions' select 'Checkout as-is, commit Unix-style line endings'
    -   After installation verify the setup using the following command in a newly opened PowerShell window. 
    ```
    git --version
    ``` 
    
Afterwards, follow the documentation to authenticate your git setup either with a personal access token or with a SSH key

Docs reference: https://docs.github.com/en/github/getting-started-with-github/getting-started-with-git/caching-your-github-credentials-in-git

## NVM-Windows

This not exactly the same `nvm`, which we recommend using on MacOS (more about the differences [here](https://github.com/coreybutler/nvm-windows#whats-the-big-difference)), however it does serve the same purpose - switching in between node versions during development.

To install nvm-windows:

-   [Download the latest version of nvm-windows installer (nvm-setup.zip)](https://github.com/coreybutler/nvm-windows/releases). You need only the `nvm-setup.zip` file, which only has the installer inside, or you can do a manual install yourself if something does not work, instruction for that can be found [here](https://github.com/coreybutler/nvm-windows/wiki#manual-installation).

-   After installation verify the setup using the following in a newly opened PowerShell window
```
nvm --version
``` 

Docs reference: https://github.com/coreybutler/nvm-windows

## Node.js

Node.js is a JavaScript runtime

To install node.js use the node version manager, which was installed previously

-   Run the following command to install node. (For the latest stable node use `nvm install latest`)
```
nvm install 12.22.1
``` 
    
-   To use the installed version of node you also have to open PowerShell with administrative rights and run (or if you installed a newer version replace the number accordingly)
```
nvm use 12.22.1
``` 


More information regarding node.js versioning using the nvm tool can be found by running `nvm`

## Yarn / Npm

Yarn and Npm are package managers

Recommended package manager to use is yarn. The npm package manager comes bundled with Node.js, which was installed previously

To install yarn:

-   Run 
```
npm install --global yarn
```

-   After installation run the following command in your elevated PowerShell window ([Source](https://stackoverflow.com/a/58765137/12541129), where this was taken from)
```
Set-ExecutionPolicy RemoteSigned
``` 

-   After installation verify the setup using 
```
yarn --version
```

## Watchman

Watchman is a file watching service used to record file changes (for development)

To install Watchman you will need to follow [instructions provided by facebook](https://facebook.github.io/watchman/docs/install.html#windows). In short:

-   Download the latest watchman windows build [here](https://github.com/facebook/watchman/releases/tag/v2021.01.11.00)

-   Create a folder named `watchman` in your `C:\Users\YOUR_USERNAME\AppData\Local` (replace YOUR_USERNAME with the username you have/use for your windows machine). In case you don't see the AppData folder press on 'View' in File Explorer and tick the 'Hidden Items' checkbox.

-   Extract content inside the downloaded windows build `bin` folder to the newly created folder. You want the `watchman.exe` to appear as top level file inside that folder, so the `bin` folder should not even be present inside `C:\Users\YOUR_USERNAME\AppData\Local`, only the content needs to be copied/extracted.

-   Add path to `watchman.exe` to enviroment variables by searching `environment variables` in Windows search. Next you will be prompted with `System Properties` dialogue. Press on `Environment Variables`, double click on `Path` or click once and then click on `Edit`, then press `Add` or double click on an empty line and paste the path to the watchman folder.

-   Press 'OK' until all dialogue windows are closed and restart your computer.

-   To validate installation open a new PowerShell window and type the following. If you see a version number it means the installation was successful.
```
watchman -v
```

Helpfull guide for this (except for the part where windows build is downloaded from Github Actions) with visual explanations can be found [here](https://stackoverflow.com/a/61130615/12541129).

Docs reference: https://facebook.github.io/watchman/docs/install.html#windows

## Chocolatey

Chocolatey is a package manager similar to brew used on MacOS. It's mainly used to install/update JDK and a few other packages.

To install it run:
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

Docs reference: https://chocolatey.org/install

## JDK

Java Development Kit needs to be installed when developing for Android, to do that run

```
choco install -y openjdk8
```
## RNV

Refer to [RNV](#rnv) in MacOS environment setup for this step.
# Tools / IDEs (Development)

Reccomended / necessary tools for every developer

## iTerm2

> Only available for MacOS, skip the installation of iTerm2 if you're using Windows

Terminal replacement tool, which allows you to setup a more flexible terminal

Download from https://iterm2.com/downloads.html

To create a flexible terminal development setup:

-   Arrange your development window with: `right click + split pane`

-   Save the configuration with: `Window -> Save Window Arrangement`

## Visual Studio Code

Lightweight IDE for general code development with a convenient extension library

Download from https://code.visualstudio.com/download

-   Open the downloaded installer

-   Complete the setup

-   For Windows install it's also recommended to check all the boxes in 'Select Additional Tasks' window under 'Other' options

-   For MacOS users: move the Visual Studio Code application to your Applications folder

-   For Windows users: move the Visual Studio Code installer to bin

After successfully setting up VS Code it is strongly recommended to set up the following extensions

-   [Prettier (code formatting)](https://github.com/prettier/prettier-vscode)

    -   Tip: Set up prettier as your default formatter and turn on `Format on Save` to make your life easier and have cleaner code
    -   If you encounter any issues see this reference: https://stackoverflow.com/a/64273353

-   ESLint (integrates ESLint into code formatting)

-   Custom colour theme (to feel like a proper developer)

-   GitLens (helps with version control)

-   Bracket Pair Colorizer

-   indent-rainbow

-   Todo Tree

-   Visual Studio Intellisense

## Android Studio

Advanced Android debugging / profiling

Download Android Studio (which setups the required SDK) from https://developer.android.com/studio

### Further steps on MacOS

To install Android studio follow the documentation from https://developer.android.com/studio/install#mac

-   Launch the installed Android studio and complete the setup by downloading any required SDK or virtual devices

-   Any further SDK configurations or virtual device setups can be done using the Android studio manager

To configure Android SDK path variable in macOS (required for launching Android applications)

-   Find the path to where your SDK is installed (Generally, the Android SDK is installed in the /Users/user-name/Library/Android/sdk folder on macOS)

-   Use nano to create or edit user bash (or zsh) profile in user home directory `nano .bash_profile`

-   Add `ANDROID_HOME` and `PATH` environment variables in user bash (or zsh) profile

-   Reference: https://stackoverflow.com/a/33631853

To configure Android SDK and NDK path with Renative

-   Find your workspace path, which includes the renative.json file (~/.reactseals/renative.json)

-   Add missing SDK and NDK paths

-   Reference: https://renative.org/docs/api-config#sdks

### Further steps on Windows


-   Make sure virtualization is enabled for your CPU and Hyper V is installed

-   Launch the installed Android studio and complete the setup by downloading any required SDK or virtual devices (for mobile development API level 30 may not work, make sure to have an emulator with an older API level)

-   Add Android SKD path to enviroment variables
```
setx ANDROID_HOME "C:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk"
```
-   Add platform tools to Path variable

The steps above in more detail:

Process is similar to the one described on MacOS, however, on MacOS virtualisation is enabled by default, on Windows it's disabled by default, so you might need to turn it on if you haven't already.

First step is to turn CPU virtualisation in your BIOS.

> Note. Not all CPUs support virtualisation, so you need to make sure yours does before proceeding further.

Typically this is done in your BIOS settings and therefore differs immensely based on the manufactorer of your motherboard and your CPU.

Docs reference for AMD CPUs: https://android-developers.googleblog.com/2018/07/android-emulator-amd-processor-hyper-v.html </br>
Docs reference for Intel CPUs: https://www.howtogeek.com/213795/how-to-enable-intel-vt-x-in-your-computers-bios-or-uefi-firmware/

Next step would be to enable Hyper V in Windows. It's mentioned in the guides linked above, but in case you missed it, search for 'windows features' and in the opened dialogue window press on the checkbox to enable it.

After enabling Hyper V follow the instructions in Android Studio MacOS setup up until the step, which includes `.bash_profile` file. On windows such file is not used and what you need to do is to add (if it wasn't added by default) Android SDK path to a new ANDROID_HOME variable in enviroment variables. The process is the same as you already went through when installing watchman:

-   Add Android SKD path to enviroment variables either by using PowerShell with administrative rights (`setx ANDROID_HOME "C:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk"`) or searching `environment variables` in Windows search. In the latter case you will be prompted with `System Properties` dialogue. Press on `Environment Variables`, double click on `New..` and enter variable name, which is ANDROID_HOME and then the path, which by default will be `C:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk`, so unless you specified some other location during the instalation of Android Studio all you need to change is YOUR_USERNAME to match you actual username.

-   Final step is to add platform tools to your Path variable. I recommend to do this using dialogue window, because most of the commands I tried which should update Path variable actaully modify it deleting the previous values. Add platform tools location to enviroment variables by searching `environment variables` in Windows search. Then you will be prompted with `System Properties` dialogue. Press on `Environment Variables`, double click on `Path` and enter variable name in the empty line at the end by double clicking it or just pressing `New`, default path, whcih you need to add, should be `C:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk\platform-tools`.
## XCode

> Only available for MacOS, skip the installation of XCode if you're using Windows

Advanced iOS debugging / profiling

Installing XCode depends on what macOS version is used on your development machine

If you are using at least macOS Big Sur 11, you can download the latest XCode version from the App Store

-   Open App Store

-   Search for XCode

-   Press install

For any lower versions of macOS the suggested approach is to download a custom version of XCode

You can find which version is compatible to your machine from https://developer.apple.com/support/xcode/

The recommended version to use is 12.4, since it is compatible with the latest deployment requirements for iOS apps

You can find all the available XCode downloads from https://developer.apple.com/download/all/?q=xcode

-   Download XCode 12.4

-   Open the downloaded installer

-   Complete the setup

-   Move the XCode application to your Applications folder

## Tizen Studio

Tizen development / debugging

TODO

## webOS Studio

LG Webos development / debugging

TODO

## Postman

Software used for API testing

Download the Postman application from https://www.postman.com/downloads/

-   Open the downloaded installer

-   Complete the setup

-   (MacOS) Accept the prompt to move the application to the Applications folder

-   Create and setup your Postman account to finish the installation process

## Sourcetree

(Optional as some use VSCode, Github Desktop and other solutions for this as well)

Version control tool used to manage your version control workflow without using the Git CLI

Download the Sourcetree application from https://www.sourcetreeapp.com/

-   Open the downloaded installer

-   Complete the setup

-   Accept the prompt to move the application to the Applications folder

More information on how to use the Sourcetree application with Git can be found in the official documentation

Docs reference: https://confluence.atlassian.com/get-started-with-sourcetree

# Miscellaneous tools

## Figma

TODO

## Slack

Software used for internal communication in the development (and other) teams

The Slack application can be downloaded from the App Store:

-   Open App Store

-   Search for Slack

-   Press install

-   Login with your work email to join the workspace

## Github

An account in Github is required to use the version control system

Register / login in https://github.com/

## Transporter

> Only available for MacOS, skip the installation of Transporter if you're using Windows

Software used for delivering iOS and TvOS production builds to Testflight

The Transporter application can be downloaded from the App Store:

-   Open App Store

-   Search for Transporter

-   Press install

-   Login with your Apple ID


## ConEmu

(Optional)
> Only available for Windows, skip the installation of ConEmu if you're using MacOS 

Having multiple windows of PowerShell or cmd open on your Windows machine tends to be annoying and managing them is rather difficult. For instance, to open CMD in a selected folder every time you start your machine you will have to cd into the directory, which is certainly less than ideal. To deal with that:
- [Download ConEmu](https://conemu.github.io/)
- Create multiple windows (not tabs) by splitting vertically and horizontally
- Navigate on each to the folder you will be working in
- Save current window selection

Having done that everytime you open ConEmu, it will open all the windows in correct location, saving some time for you. 
