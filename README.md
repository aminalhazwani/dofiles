# Dotfiles (Amin Al Hazwani)

When a new OS arrives I usually install it from scratch. Recently Apple has been presenting a new OS X every year and – in my opinion – is good practice to do a clean install when you chose to download it. A year is a lot of time and a fresh start for your machine is more than welcome. This guide provides all the necessary dotfiles to put your computer back in place. Without hassle. So dive in installing and setting my collection OS X dotfiles.

## Terminal
I spend a lot of time in Terminal.app. So it's good practice to setup a nice and [solorized](http://ethanschoonover.com/solarized) environment
```
$ cd ~
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.aliases
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.bash_profile
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.bash_prompt
```

Avoid SHIFT button for capital letters while typing? YES please!
```
$ cd ~
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.inputrc
```
__Note__: in Terminal.app while navigating you can press TAB to autocomplete your path.

## Git
I usually install git with [Homebrew](http://brew.sh/). If you need to install Homebrew follow this simple two steps I showed in [this guide](https://github.com/aminalhazwani/mac-web-dev-setup) on how to set your Mac for web development
```
brew install git
```
add some nice colors to the basic git commands and outputs
```
$ cd ~
$ curl -O https://github.com/aminalhazwani/dotfiles/blob/master/.gitconfig
```
define your git user
```
$ git config --global user.name "Your Name Here"
$ git config --global user.email "your_email@youremail.com"
```
and finally generate a ssh key following [this guide](https://help.github.com/articles/generating-ssh-keys/).

## Vim
It could happen that from time to time I need to edit a file on-the-go inside Terminal.app. I prefer [Vim](http://www.vim.org/) over [nano](http://www.nano-editor.org/dist/v2.2/nano.html) so, let's install it
```
$ mkdir -p ~/.vim/autoload ~/.vim/bundle && \
    curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
```
add some basic user preferences
```
$ cd ~
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.vimrc
```
and add some nice colors
```
$ cd ~
$ mkdir .vim
$ cd .vim
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.vim/colors/solarized.vim
```

## Sublime Text
Sublime Text 2 if my text editor of choice. Download it from their [offical website](http://www.sublimetext.com/2).

### Install Package Control
Sublime Text without Package Control is no Sublime Text. Open Sublime Text console with the shortcut `ctrl + backtick` and paste inside it the appropriate Python code for your version of Sublime Text
```
import urllib2,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')
```

### Install packages
These are packages I have currently installed:
- Spacegrey theme
- MarkdownEditing
- AdvancedNewFile

### Sublime Text User preferences
I have a strong passion for typography. This is reflected of course on my type setting in Sublime Text. My favorite coding font is [Input Mono](http://input.fontbureau.com/) by [Font Bureau](http://www.fontbureau.com/).
```
$ cd ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/User/
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/init/Preferences.sublime-settings
```

### Enable to launch Sublime Text from the command-line
While navigating in Terminal.app is really helpful to launch Sublime with just a type of a button. This little hack will allow you to launch Sublime Text. All you need is to type `subl`.
```
$ ln -s /Applications/Sublime\ Text\ 2.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl
```
