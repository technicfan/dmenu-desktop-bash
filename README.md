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
- to change menu that is used use --dmenu=\<menu\>
    - if using default menu (not --dmenu=), arguments will be passed to it
- instead of your desired prompt write \~prompt\~ without quotation marks
- to change the default prompts add variables to ~/.config/l7-dmenu-desktop/config:
    * prompt1=\<first prompt (the one you see on launch)\>
    * prompt2=\<second prompt (the confirmation on launching a program that is not on the list)\>
        - use \~command\~ to insert the command that is asked to be run
- write ~\<command\> into the menu to directly run it with bash
- to clear the cache use --clean
- if you are not using alacritty change the terminal by adding term=\<terminal\>
  to ~/.config/l7-dmenu-desktop/config
- to hide desktop entries add "hidedesktop=1" to ~/.config/l7-dmenu-desktop/config
- use --benchmark to leave the menu command empty (eg. to measure the time)
- to change the default menu command "menu=\<menu\>" without arguments to ~/.config/l7-dmenu-desktop/config

**Important**
- commands that need to be available:
    - dmenu (if no other similar menu specified)
        - dmenu_path & stest (for path items)
    - alacritty (if no other terminal emulator specified)
    - notify-send (optional for notifications)
    - bash :)
    - echo
    - sed
    - grep
    - awk
    - find
    - sort
    - printf
    - touch
    - rm
    - diff
    - wc
