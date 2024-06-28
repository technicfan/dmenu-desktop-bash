l7-dmenu-desktop:
- put scripts in your PATH
- looks for .desktop files in ~/.local/share/applications/; /usr/share/;
  /var/lib/flatpak/exports/share/applications/; ~/.local/flatpak/exports/share/applications/
    - will build cache on first run (takes about one second on my system with 450 .desktop files)
    - after initial caching will update on change (faster)
- includes aliases from ~/.config/l7-dmenu-desktop/aliases
    - syntax: alias \<name\>=\<command\>
- removes entries specified in ~/.config/l7-dmenu-desktop/excludes
    - write one exclude per line
- to include regular binaries from PATH create ~/.config/l7-dmenu-desktop/addpath
- to change menu that is used use --dmenu=\<menu\>
    - if using dmenu (not --dmenu=), arguments will be passed to it
- instead of your desired prompt write ~prompt~ without ' or "
- for changing the default prompts create ~/.config/l7-dmenu-desktop/prompts:
    * first line = first prompt (the one you see on launch)
    * second line = second prompt (the confirmation on launching a program that is not on the list)
        - use ~command~ to insert the command that is asked to be run

**! Important !**
- dependencies (that where not installed on my ArcoLinux system):
    - dmenu (or other similar menu)
    - dex
    - parallel
    - awk
- if you are not using alacritty change the terminal manually in l7-dmenu-desktop (line 53)
- if you want to use less or more than 12 cores change it manually in dmenu_desktop (line 66)
