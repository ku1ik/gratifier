# gratifier

**gra**vatar no**tifier**.

## About

**gratifier** is a wrapper for desktop notification utilities that allows you
to display notifications with avatar image as notification icon.

Avatar images are fetched from [gravatar.com](http://www.gravatar.com/) and
cached in `~/.gratifier/gravatars` directory.

It supports following notification utilities:

* `notify-send` on Linux with _libnotify_ (Ubuntu, other Gnome based desktop)
* `kdialog` on Linux with KDE
* `growlnotify` on OSX

## Installation

    $ curl -skL https://github.com/sickill/gratifier/raw/master/bin/gratifier >~/bin/gratifier
    $ chmod +x ~/bin/gratifier

\* Make sure `~/bin` is in your `$PATH` or put `gratifier` script somewhere else
on your `$PATH`.

## Usage

### Option 1: specifying email address

If app that displays notification knows email address of user that triggered
notification:

    $ GRAVATAR_EMAIL=email@example.org gratifier "Notification title" "Notification body"

### Option 2: specifying nickname

If app that displays notification knows only nickname of user that triggered
notification:

    $ NICKNAME=joe gratifier "Notification title" "Notification body"

In this scenario you need to edit `~/.gratifier/nicknames/joe` file and specify
either email address you know for this nickname or path to avatar image.

## Bugs

Report bugs and request new features at <https://github.com/sickill/gratifier/issues>.

## Authors

<https://github.com/sickill/gratifier/contributors>

