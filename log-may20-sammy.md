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




mpv
-----

I can't see the window when mpv plays audio files.
Use --force-window.

Run mpv in input test mode:
mpv --input-test --force-window --idle

mpv --ytdl-format [format code] https://www.youtube.com/watch?v=SYM-RJwSGQ8
You can mix different video+audio:
For mp4 1080p video (3770k) and webm audio (149k, opus @160k):
mpv --ytdl-format 137+251 https://www.youtube.com/watch?v=SYM-RJwSGQ8

if you always want to use the best video stream but only up to 1440p -
and falling back to the best single-file format when not playing DASH
streams 
ytdl-format=bestvideo[height<=?1440]+bestaudio/best



--ytdl-format=<ytdl|best|worst|mp4|webm|...>
Video format/quality that is directly passed to youtube-dl. The possible
values are specific to the website and the video, for a given url the
available formats can be found with the command youtube-dl
--list-formats URL
(Default: bestvideo+bestaudio/best)
The ytdl value does not pass a --format option to youtube-dl at all, and
thus does not override its default. Note that sometimes youtube-dl
returns a format that mpv cannot use, and in these cases the mpv default
may work better.




alsa cards devices
-----

aplay -l

https://superuser.com/questions/53957/what-do-alsa-devices-like-hw0-0-mean-how-do-i-figure-out-which-to-use
https://www.alsa-project.org/main/index.php/Asoundrc#The_naming_of_PCM_devices
https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture

What do ALSA devices like “hw:0,0” mean? How do I figure out which to use?

JohnT's answer gives a good basic. I'll follow it up with how to find
the devices on your system. Use "aplay -l" to get a list of the devices
on your system. The hw:X,Y comes from this mapping of your hardware --
in this case, X is the card number, while Y is the device number. .
<F11>o


