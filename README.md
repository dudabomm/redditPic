# Reddit Lockscreen

Sets images fetched on reddit as lockscreen.

## Description

This script will automatically download a new lockscreen from reddit every time you log in.
It will require **admin rights** in order to work.
Remember, these images are pulled directly from reddit, so if you like your lockcreen **upvote the post** and give credit where it is due.
(You can find the link to the post in the [logfile](####`-showlog`).

This script was inspired by stibinator's [The Great Dismal](https://github.com/stibinator/GreatDismal).

## Table of content

[Requirements](#Requirements)
[Install](#Install)
[Usage](#Usage)
[Uninstall](#Uninstall)

## Requirements

* Powershell 5+
* Admin rights
Works for Windows 10 (build 1703 or later)

## Install

### Quick Version

1. Clone the repo or download archive from [releases](https://github.com/Garfield1002/redditPic/releases)
2. Execute in an elevated instance of `Windows PowerShell`:

```powershell
.\installer.ps1
```

Then follow instructions.

### Detailed Installation Guide

If you have never used `PowerShell`, this is for you.
In the `Search Bar`, type in `PowerShell` and click on `Run As Administrator`.

Once in `PowerShell`, run `Set-Location "C:\Users\ ...\Downloads\reddit pics"` the path to your download

Now run `.\installer.ps1`

From there on, simply follow instructions.

## Usage

You can run the utility at any given time to try and find a new background.

In `Windows PowerShell`:

```powershell
RedditLockscreen [-help] [-install] [-showpic] [-showlog] [-config] [-uninstall] [[-subreddit] [-sort] [-nsfw]]
```

In `Command Prompt`:

```bat
powershell RedditLockscreen [-help] [-install] [-showpic] [-showlog] [-config] [-list] [-add] [-remove] [-uninstall] [[-subreddit] [-sort] [-nsfw]]
```

Naturally, both need admin rights.

Use `RedditLockscreen -help` for help.

### Paramaters

#### `-help`

Displays Help on the usage of the `RedditLockscreen` script.

#### `-install`

Installs the `RedditLockscreen` script, will automatically add the script to `Task Scheduler`. The script will be called every time the user logs on.

#### `-showpic`

Dislays the current lockscreen if it was generated by `RedditLockscreen`.

#### `-showlog`

Displays the logfile, it contains the download date, author, subreddit and link of every downloaded lockscreen.

#### `-config`

Opens the `config.json` file. This file can be manually modified, values of `nsfw` and `sort` can only be changed this way.

#### `-list`

Lists the current subreddits from which lockscreens will be downloaded.

#### `-add`

Adds one or several subreddits to the config file.

#### `-remove`

Removes one or several subreddits from the config file.

#### `-uninstall`

Uninstalls the script, see [Uninstall](#Uninstall) for more details.

#### `-subreddit`

Specifies which subreddits will be used during a single execution of `RedditLockscreen`.
Default will use values set in config.
Example usage:

```powershell
RedditLockscreen -subreddit wallpaper
```

```powershell
RedditLockscreen -subreddit ("wallpaper", "cute")
```

#### `-sort`

Specifies how reddit will sort results during a single execution of `RedditLockscreen`.
Accepted values are: `new` and `hot`.
Default will use value set in config.

```powershell
RedditLockscreen -sort new
```

#### `-nsfw`

Specifies that nsfw content can be used during a single execution of `RedditLockscreen`.
Default will use value set in config.

```powershell
RedditLockscreen -nsfw
```

## Uninstall

Run `RedditLockscreen -uninstall`

You will be asked to manually delete the module folder.
