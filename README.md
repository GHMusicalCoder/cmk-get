# cmk-get
My personal installer program based on deb-get.  Used for zips and tars or other non-deb applications.  
Will be used to install and update non-deb / non-flatpak programs.
This is currently only for ubuntu systems.

### current programs 
- bw-cli (Bitwarden CLI program from GitHub)
- btop++ (Github make)
- g910-keys (Logitech g910 Keyboard extra GKeys mapper)
- sweet dark theme
- candy icons
- sweet folders
- nerd fonts

### assumptions
- uses sudo (not doas or as SU [root])
- ubuntu base system (so Ubuntu or UMate, UBudgie, etc)
  - because of this, I don't care about arch as I'm only install on intel/amd cpu's
  - nor do I care about releases,  versions, or the ID of the OS

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
    update is used to resynchronize the app index files from their sources.

upgrade
    upgrade is used to install the newest versions of all apps currently installed on the system.

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
| [<img src=".icons/icon-zipper.svc" align="top" width="20" style="background-color:white" />]() | `btop` | <b>btop++</b> | <i></i> |
| [<img src=".icons/icon-zipper.svc" align="top" width="20" style="background-color:white" />]() | `bw-cli` | <b>Bitwarden CLI</b> | <i></i> |
| [<img src=".icons/icon-zipper.svc" align="top" width="20" style="background-color:white" />]() | `candy-icons` | <b>Candy Icons by Elivira</b> | <i></i> |
| [<img src=".icons/icon-github.svc" align="top" width="20" style="background-color:white" />]() | `g910-keys` | <b>Logitech G910 Key Mapper</b> | <i></i> |
| [<img src=".icons/icon-zipper.svc" align="top" width="20" style="background-color:white" />]() | `nerd-fonts` | <b>Nerd Fonts</b> | <i></i> |
| [<img src=".icons/icon-zipper.svc" align="top" width="20" style="background-color:white" />]() | `sweet-dark-theme` | <b>Sweet Dark Theme by Elivira</b> | <i></i> |
| [<img src=".icons/icon-zipper.svc" align="top" width="20" style="background-color:white" />]() | `sweet-folder` | <b>Sweet Purple Folders by Elivira</b> | <i></i> |
<!-- [[[end]]] -->
