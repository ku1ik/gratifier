# gratifier

Command line desktop notifications with Gravatars!

## About

TODO

## Installation

    $ curl -skL https://github.com/sickill/gratifier/raw/master/bin/gratifier >~/bin/gratifier
    $ chmod +x ~/bin/gratifier

\* Make sure `~/bin` is in your `$PATH` or put `gratifier` script somewhere else
on your `$PATH`.

## Usage

### Option 1: specifying email address

If your app knows email address of user that triggered notification:

    $ GRAVATAR_EMAIL=email@example.org gratifier "Notification title" "Notification body"

### Option 2: specifying nickname

If your app knows only nickname of user that triggered notification:

    $ NICKNAME=joe gratifier "Notification title" "Notification body"

In this scenario you need to edit `~/.gratifier/nicknames/joe` file (that is
initially empty) and enter email address you know for this nickname.
