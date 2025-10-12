![MCServeMe banner logo](mcserveme-banner-logo.png)

## MCServeMe – the terminal based Minecraft Java server launcher

This is a text based yet easy to use server launcher for *nix systems. It has been tested on Linux so far, and chances are that it will run out of the box on macOS and *BSD.

The projects’s aim is to provide something like [Prism Launcher](https://prismlauncher.org/) but for servers. To that end MCServeMe allows keeping different versions of the Minecraft Java server around, possibly with individual settings. That comes in handy if you have older worlds that rely on a specific world generation, or you prefer to use an older client.

You can tweak a fair number of settings, however if you don't care much about that then simply getting a [Fabric](https://fabricmc.net/) enabled and moddable server up and running is a matter of firing up MCServeMe and hitting the Enter key a few times.

---

### Features

- Comfortably manage and run multiple server versions
- Global and per-server configuration
- Support for server-side Fabric mods
- Flexible server and world backups
- Kickstart mode (via `-k`/`--kickstart` command line switch): Downloads (if necessary) and runs the newest server without any user interaction
- Lightweight dependencies: `dialog`, `curl` and `jq`, plus a Java runtime for the servers

---

### Disclaimer

This is still **alpha software**. While I am zealous to write decent and portable code, this is a quite bulky script file and you may encounter bugs and glitches. In particular it has not yet been tested on macOS and other non-GNU systems  where the same commands may potentially behave differently. Therefore, just to be in safe waters, I encourage you to make regular backups of your worlds when using this software.

Furthermore I recommend using MCServeMe only for operating small-scale private servers at this time.

---

### Installation

MCServeMe comes as a single large shell script with a README and a license file plus a couple of desktop assets. You can simply launch the `mcserveme` script file and you are good to go. For added convenience there is an entry in the global options menu for installing the script to `~/.local/bin` where it is (likely) in the $PATH. You can also have a desktop icon and menu entry installed if the computer is running a GUI.

---

### Usage

Most of the user interface should be self-explaining even for non-technical folks. There is a main menu with some system information displayed at the top, a menu for the global settings, as well as different server lists. Selecting a server presents you with a number of related actions.

MCServeMe furthermore features a small number of command line parameters as well, which you can list using `mcserveme --help`.

---

### Frequently asked questions

**It seems that MCServeMe is sometimes “caching” something during startup, what is happening?**

MCServeMe regularly downloads a list of available server jars and other components from the Fabric website into a cache directory. The interval is every hour. To disable this feature and only update manually from the main menu start MCServeMe with the `-n`/`--no-auto-cache` parameter.

**A word is missing here and there in some of the dialogs. Are those spelling errors?**

Language proficiency is not the issue here (although English is not my first language). What happens is that `dialog` sometimes swallows a word in dialog captions when color codes are enabled. I am looking into a workaround.

**I think that the color scheme looks a bit plain.**

Don’t despair, MCServeMe features support for a custom `dialogrc`. First you need to tell `dialog` to create a file with color definitions and some general settings:

`dialog --create-rc ~/.config/MCServeMe/colors`

Then edit the `colors` file to your liking.

**Can I play the Minecraft betas with it? Or 1.0?**

Alas, the Fabric mod loader has not existed for that long. Hence the erliest snapshot you can play in MCServeMe is 18w43b and the earliest stable release is 1.14. I may add support for vanilla servers in the future if there is demand.

---

### Not yet implemented features

- Launching servers and selecting worlds directly from the command line
- Directory selection dialogs
- Downloading and managing of server optimization mods
- Editing the whitelist and ops list
- World and settings backups
- Multiple worlds per server
- Make a flatpak

---

### How to participate

If you would like to contribute you can help the project in several ways:

- Test the script on different platforms (Linux distros other than the Buntus; macOS, *BSD etc.). I am quite positive that it can run fine on most common Unices with only minor tweaks. It might even run on WSL, although I am not sure why someone would try that.
- Leave some feedback, constructive criticism or praise in the official Reddit thread or on my Discord server.
- Make a (blog/video) review or showcase to maybe get some people interested
- If you found glitches or bugs in MCServeMe, or have a feature request, please [open an issue](https://github.com/lortordermur/mcserveme/issues).
