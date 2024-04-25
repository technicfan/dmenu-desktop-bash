l7-dmenu-desktop:
- put scripts in your PATH
- looks for .desktop files in ~/.local/share/applications/; /usr/share/;
  /var/lib/flatpak/exports/share/applications/; ~/.local/flatpak/exports/share/applications/
    - will build cache on first run (takes about 2 seconds on my system with 450 .desktop files)
    - after initial caching will update on change (fast)
- includes aliases from ~/.config/l7-dmenu-desktop/aliases
    - syntax: alias <name>=<command>
- removes entries specified in ~/.config/l7-dmenu-desktop/excludes
    - write one exclude per line
- you need to install "dex"
- to include regular binaries from PATH create ~/.config/l7-dmenu-desktop/addpath
- to change menu that is used use --dmenu=<menu>
    - if using dmenu (not --dmenu=), arguments will be passed to it
