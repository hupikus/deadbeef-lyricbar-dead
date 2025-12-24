
# DeaDBeeF Lyricbar-dead Plugin
Plugin for [DeaDBeeF audio player](https://github.com/DeaDBeeF-Player/deadbeef) that fetches and shows the song’s synced lyrics from metadata or lrc/txt file (same name on same folder as track).

![GIF](https://github.com/AsVHEn/deadbeef-lyricbar/assets/4272271/2506a8cb-2c94-4a73-99c7-33b7aa22e26e)


## Fork
Fork is based on [AsVHEn's](https://github.com/AsVHEn/deadbeef-lyricbar); their fork is based on [loskutov's](https://github.com/loskutov/deadbeef-lyricbar)
This fork focuses solely on improving local sub display and improving stability. Any remote sub fetch that requires maintenance will be dropped in the fork.
Yet, don't expect much yet. If you need just to use the plugin, cosider the (source)[https://github.com/AsVHEn/deadbeef-lyricbar].

## Dependencies
To use this plugin, you need to have [gtkmm](http://www.gtkmm.org/) and [gtk3](https://www.gtk.org/) installed. (also: libcurl and libtag)

You need deadbeef.h file to build this plugin. The file /usr/include/deadbeef/deadbeef.h should've been installed with the player itself. If not -- look for deadbeef-plugin-dev package, or something like this. Or get the file from a source tarball.

## Installation
Just download compiled file _ddb_lyricbar_gtk3.so_, and copy it to ~/.local/lib/deadbeef or:

Clone this repository and perform the following:
```sh
make [gtk3]
sudo install
# OR, to install for the current user only
mkdir -p ~/.local/lib/deadbeef && cp *.so ~/.local/lib/deadbeef # depends on where deadbeef is installed
sudo cp ./gettext/[your language]/*.mo /usr/share/locale/[your language]/LC_MESSAGES/ 
```

## Usage
Activate Design Mode (View → Design mode) and add Lyricbar somewhere. Disable Design Mode back and edit appareance if you want in config options:

![Config](https://github.com/user-attachments/assets/8035a41f-dea5-4ea9-89cf-894ea4bfc30d)

## Development Status
The original plugin is discontinued for unknown time, as DeaDBeeF developers act agressively towards Russian-speaking users (see [the related commit](https://github.com/DeaDBeeF-Player/deadbeef/commit/d68495890fab7e3ac63674df72d8de82a592d78f)).
> Besides, I haven't been actively developing it lately anyways.
> Hopefully, the archived version of the plugin is usable enough, though.
- original plugin dev (loskutov)

Lyrics will be stored on tags "LYRICS" for synced, and "UNSYNCEDLYRICS" for non-sync. SYLT tags will be removed if exists (????).

Right now, working sites are:
- LRCLIB.
- RCLyricsBand.
- Megalobiz.
- Music 163.


There is also a window to edit lyrics.
![Edit](https://github.com/user-attachments/assets/f3aa7ac5-21c2-4b85-8568-6d4930162bbd)

> In addition, if you want to traslate to your language you only need copy deadbeef-lyricbar/gettext/deadbeef-lyricbar.pot (only spanish is available at the moment), rename to deadbeef-lyricbar.po, edit it and put /gettext/[your language]/ before compiling. Also if you're not satisfied with lyrics providers you can help adding another ones :D.
