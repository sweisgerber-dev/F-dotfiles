Preamble
--------

![You dot know nothing about stow](https://dl.dropboxusercontent.com/u/1026715/ygritte-meme.png)

Rings true?  
Then, unless you re part of the Greyjoy<sup>1</sup> family, you should read this [article](http://brandon.invergo.net/news/2012-05-26-using-gnu-stow-to-manage-your-dotfiles.html) that present it briefly.

<sup>1</sup> not the intended audience, obviously. Reminder: *"[We do not stow"](https://scifi.stackexchange.com/questions/4222/what-does-house-greyjoys-motto-we-do-not-sow-mean)* -- House Greyjoy's motto

_dotfiles
---------

_dotfiles is a stow-based organization scheme for folks wary of advanced
bash magic.

Power comes from its strict adhesion to the *Three Old Rules* :

    1. underbar rule: folders part of a stow package path starts with a '_'
    2. local rule: files that shall be kept secret ends with '.local'
    3. common rule: files located in the `/common` folder are not stowed

Benefits
--------

The rules might seem abstract but the benefits are tangible :

- *Unity*. All configuration folders lie in a single place yet distinction between
  classic vs stowable folders is made obvious with the `_` prefix.
- *Simplicity*. Any dot file installation - may it be os or environment
  dependant - is just one `stow` command away. Type `stow _*` to install all
  packages.
- *Transparency*. Same ignore patterns apply for all files tree: `*local` files
  are not commited, `/common/*` files are not stowed.
- *Discoverability*. Type `_<TAB>` to browse through stow packages
  configurations.
- *DRYability*. A configuration file spread across various locations on
  different OS has a single _dotfiles represention.

Install
-------

- `git clone https://github.com/Kraymer/_dotfiles.git`
- edit env/platform specific packages to ignore in `/.stow-local-ignore`
- stow 'em all, starting by stow: `stow _stow _*`

FAQ
---

*Where to save a file that is installed at different locations depending on the
OS ?*

see ST3
