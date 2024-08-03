l7-dmenu-desktop:
- looks for .desktop files in ~/.local/share/applications/; /usr/share/applications/;
  /var/lib/flatpak/exports/share/applications/; ~/.local/flatpak/exports/share/applications/
    - will build cache on first run (takes about one second on my system with 450 .desktop files)
    - after initial caching will update on change (faster)
- includes aliases from ~/.config/l7-dmenu-desktop/aliases
    - syntax: alias \<name\>=\<command/name\>
    - if you want to point the alias to an app from a desktop file add "; desktop" after the name
- removes entries specified in ~/.config/l7-dmenu-desktop/excludes
    - write one exclude per line
- to include regular binaries from PATH add "addpath=1" to ~/.config/l7-dmenu-desktop/config
  or use the flag --addpath (requires stest (from dmenu))
- to change menu that is used use --dmenu=\<menu\>
    - if using default menu (not --dmenu=), arguments will be passed to it
- write *\<command\> into the menu to directly run it with bash
- write ~\<command\> to launch it in your terminal
- to clear the cache use --clean
- if you are not using alacritty change the terminal by adding term=\<terminal\>
  to ~/.config/l7-dmenu-desktop/config or using the flag --term=
- to hide desktop entries add "hidedesktop=1" to ~/.config/l7-dmenu-desktop/config
  or use the flag --hidedesktop
- use --benchmark to leave the menu command empty (eg. to measure the time)
- to change the default menu command "menu=\<menu\>" to ~/.config/l7-dmenu-desktop/config

**Important**
- commands that need to be available:
    - dmenu (if no other similar menu specified)
        - stest (for path items)
    - alacritty (if no other terminal emulator specified)
    - notify-send (optional for notifications)
    - bash :)
    - sed
    - grep
    - awk
    - find
    - sort
    - cat
    - touch
    - rm
    - comm
    - wc
