# describe

query word definitions from Oxford Dictionaries API

![](https://i.imgur.com/7B4HKZi.png)

## Description

a small shell script for quickly looking up a words meaning, synonyms or antonyms from within the console.

## Installation

In order to make the script work you first have to register a (free) developer account at [Oxford Dictionaries](https://developer.oxforddictionaries.com/) to obtain an `app id` and `app key`.

You then have to provide them to the script by a configuration file called `~/.config/describe`. Create this file
and place the `app id` and `app key` in it like so:

```bash
app_id=12345
app_key=1234567890
```
where 12345 resembles your `app id` and 1234567890 resembles your `app key`.

Optionally, create a symlink to the script to a location contained in your path like _/usr/bin_ or _/usr/local/bin_ to make it conveniently executable from everywhere, e.g.

if you placed the script in /opt/scripts before:

```bash
sudo ln -s /opt/scripts/describe.sh /usr/local/bin/describe
```

## Usage

To query for a words definition simply pass it as an argument to the script

```bash
$ describe tiny

tiny [ˈtʌɪni] is very small
```

Alternatively, you can try deriving the words meaning by its synonyms

```bash
$ describe --synonyms tiny

minute
small-scale
scaled-down
mini
baby
toy
pocket
fun-size
petite
dwarfish
knee-high
miniature
minuscule
microscopic
nanoscopic
infinitesimal
micro
diminutive
pocket-sized
reduced
Lilliputian
```

or its antonyms

```bash
$ describe --antonyms tiny

huge
significant
```

You can also obtain definitions for more than one word at once

```bash
$ describe tiny kitten

tiny [ˈtʌɪni] is very small
kitten [ˈkɪt(ə)n] is a young cat
```

## Requirements

`curl`
`jq`
`sed`
