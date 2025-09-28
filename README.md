### dmenu-desktop-bash:

- looks for .desktop files in ~/.local/share/applications/; /usr/share/applications/;
  /var/lib/flatpak/exports/share/applications/; ~/.local/share/flatpak/exports/share/applications/
    - will build cache on first run
        - takes about 300 ms on my system (i5-12400) with 500 .desktop files
    - after initial caching will update on change (faster)
- includes aliases from ~/.config/dmenu-desktop-bash/aliases
    - syntax: alias \<name\>=\<command/name\>
    - if you want to point the alias to an app from a desktop file add "; desktop" after the name
- removes entries specified in ~/.config/dmenu-desktop-bash/excludes
    - write one exclude per line
- to include regular binaries from PATH add "addpath=1" to ~/.config/dmenu-desktop-bash/config
  or use the flag --addpath (requires stest (from dmenu))
- to change menu that is used use --dmenu=\<menu\>
    - if using default menu (not --dmenu=), arguments will be passed to it
- write \*\<command\> into the menu to directly run it with bash
- write ~\<command\> to launch it in your terminal
- to clear the cache use --clean
- if you are not using alacritty change the terminal by adding term=\<terminal\>
  to ~/.config/dmenu-desktop-bash/config or using the flag --term=
- to hide desktop entries add "hidedesktop=1" to ~/.config/dmenu-desktop-bash/config
  or use the flag --hidedesktop
- use --benchmark to leave the menu command empty (eg. to measure the time)
- to change the default menu command "menu=\<menu\>" to ~/.config/dmenu-desktop-bash/config

### Dependencies:

- dmenu (if no other similar menu specified)
    - stest (for path items)
- alacritty (if no other terminal emulator specified)
- notify-send (optional for notifications)
- bash :)
- grep
- find
- coreutils
