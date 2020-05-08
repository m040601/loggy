vim: ft=markdown

HELPDESK
====


r only cli
----

https://wiki.archlinux.org/index.php/R#Installation
    install.packages() requires tk to be installed for selecting mirrors. Try installing this package if you see:

Error: .onLoad failed in loadNamespace() for 'tcltk', details (...)

    Alternatively, you can disable graphical pop-ups like this by running [2]:

> options(menu.graphics=FALSE)

to make this change more permanent add the above line to your Rprofile.

Within your R session, run this c


MICROTOPICS
====


mpd
-----

### metadata_to_use “+comment”

takes some time to rebuild the database

Use only the specified tags, and ignore the others. This setting can reduce the database size and MPD’s memory usage by omitting unused tags. By default, all tags but comment are enabled. The special value “none” disables all tags.

If the setting starts with + or -, then the following tags will be added or remoted to/from the current set of tags. This example just enables the “comment” tag without disabling all the other supported tags

    metadata_to_use “+comment”

Section Tags contains a list of supported tags.
### per directory dot mpdignore files 
User’s Manual — Music Player Daemon 0.22 documentation (https://www.musicpd.org/doc/html/user.html#the-music-directory-and-the-database)
NEWTOOLS
===

METABEST
=====

knitractive: A knitr engine to simulate interactive sessions
-----

[datascienceworkshops/knitractive: A knitr engine to simulate interactive sessions](https://github.com/datascienceworkshops/knitractive)
again git bare
-----

git clone --bare https://github.com/zserge/dotfiles $HOME/.dotfiles && git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME checkout


METABESTBEST
====

METAFUCK
====

METAFUCKFUCK
=====


mpc the file of currently playing to somewhere
----


cp "/var/lib/mpd/music/`mpc --format '%file%' | head -n1`" /some/where/else

ROLLING
====


