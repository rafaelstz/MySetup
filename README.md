# MySetup

My machine setup in MacOS Sierra and Linux Ubuntu

# MacOS Sierra

## Firewall turn on

sudo defaults write /Library/Preferences/com.apple.alf globalstate -int 1

## Xcode

xcode-select --install

## Homebrew

/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

## Cask

brew tap caskroom/cask

## Dropbox

brew cask install dropbox

## Mackup

brew install mackup

mackup restore

## Mac App Store command line interface

brew install mas

## Oh-My-Zsh

mv ~/.oh-my-zsh ~/.oh-my-zsh.bkp

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

mv ~/.oh-my-zsh ~/.oh-my-zsh.bkp2

mv ~/.oh-my-zsh.bkp ~/.oh-my-zsh

## Update .zshrc

vim ~/.zshrc

ZSH=$HOME/.oh-my-zsh

plugins=(git git-flow github node npm osx docker docker-compose brew)

source $ZSH/oh-my-zsh.sh

export PATH=/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/mysql/bin:/usr/X11/bin

## Brew install

brew install \

tree \

node \

ssh-copy-id \

wget \

caskroom \

cask \

brew-cask

## Brew Cask install
brew cask install \

sequel-pro \

tunnelblick \

docker \

boot2docker \

docker-toolbox \

kitematic \

firefox \

google-chrome \

itau \

postman \

spotify \

skype \

vagrant \

vagrant-manager \

virtualbox \

visual-studio-code \

vlc

# OS X Preferences

## Enable character repeat on keydown

defaults write -g ApplePressAndHoldEnabled -bool false

## Set a shorter Delay until key repeat

defaults write NSGlobalDomain InitialKeyRepeat -int 12

## Turn on dashboard-as-space

defaults write com.apple.dashboard enabled-state 2

## Use plain text mode for new TextEdit documents

defaults write com.apple.TextEdit RichText -int 0

## Make top-right hotspot start screensaver

defaults write com.apple.dock wvous-tr-corner -int 5 && \

defaults write com.apple.dock wvous-tr-modifier -int 0

## Set default Finder location to home folder (~/)

defaults write com.apple.finder NewWindowTarget -string "PfLo" && \

defaults write com.apple.finder NewWindowTargetPath -string "file://${HOME}"

## Expand save panel by default

defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true

## Disable ext change warning

defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false

## Check for software updates daily, not just once per week

defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1

## Use current directory as default search scope in Finder

defaults write com.apple.finder FXDefaultSearchScope -string "SCcf"

## Show Path bar in Finder

defaults write com.apple.finder ShowPathbar -bool true

## Show Status bar in Finder

defaults write com.apple.finder ShowStatusBar -bool true

## Show icons for hard drives, servers, and removable media on the desktop

defaults write com.apple.finder ShowExternalHardDrivesOnDesktop -bool true && \

defaults write com.apple.finder ShowHardDrivesOnDesktop -bool true && \

defaults write com.apple.finder ShowMountedServersOnDesktop -bool true && \

defaults write com.apple.finder ShowRemovableMediaOnDesktop -bool true

## Avoid creating .DS_Store files on network volumes

defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

## Disable disk image verification

defaults write com.apple.frameworks.diskimages skip-verify -bool true && \

defaults write com.apple.frameworks.diskimages skip-verify-locked -bool true && \

defaults write com.apple.frameworks.diskimages skip-verify-remote -bool true

## Trackpad: map bottom right corner to right-click

defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad TrackpadCornerSecondaryClick -int 2 && \

defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad TrackpadRightClick -bool true && \

defaults -currentHost write NSGlobalDomain com.apple.trackpad.trackpadCornerClickBehavior -int 1 && \

defaults -currentHost write NSGlobalDomain com.apple.trackpad.enableSecondaryClick -bool true

## Enable the Develop menu and the Web Inspector in Safari

defaults write com.apple.Safari IncludeInternalDebugMenu -bool true && \

defaults write com.apple.Safari IncludeDevelopMenu -bool true && \

defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true && \

defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true && \

defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

## Show the ~/Library folder

chflags nohidden ~/Library

## Show absolute path in finder's title bar. 

defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES

## Auto-play videos when opened with QuickTime Player

defaults write com.apple.QuickTimePlayerX MGPlayMovieOnOpen 1

## Enable AirDrop over Ethernet and on unsupported Macs

defaults write com.apple.NetworkBrowser BrowseAllInterfaces -bool true

## Disable WebkitNightly.app's homepage

defaults write org.webkit.nightly.WebKit StartPageDisabled -bool true


# Setup Github

ssh-keygen -t rsa -C "rafaelcg_stz@hotmail.com"

## copy ssh key to github.com

vim ~/.ssh/id_rsa.pub

## test connection

ssh -T git@github.com

## set git config values

git config --global user.name "Rafael Corrêa Gomes"

git config --global user.email "rafaelcg_stz@hotmail.com"

git config --global github.user rafaelstz

#git config --global core.editor "subl -w"

git config --global color.ui true

git config --global push.default simple

## token

git config --global github.token your_token_here

# diff-so-fancy

brew install diff-so-fancy

git config --global pager.diff "diff-so-fancy | less --tabs=4 -RFX" && \

git config --global pager.show "diff-so-fancy | less --tabs=4 -RFX"
