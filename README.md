# cmk-get
My personal installer program based on deb-get.  Used for zips and tars or other non-deb applications.  This will also use several one off functions to install special case software (like g910-keys)

Will be used to install and update non-deb / non-flatpak programs.
This is currently only for ubuntu systems.

### assumptions
- uses sudo (not doas or as SU [root])  * may change as I learn more about doas
- ubuntu base system (so Ubuntu or UMate, UBudgie, etc)
  - because of this, I don't care about arch as I'm only install on intel/amd cpu's
  - nor do I care about releases,  versions, or the ID of the OS
- some installs will be coded to specific folder structures I use so other people using may require some additional tweaks

## Usage

Here's an example of how to install Bitwarden CLI.

```bash
cmk-get install bw-cli
```

You can see what applications are supported by using `cmk-get list`.

You can upgrade packages installed using `cmk-get` by running
`cmk-get upgrade`.

<!-- [[[cog
import subprocess

import cog
result = subprocess.check_output(["./cmk-get", "help"], encoding="utf-8")
# strip the "Usage" header
help = result.replace("Usage\n\n", "").rstrip()
cog.out(f"```\n{help}\n```")
]]] -->
```

cmk-get {update | upgrade | show pkg | install pkg | remove pkg  | cache 
        | clean | list | fancy | comma | help | version}

cmk-get provides a high-level commandline interface to easily install and update packages
published in 3rd party github/gitlab releases, or other sites via direct download.

update
    update checks installed cmk-get apps for newer versions (all installed apps).

upgrade
    upgrade will update any cmk-get apps that have newer versions (all installed apps with updates).

install
    install is followed by one app desired for installation or upgrading.

remove
    remove is identical to install except apps are removed instead of installed.

clean
    clean clears out the local repository (/var/cache/cmk-get) of retrieved app files.

show
    show is followed by one app and shows information about the given app including its install source and update mechanism.

list
    list the apps available via cmk-get.

fancy
    markdown formatted list of apps available via cmk-get.

comma
    CSV formatted list of apps available via cmk-get.

cache
    list the contents of the cmk-get cache (/var/cache/cmk-get)

help
    shows this help

version
    show cmk-get version
```
<!-- [[[end]]] -->


<!-- [[[cog
pretty_list = subprocess.check_output(["./cmk-get", "fancy"], encoding="utf-8")
cog.out(pretty_list)
]]] -->
| Source   | Install Name   | Application Name   | Description   |
| :------: | :------------: | :----------------: | :-----------: |
| [<img src=".icons/icon-trowel.svg" align="top" width="20" style="background-color:white;padding:20px;" />](https://github.com/aristocratos/btop) | `btop` | <b>btop++</b> | <i>Resource monitor that shows usage and stats for processor, memory, disks, network and processes.  Written in C++</i> |
| [<img src=".icons/icon-zipper.svg" align="top" width="20" style="background-color:white;padding:20px;" />](https://www.bitwarden.com) | `bw-cli` | <b>Bitwarden CLI</b> | <i>A command line version of the Bitwarden Password Manager client.</i> |
| [<img src=".icons/icon-github.svg" align="top" width="20" style="background-color:white;padding:20px;" />](https://github.com/JSubelj/g910-gkey-macro-support) | `g910-gkeys` | <b>Logitech G910 Key Mapper</b> | <i>Linux keyboard mapper for Logitech G910 G-Keys.</i> |
| [<img src=".icons/icon-zipper.svg" align="top" width="20" style="background-color:white;padding:20px;" />]() | `nerd-fonts` | <b>Nerd Fonts</b> | <i></i> |
| [<img src=".icons/icon-zipper.svg" align="top" width="20" style="background-color:white;padding:20px;" />](https://www.pling.com/p/1305251/) | `sweet-dark` | <b>Candy Icons</b> | <i>A Candy neon-istic icon theme.</i> |
| [<img src=".icons/icon-github.svg" align="top" width="20" style="background-color:white;padding:20px;" />](https://www.opendesktop.org/p/1284047) | `sweet-folder` | <b>Sweet Folders - Purple</b> | <i>Folder icons for the Sweet GTK theme.</i> |
<!-- [[[end]]] -->
