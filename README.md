# Dotfiles (Amin Al Hazwani)

My collection of OS X dotfiles: bash, git, vim, etc.

## Terminal
Let's set a nice and [solarized](http://ethanschoonover.com/solarized) terminal
```
$ cd ~
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.aliases
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.bash_profile
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.bash_prompt
```

Ignore case while typing/complimenting
```
$ cd ~
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/.inputrc
```

## Git
```
brew install git
```
and add some nice colors to the basic git commands and outputs
```
$ cd ~
$ curl -O https://github.com/aminalhazwani/dotfiles/blob/master/.gitconfig
```
define your git user
```
$ git config --global user.name "Your Name Here"
$ git config --global user.email "your_email@youremail.com"
```
and generate a ssh key following this guide: [https://help.github.com/articles/generating-ssh-keys/](https://help.github.com/articles/generating-ssh-keys/)

## Sublime Text
Download your preferred version of sublime text: [http://www.sublimetext.com/2](http://www.sublimetext.com/2)

### Install Package Control
Open the Sublime Text console with the shortcut `ctrl + backtick` and paste inside it the appropriate Python code for your version of Sublime Text
```
import urllib2,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')
```

### Install packages
These are my favorites:
- Theme -> Spacegrey
- MarkdownEditing
- AdvancedNewFile

### Sublime Text User preferences
```
$ cd ~/Library/Application\ Support/Sublime\ Text\ 2/Packages/User/
$ curl -O https://raw.githubusercontent.com/aminalhazwani/dotfiles/master/init/Preferences.sublime-settings
```

### Enable to launch Sublime Text from the command-line
```
$ ln -s /Applications/Sublime\ Text\ 2.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl
```

## Vim
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