The complex way, if you're not doing this with a desktop system, gets
... interesting. You might be able to get away with using device aliases
instead of the "hw:X,Y" -- this is what the output of "aplay -L" shows.
The "something:CARD=FOO,DEV=Y" stuff is the alias, and probably won't
change between different device plug-ins, where the X in "hw:X,Y" might.
(Assuming that you're using the same USB dongle each time.).

If you need something more stable at an even lower level, actual kernel
devices, udev is what you want -- it's the system that allows for
hotplugging devices into the system. You can write rules for udev (and
here's the man page) that will allow devices to get the same devicename
when plugged in..



hw:0,0 specifies the default device, on the default sound card. To access your second soundcard's first device, you would specify hw:1,0. These are specified in your .asoundrc. More on all of this here.



fuck pdftotext - chinese - Syntax Error (305): No font in show/space - unknown font tag tt2
----

install poppler-data

MORERSS
====

diy opensource low tech [OpenSourceLowTech - YouTube](https://www.youtube.com/user/SolarflowerOrg/videos)
NEWSBOAT
=====


exec: in urls with sed
----

Can't use `sed` in urls file · Issue #926 · newsboat/newsboat (https://github.com/newsboat/newsboat/issues/926)

> `"exec:curl --silent https://feeds.metaebene.me/raumzeit/m4a | sed 's#\(</guid>\|</id>\)#-M4A&#'" "~Raumzeit [M4A]"`


[Add a way to migrate feeds from one db to other db · Issue #985 · newsboat/newsboat](https://github.com/newsboat/newsboat/issues/985)
-----

fuck sn't cleanup-on-quit the option you're looking for? Suppose you want to split a feed with URL https://example.com/news.atom to a separate urlfile/databasefile pair:

    Copy your existing database file to a new location.
    Create a new url file and put "https://example.com/news.atom" into it.
    cleanup-on-quit is enabled by default, so no need to create a new config -- an empty one will do.
    Run newsboat on your new database, url file, and empty config: newsboat --config-file=/dev/null --cache-file=path/to/new/database --url-file=path/to/new/urls.
    Quit Newsboat and wait for it to remove all the feeds except https://example.com/news.atom.

Does that suit you




more example queries jun20
----

https://github.com/Jorengarenar/dotfiles/blob/master/newsboat/queries
PANDOC
=====

xclip and pandoc html
----

xclip -t text/html -o | pandoc -f html -t markdown


Filtering out messy HTML

From this answer:

:!%pandoc -f html -t markdown-raw_html-native_divs-native_spans

Or more fully:

:new
:r !xclip -sel clip -o -t text/html
:!%pandoc -f html -t markdown-raw_html-native_divs-native_spans --wrap=none

MUTT
====


different sender
----
 Dariusz Fedejko <mailing at fedejko.net> [2018-03-28 10:03]:
> Also, when I go inside a folder which belongs
> to another account and compose a message, the
> "from:" field changes accordingly - is that doable?

yes.

consider:

folder-hook .   "source ~/.mutt/persona.default"
folder-hook FOO "source ~/.mutt/persona.foo"

~/.mutt/persona.default:
    set from=default at domain.tld

~/.mutt/persona.foo"
    set from=special at domain.tld

so, for all folder which conrain ".",
ie some arbitrary character, neomutt
will source the "persona.default"
file which sets "default at domain.tld"
as your sender address.

and when you enter a folder FOO
then it sources the "persona.foo" file
which sets special at domain.tld
as your sender address.

of course you can change any other option
within those sourced files, eg realname.

easy enough?

Sven

MICROTOPICS
====


readability
-----


### fox [enrico-kaack/markdown-clipper: A Firefox and Google Chrome extension to clip websites and download them into a readable markdown file.](https://github.com/enrico-kaack/markdown-clipper)

This is a Firefox and Google Chrome extension to clip websites and download them into a readable markdown file.

It uses the following two libraries:

Readability.js by Mozilla in version from commit 977be42d1fb33781401001318813ab9fe4568647. This library is also used for the Firefox Reader View and it simplifies the page so that only the important parts are clipped. (Licensed under Apache License Version 2.0)
Turndown by Dom Christie in version 5.0.1 is used to convert the simplified HTML (from Readability.js) into markdown. (Licensed under MIT License)

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
BROWSER
=====


metabest https://github.com/enrico-kaack/markdown-clipper
----
This is a Firefox and Google Chrome extension to clip websites and download them into a readable markdown file.

It uses the following two libraries:

Readability.js by Mozilla in version from commit 977be42d1fb33781401001318813ab9fe4568647. This library is also used for the Firefox Reader View and it simplifies the page so that only the important parts are clipped. (Licensed under Apache License Version 2.0)
Turndown by Dom Christie in version 5.0.1 is used to convert the simplified HTML (from Readability.js) into markdown. (Licensed under MIT License)
Installation
The


NEWTOOLS
===


nethogs and nettop or jnetop (the setup)
----



metabest community/grc 1.11.3-1 [installed] python Yet another colouriser for beautifying your logfiles or output of commands
---
    Yet another colouriser for beautifying your logfiles or output of commands



Being overflooded with different logfile colo(u)?ri(s|z)ers, colortails, gccolors, colormakes and similar programs for making text files or outputs of different programs more readable by inserting ansi colour control codes into them, I decided to write my very own colouriser, eventually providing the functions of all those others.

Two programs are provided: grc and grcat. The main is grcat, which acts
as a filter, i.e. taking standard input, colourising it and writing to
standard output..




METABEST
=====

knitractive: A knitr engine to simulate interactive sessions
-----

[datascienceworkshops/knitractive: A knitr engine to simulate interactive sessions](https://github.com/datascienceworkshops/knitractive)
again git bare
-----

git clone --bare https://github.com/zserge/dotfiles $HOME/.dotfiles && git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME checkout



METABESTBEST very polished - same guy pandoc url cite -  rga ripgrep all - creates a cached version of the indexed text files (audio metadata tags pdf ebook zip tar etc)
----
[rga: ripgrep, but also search in PDFs, E-Books, Office documents, zip, tar.gz, etc. - phiresky's blog](https://phiresky.github.io/blog/2019/rga--ripgrep-for-zip-targz-docx-odt-epub-jpg/)

uses 'adapters' pandoc , ffmpeg etc


### METABESTBEST original idea, poorman's pdftotext cache with hashes stat and awk
[pdftotext-cached.sh](https://gist.github.com/phiresky/5025490526ba70663ab3b8af6c40a8db)
	#!/bin/bash

	fname="$1"

	cachedir=/tmp/pdfextract
	mkdir -p "$cachedir"

	mtime="$(stat -c %Y "$1")"

	hash=$(echo $fname.$mtime | sha256sum |  cut -c1-64)

	echo $hash $fname $mtime

	cachefname="$cachedir/$hash.txt"
	if [[ ! -f "$cachefname" ]]; then
		pdftotext -layout "$fname" - |
			# add "Page X: " prefix to each line
			awk 'BEGIN {page=1} /\f/{page+=1}; { sub(/\f/, ""); print "Page " page ":", $0}' > "$cachefname"
	fi

	exec cat "$cachefname"

METABESTBEST
====



stats always on mpv terminal
----

https://github.com/mpv-player/mpv/issues/5907

-- ~/.config/mpv/scripts/stats-on-no-video.lua
if mp.get_property('vid') == 'no' then
	mp.register_event('file-loaded', function()
		mp.command('script-binding stats/display-stats-toggle') end)
end
fox [enrico-kaack/markdown-clipper: A Firefox and Google Chrome extension to clip websites and download them into a readable markdown file.](https://github.com/enrico-kaack/markdown-clipper)
----

This is a Firefox and Google Chrome extension to clip websites and download them into a readable markdown file.

It uses the following two libraries:

Readability.js by Mozilla in version from commit 977be42d1fb33781401001318813ab9fe4568647. This library is also used for the Firefox Reader View and it simplifies the page so that only the important parts are clipped. (Licensed under Apache License Version 2.0)
Turndown by Dom Christie in version 5.0.1 is used to convert the simplified HTML (from Readability.js) into markdown. (Licensed under MIT License)


METABESTBEST rga ripgrep all - creates a cached version of the indexed text files (audio metadata tags pdf ebook zip tar etc)
----
[rga: ripgrep, but also search in PDFs, E-Books, Office documents, zip, tar.gz, etc. - phiresky's blog](https://phiresky.github.io/blog/2019/rga--ripgrep-for-zip-targz-docx-odt-epub-jpg/)
METAFUCK
====

pandoc
-----

:w !pandoc -f markdown -t html | xclip -sel clip

Pandoc (https://issarice.com/pandoc)

> After composing the email in Vim, simply write the buffer directly
> into Pandoc, convert the markdown to HTML, and send that into the
> clipboard with xclip:.


pand


gtk-launch gio etc
----


gtk-launch <program>
gio open <file>


METAFUCKFUCK
=====


mpc the file of currently playing to somewhere
----


cp "/var/lib/mpd/music/`mpc --format '%file%' | head -n1`" /some/where/else

vim windo diffthis
-----

https://issarice.com/vim

:windo diffthis and then :windo diffoff when done

vim quick cleanup something on the clipboard with xclip
----

https://issarice.com/vim

Filtering span tags from Quora’s HTML, assuming the HTML is in its own buffer; modify as necessary for parts of a buffer:

" paste the raw HTML
:r !xclip -sel clip -t text/html -o
" remove span tags; may need to repeat with @: if these are nested
:%!pandoc -f html -t html -F ./despan.py
" finally convert to markdown; use gq for further formatting as
" necessary
:%!pandoc -f html -t markdown

Here despan.py is the following:

	#!/usr/bin/python3

	# modified from https://github.com/jgm/pandoc/issues/1893

	from pandocfilters import toJSONFilter, Str

	def despan(key, value, format, meta):
	    if key == 'Span':
		return value[1]

	if __name__ == "__main__":
	    toJSONFilter(despan)

	See also Filtering out messy HTML.




vim global toc
----

https://issarice.com/vim
To generate the headings in a new split window, do something like this:

:redir @a
:silent global/^#/print
:redir END
:vnew | put a
:g/^$/d

my version:

:redir @a
:silent global/^====/-1print
:redir END
:global/^INDEX/+1put a


Then save it in a file and :source it, or yank it and execute with @". You can also view the output at any time without putting it in a new window using :echo @a. For some reason, chaining the above commands like

:redir @a | silent global/^#/print | redir END

only captures the first line of output from the :global command. I think it’s because :global tries to use everything after it as the ex command it executes. Doing

:redir @a | silent global/^#/print \| redir END

seems to work.





freebinds may20
----

### refs

fuck man 3 readline

### TIL and keep it like that

- alt alt or esc esc is complete

### TIL and possible candidate tmux et al

dvorak first seat ? shift ? think first !

- alt backslash delete spaces and tabs




inputrc readlinet alt dot
-----


    Instead of Alt-. you can hit Esc and then .
    Alt-1 <let go of 1 but keep alt pressed and add> . or just Esc, then 1, then . to gets the first argument (like !:1). You can use any number, of course, to reach any argument.

    permalinkembedsaveparent
THESETUP
=====

lesspipe now on github
----
even has a wiki, [wofr06/lesspipe: lesspipe (formerly on sourceforge)](https://github.com/wofr06/lesspipe)
https://github.com/wofr06/lesspipe/wiki
[wofr06/lesspipe: lesspipe (formerly on sourceforge)](https://github.com/wofr06/lesspipe)
ROLLING
====


manjaro-arm · GitLab (https://gitlab.manjaro.org/manjaro-arm)
----
https://osdn.net/projects/manjaro-arm/storage/rpi4/xfce/20.04/
Status of OpenGLES 2.0 with Panfrost/Lima - General Discussion - Manjaro Linux Forum (https://forum.manjaro.org/t/status-of-opengles-2-0-with-panfrost-lima/113591)


[Made a script to quickly get the text from the selected area using tesseract and maim : commandline](https://old.reddit.com/r/commandline/comments/guj6h0/made_a_script_to_quickly_get_the_text_from_the/)
----
https://github.com/sdushantha/bin/blob/master/utils/ocr
https://old.reddit.com/r/commandline/comments/guj6h0/made_a_script_to_quickly_get_the_text_from_the/


tig tack stack - telegraf influxdb grafana
-----
Quantifying Your life: Introduction to the TIG Stack :: Gideon Wolfe (https://www.gideonwolfe.com/posts/sysadmin/tig/intro/)
https://www.influxdata.com/time-series-platform/telegraf/

https://en.wikipedia.org/wiki/Grafana
https://en.wikipedia.org/wiki/Graphite_(software)
https://en.wikipedia.org/wiki/InfluxDB



more mail project - sync gmail tags
----


gauteh/lieer: Fast email-fetching and sending and two-way tag
synchronization between notmuch and GMail
(https://github.com/gauteh/lieer)

> This program can pull, and send, email and labels (and changes to
> labels) from your GMail account and store them locally in a maildir
> with the labels synchronized with a notmuch (https://notmuchmail.org/)
> database. The changes to tags in the notmuch database may be pushed
> back remotely to your GMail account.




extm3u m3u8 ietf specification
-----

https://en.wikipedia.org/wiki/M3U
https://tools.ietf.org/html/draft-pantos-http-live-streaming-08
https://tools.ietf.org/html/rfc8216



ffmpeg dumping m3u8
-----


https://stackoverflow.com/questions/49975527/choose-download-resolution-in-m3u8-list-with-ffmpeg

> I'm trying to download video from a m3u8 playlist using ffmpeg but I
> do not know how to choose the resolution to download. Currently the
> command is downloading the highest version

the command I am...


the command I am using is:

    /home/user/bin/ffmpeg -user_agent "Mozilla/5.0 (Windows NT 10.0; WOW64; rv:49.0) Gecko/20100101 Firefox/49.0" -i "https://sitevideo.com/list.m3u8" -c copy "/home/file/video.ts"
    

My list is this

    #EXTM3U
    #EXT-X-VERSION:3
    #EXT-X-STREAM-INF:BANDWIDTH=400000,NAME="low"
    size1.m3u8
    #EXT-X-STREAM-INF:BANDWIDTH=800000,NAME="med"
    size2.m3u8
    #EXT-X-STREAM-INF:BANDWIDTH=1900000,NAME="best"
    size3.m3u8

o

ou have to use the -map option.

ffmpeg ... -i "https://sitevideo.com/list.m3u8" -map p:1 -c copy "/home/file/video.ts"

p:1 refers to the 2nd program (variant playlist, in this case)..
o



If you don't put the map command it will take the best quality by default.



FFMPEG mp4 from http live streaming m3u8 file? aac adtstoasc
----


ffmpeg -i in.m3u8 -acodec copy -vcodec copy out.mp4

For AAC audio you will also need to add the the bit ststream filter. (Thanks @aergistal for pointing that out)

ffmpeg -i in.m3u8 -acodec copy -bsf:a aac_adtstoasc -vcodec copy out.mp4

- Stack Overflow (https://stackoverflow.com/questions/32528595/ffmpeg-mp4-from-http-live-streaming-m3u8-file)

> `ffmpeg -i http://.../playlist.m3u8 -c copy -bsf:a aac_adtstoasc output.mp4`



### 1 
FFmpeg Bitstream Filters Documentation (https://ffmpeg.org/ffmpeg-bitstream-filters.html#aac_005fadtstoasc)

> ### 2.1 aac_adtstoasc (https://ffmpeg.org/ffmpeg-bitstream-filters.html#toc-aac_005fadtstoasc)
> 
> Convert MPEG-2/4 AAC ADTS to an MPEG-4 Audio Specific Configuration bitstream.
> 
> This filter creates an MPEG-4 AudioSpecificConfig from an MPEG-2/4 ADTS header and removes the ADTS header.
> 
> This filter is required for example when copying an AAC stream from a raw ADTS AAC or an MPEG-TS container to MP4A-LATM, to an FLV file, or to MOV/MP4 files and related formats such as 3GP or M4A. Please note that it is auto-inserted for MP4A-LATM and MOV/MP4 and related formats.







### 2
video - Converting an HLS (m3u8) to MP4 - Stack Overflow (https://stackoverflow.com/questions/33108105/converting-an-hls-m3u8-to-mp4)

> `ffmpeg -i in.m3u8 -acodec copy -vcodec copy out.mp4`
> 
> For AAC audio you will also need to add the the bit ststream filter. (Thanks @aergistal for pointing that out)
> 
> `ffmpeg -i in.m3u8 -acodec copy -bsf:a aac_adtstoasc -vcodec copy out.mp4`





### 3
FFMPEG mp4 from http live streaming m3u8 file? - Stack Overflow (https://stackoverflow.com/questions/32528595/ffmpeg-mp4-from-http-live-streaming-m3u8-file)

> 171
> 
> Your command is completely incorrect. The output format is not `rawvideo` and you don't need the bitstream filter `h264_mp4toannexb` which is used when you want to convert the `h264` contained in an `mp4` to the `Annex B` format used by `MPEG-TS` for example. What you want to use instead is the `aac_adtstoasc` for the `AAC` streams.
> 
>     ffmpeg -i http://.../playlist.m3u8 -c copy -bsf:a aac_adtstoasc output.mp4




Aergistal's answer works, but I found that converting to mp4 can make some m3u8 videos broken. If you are stuck with this problem, try to convert them to mkv, and convert them to mp4 later.


.ts also works quiet well for some streams – Honza R Apr 3 '18 at 21:13

















### 4 best
m3u8 stream to mp4 using ffmpeg (https://gist.github.com/tzmartin/fb1f4a8e95ef5fb79596bd4719671b5d)

> trying to understand what the options mean
> 
>     ffmpeg -i "http://host/folder/file.m3u8" -bsf:a aac_adtstoasc -vcodec copy -c copy -crf 50 file.mp4
>     
> 
> ### `-bsf:a aac_adtstoasc`
> 
> - bsf = (bit stream filter)
> - use `aac_adtstoasc` bsf for `a` audio streams, this is need if `.m3u8` file consists with `.ts` files and output is `.mp4`
> - reference https://ffmpeg.org/ffmpeg-bitstream-filters.html#aac_005fadtstoasc (https://ffmpeg.org/ffmpeg-bitstream-filters.html#aac_005fadtstoasc)
> 
> ### `-c copy -vcodec copy`
> 
> - skip codec (encode and decode), just `demux` and `mux`
> - I guess `.ts` and `.mp4`, for video stream, they are both H.264 codec, just guess.
> - reference https://ffmpeg.org/ffmpeg.html#Stream-copy (https://ffmpeg.org/ffmpeg.html#Stream-copy)
> 
> ### `-crf 50`
> 
> - reference https://trac.ffmpeg.org/wiki/Encode/H.264#CRFExample (https://trac.ffmpeg.org/wiki/Encode/H.264#CRFExample)
> - the example shows `-c:a copy` did not re-encode, guess this option is not needed here.
> - And 0 is lossless, 23 is the default, and 51 is worst quality possible ![cry](https://github.githubassets.com/images/icons/emoji/unicode/1f622.png)


jun20:

 varenc commented 10 days ago •

@magicdawn, most of the ffmpeg options here don't do anything so it's particularly confusing trying to understand them.

In most all situations you just need this:
ffmpeg -i "http://host/folder/file.m3u" -c copy file.mp4

or

echo "Enter m3u8 link:";read link;echo "Enter output filename:";read filename;ffmpeg -i "$link"  -c copy $filename.mp4


to breakdown the original command...
-c copy -vcodec copy

is redundant. -c copy says "for all streams, do a stream copy" (no re-encoding). And then -vcodec copy says "for the video stream[s], do a stream copy". -c copy is all that's needed. You could also do -vcodec copy -acodec copy or -codec copy since -c is just a short version of -codec.
-crf 50

As you pointed out, since there's no transcoding going on, this video quality flag does nothing. And if it did work, 50 is such low quality that you probably wouldn't like the result. Also this flag is only supported by some codecs. (I wish ffmpeg gave you a warning when you pass in a useless flag!)
-bsf:a aac_adtstoasc

These days ffmpeg is smart enough to automatically insert this filter when needed. IMHO it's cleaner to just rely on that rather than always inserting it even when it's not necessary. (like in non-AAC+MPEG-TS streams) If you turn on verbose messaging with -v verbose you'll see that ffmpeg informs you of this:

$  ffmpeg -i https://...m3u8 -v verbose -c copy test.mp4
...
Automatically inserted bitstream filter 'aac_adtstoasc'; args=''

You can pull all this together and test things by downloading a stream with and without all these options and see that the resulting files are identical!

$ ffmpeg -i https://../stream.m3u8 -c copy test1.mp4
$ ffmpeg -i https://../stream.m3u8 -bsf:a aac_adtstoasc -vcodec copy -c copy -crf 50 test2.mp4
$ md5 test*.mp4
MD5 (test1.mp4) = 854e2beca4b3e516dd4cf147ca0521ee
MD5 (test2.mp4) = 854e2beca4b3e516dd4cf147ca0521ee

Another tip: if youtube-dl works but you want to control how ffmpeg downloads a stream without having to manually snoop for the .m3u8 file, just use youtube-dl's -g flag and it'll print out the m3u8 url and exit.
$ youtube-dl -g "https://host.com/some-webplay-video"

for example

$ youtube-dl -g https://www.pbs.org/video/east-bay-hip-hop-dance-in-richmond-ca-ng3v7e/
https://ga.video.cdn.pbs.org/videos/if-cities-could-dance/a7c8f330-2de4-4476-bb64-b23ae0bb2951/2000112404/hd-16x9-mezzanine-1080p/3f1sh5t6_richmond_iccd-16x9-1080p-1080p-6500k.m3u8

$ ffmpeg -i https://ga.video.cdn.pbs.org/videos/if-cities-could-dance/a7c8f330-2de4-4476-bb64-b23ae0bb2951/2000112404/hd-16x9-mezzanine-1080p/3f1sh5t6_richmond_iccd-16x9-1080p-1080p-6500k.m3u8 -c copy pbs-vid.mp4
;w
;w
