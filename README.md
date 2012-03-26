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

### Step 1: Download

    $ curl -skL https://github.com/sickill/gratifier/raw/master/bin/gratifier >~/bin/gratifier
    $ chmod +x ~/bin/gratifier

\* Make sure `~/bin` is in your `$PATH` or put `gratifier` script somewhere else
on your `$PATH`.

### Step 2: Symlink

gratifier is a very thin wrapper around existing notification utility - it
passes all its command-line arguments down to the actual utility. The only
thing it adds is a proper command-line switch and image path for displaying
avatar.

Now, you must create a symlink to the gratifier script. The name of this
symlink should include the name of your desktop notification utility.

Here are some examples:

    # Gnome/Unity
    $ ln -s ~/bin/gratifier ~/bin/gratifier.notify-send

    # KDE
    $ ln -s ~/bin/gratifier ~/bin/gratifier.kdialog

    # OSX
    $ ln -s ~/bin/gratifier ~/bin/gratifier.growlnotify

    # Some funky symlink names:
    $ ln -s ~/bin/gratifier ~/bin/growlnotify-avatar
    $ ln -s ~/bin/gratifier ~/bin/my-kdialog-with-gravatar

Thanks to this symlink:

* gratifier doesn't need to guess what utility you have installed (or choose one
  if you have let's say both notify-send and kdialog on Linux)

* it gives you clear indication what utility it wraps thus saving you from
  confusion about command-line args you need to pass to it

## Usage

Following usage examples are assuming you have `notify-send` as your notifier.
Adjust script name and arguments to your environment.

### No avatar

Just invoke the script like in old, pre-gratifier days:

    $ gratifier.notify-send "Hey you!"

### Avatar via email address

If you have email address of user that triggered notification invoke gratifier
with `GRAVATAR_EMAIL` env variable like this:

    $ GRAVATAR_EMAIL=email@example.org gratifier.notify-send "Notification title" "Notification body"

### Avatar via nickname

You may want to use gratifier as a notifier for some app that doesn't have
information about email addresses of the users (for example IRC client
like _irssi_).

If you only have nickname of user that triggered notification invoke gratifier
with `NICKNAME` env variable like this:

    $ NICKNAME=joe gratifier.notify-send "Notification title" "Notification body"

If it happens that app displaying notification doesn't know the email address
of user "joe" but **you** know it just edit `~/.gratifier/nicknames/joe` file
and specify his email there. This file will be created for you on first
notification displayed for a nickname. Also, if you don't know joe's email but
you have got his photo you can specify path to the image in the same file.

## Bugs

Report bugs and request new features at <https://github.com/sickill/gratifier/issues>.

## Authors

<https://github.com/sickill/gratifier/contributors>

