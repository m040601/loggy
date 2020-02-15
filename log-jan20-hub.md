vim: ft=markdown

MORE RSS
====

https://openwrt.org/feed.php
https://www.youtube.com/channel/UCj4SLNED1DiNPHComZTCbzw rex krueger woodworikng for human approved

HELPDESK
=====

watch github wikis
-----
[How can you track or be notified of changes to GitHub wikis? - Stack Overflow](https://stackoverflow.com/questions/8407917/how-can-you-track-or-be-notified-of-changes-to-github-wikis)




long urls in urxvt (seems no fix)
----
wont fix ?
[url-select: selection of long urls · Issue #61 · muennich/urxvt-perls](https://github.com/muennich/urxvt-perls/issues/61)

 When urxvt wraps a line containing an url, url-select only catches the first line
 MAPS
 =====

METABEST [FOSDEM 2020 - Creating GPX tracks from cycle routes in OpenStreetMap](https://fosdem.org/2020/schedule/event/creating_gpx_tracks_from_cycle_routes_in_openstreetmap/)
----
> In this talk I will present an Open Source tool to download GPX tracks of
> cycle routes, and a website for people to download the generated GPX files. I
> will discuss some of the nuances of how cycle routes are stored as relations
> and what processing needs to be performed in order to create a continuous
> route. In addition, I will speak about how the tool can be used to identify
> inconsistencies in OpenStreetMap data.

[hpgmiskin/OpenCycleExport: Python tool to export OpenStreetMap cycle routes as GPX tracks](https://github.com/hpgmiskin/OpenCycleExport)

[FOSDEM 2020 - Frictionless Data for Reproducible Research]
---

(https://fosdem.org/2020/schedule/event/open_research_frictionless_data/)

> The Frictionless Data project is comprised of a set of specifications
> (https://frictionlessdata.io/specs/) for data and metadata interoperability,
> accompanied by a collection of open source software libraries
> (https://frictionlessdata.io/software/) that implement these specifications,
> and a range of best practices for data management. Over the past year and a
> half, we have been wo.

[Frictionless Data](https://github.com/frictionlessdata/)



METABEST rotate xrandr touchpad(xinput) and gestures
---

https://askubuntu.com/questions/978803/rotate-touchpad-when-screen-is-orientation-rotated
https://wiki.archlinux.org/index.php/Tablet_PC#Automatic_rotation


put the following in ~/bin after replacing eDP1 with the screen your touchpad
to follow. can get a list of your screens by running xrandr.

change --output eDP1 to -o if you want to rotate all screens.

you may need to play around with the code that gets the xinput id for your
touchpad.

make sure it is executable and also bin is in $PATH variable.

without stuff that doesn't pretain your question

	#!/bin/bash
	#inverted -> right -> normal -> left -> inverted
	status="$(xrandr -q|grep eDP1|awk '{print $3}')"
	if [ $status == 'primary' ]; then
	   state="$(xrandr -q|grep eDP1|awk '{print $5}')"
	else
	   state="$(xrandr -q|grep eDP1|awk '{print $4}')"
	fi
	touchpad=$(xinput | awk '/Touchpad/ {print $7}' | grep -oP [0-9]+) #


	case "${state}" in
	'inverted')
	  xrandr --output eDP1 --rotate right
	  xinput set-prop "$touchpad" --type=float "Coordinate Transformation Matrix" 0 1 0 -1 0 0 0 0 1
	  ;;
	'right')
	  xrandr --output eDP1 --rotate normal
	  xinput set-prop ${touchpad} --type=float "Coordinate Transformation Matrix" 1 0 0 0 1 0 0 0 1
	  ;;
	'(normal')
	  xrandr --output eDP1 --rotate left
	  xinput set-prop ${touchpad} --type=float "Coordinate Transformation Matrix" 0 -1 0 1 0 0 0 0 1
	  ;;
	'left')
	  xrandr --output eDP1 --rotate inverted
	  xinput set-prop ${touchpad} --type=float "Coordinate Transformation Matrix" -1 0 0 0 -1 0 0 0 1
	  ;;
	esac


I have it doing custom things as well

	#!/bin/bash
	#inverted -> right -> normal -> left -> inverted
	state="$(orientation)"
	#[ "${state}" == 'inverted' ] && xrandr --output eDP1 --rotate right || ([ "${state}" == 'right' ] && xrandr --output eDP1 --rotate normal || ([ "${state}" == 'left' ] && xrandr --output eDP1 --rotate inverted || xrandr --output eDP1 --rotate left));
	#sleep 2
	#xrandr-invert-colors;
	touchpad=$(xinput | awk '/Touchpad/ {print $7}' | grep -oP [0-9]+) #xinput list --id-only "ipts 1B96:005E Touchscreen"
	libinput_enabled=false
	gestures_enabled=true

	case "${state}" in
	'inverted')
	  xrandr --output eDP1 --rotate right
	  xinput set-prop "$touchpad" --type=float "Coordinate Transformation Matrix" 0 1 0 -1 0 0 0 0 1
	  if [ "$libinput_" = true ]; then
	    cp ~/.config/libinput-gestures.conf_right ~/.config/libinput-gestures.conf
	    libinput-gestures-setup restart
	  fi
	  ;;
	'right')
	  xrandr --output eDP1 --rotate normal
	  xinput set-prop ${touchpad} --type=float "Coordinate Transformation Matrix" 1 0 0 0 1 0 0 0 1
	  if [ "$libinput_" = true ]; then
	    cp ~/.config/libinput-gestures.conf_normal ~/.config/libinput-gestures.conf
	    libinput-gestures-setup restart
	  fi
	  ;;
	'(normal')
	  xrandr --output eDP1 --rotate left
	  xinput set-prop ${touchpad} --type=float "Coordinate Transformation Matrix" 0 -1 0 1 0 0 0 0 1
	  if [ "$libinput_" = true ]; then
	    cp ~/.config/libinput-gestures.conf_left ~/.config/libinput-gestures.conf
	    libinput-gestures-setup restart
	  fi
	  ;;
	'left')
	  xrandr --output eDP1 --rotate inverted
	  xinput set-prop ${touchpad} --type=float "Coordinate Transformation Matrix" -1 0 0 0 -1 0 0 0 1
	  if [ "$libinput_" = true ]; then
	    cp ~/.config/libinput-gestures.conf_inverted ~/.config/libinput-gestures.conf
	    libinput-gestures-setup restart
	  fi
	  ;;
	esac

	if [ "$gestures_enabled" = true ]; then
	   restartTouchpad;
	fi

MICROTOPICS
====

hugo jekyll
----


### habd.as - after dark hugo theme

> Pages on [habd.as](https://habd.as) are powered by
> [Hugo](https://gohugo.io) using the [After
> Dark](https://habd.as/code/after-dark/) theme. Most text is written
> and stored in a markdown-like format known as
> [CommonMark](https://commonmark.org) with embedded
> [shortcodes](https://after-dark.habd.as/shortcode/) to facilitate
> reuse of common interface elements such as an
> [alert](https://after-dark.habd.as/shortcode/alert/).

readability
-------


### mercury now open source ?
[postlight/mercury-parser: 📜 Extract meaningful content from the chaos of a web page](https://github.com/postlight/mercury-parser)

> [Postlight](https://postlight.com)'s Mercury Parser extracts the bits that humans care about from any URL you give it. That includes article content, titles, authors, published dates, excerpts, lead images, and more.
> 
> Mercury Parser powers the [Mercury AMP Converter](https://mercury.postlight.com/amp-converter/) and [Mercury Reader](https://mercury.postlight.com/reader/), a Chrome extension that removes ads and distractions, leaving only text and images for a beautiful reading view on any site.
> 
> Mercury Parser allows you to easily create custom parsers using simple JavaScript and CSS selectors. This allows you to proactively manage parsing and migration edge cases. There are [many examples available](https://github.com/postlight/mercury-parser/tree/master/src/extractors/custom) along with [documentation](https://github.com/postlight/mercury-parser/blob/master/src/extractors/custom/README.md).


[zyocum/reader: Extract clean(er), readable text from web pages via Mercury Web Parser.](https://github.com/zyocum/reader)

> The creators of the Mercury Web Parser initially offered it as a free
> service via a ReSTful API, but have since open sourced it. The API was
> shut down April 15, 2019. To continue using the parser, install its
> command-line driver using [`yarn`](https://github.com/yarnpkg/yarn) or
> [`npm`](https://github.com/npm/cli) package managers:




### pandoc epub from clean html from mercury

[How can I create a TOC based on input files? - Grupos do Google](https://groups.google.com/forum/#!topic/pandoc-discuss/SKotTwiXwCE)

	> I use mercury-parser to save web pages as clean HTML. I like to merge some of these pages into a single epub. I currently use this command:  
	> pandoc --toc -s *.html -o fruit2.epub  
	> But this creates an empty toc, as the files themselves don’t have whatever formatting hints pandoc uses to detect sections; I’d like to have a toc based on the input file themselves (each input file = a section). How do I go about achieving that?  
	> 
	> Mostrar conteúdo cortado


Sections are constructed based on heading elements. (h1, h2, etc.
in HTML.)

So, assuming your documents have h2s and not h1s, you'd need to
insert an h1 with the title of the chapter in front of each html
file.




MAPS
====

metabest blender gis
----
[domlysz/BlenderGIS: Blender addons to make the bridge between Blender and geographic data](https://github.com/domlysz/BlenderGIS)

geojson.io to geojson.net https
----
[mapbox/geojson.io: IMPORTANT: development of this project has been paused, see the README (fast, simple map creation)](https://github.com/mapbox/geojson.io)

> Note: development of geojson.io is currently paused. You may be
> interested in the new fork at
> [https://geojson.net](https://geojson.net). Until development
> restarts, please refrain from adding issues to the tracker..


Framacarte  - umap
----
[Framacarte](https://framacarte.org/en/)


cute umap hemicycle french parlament umap
----

https://umap.openstreetmap.fr/en/map/hemicycle-idf_70859#5/-34.615/20.962

METABEST geojson.io cli tools  semi-abandoned npm
----

[mapbox/geojson.io: IMPORTANT: development of this project has been paused, see the README (fast, simple map creation)](https://github.com/mapbox/geojson.io)

> ## Goes Great With!
> 
> **Tools**
> 
> -   [Using geojson.io with GitHub is better with the Chrome Extension](https://chrome.google.com/webstore/detail/geojsonio/oibjgofbhldcajfamjganpeacipebckp)
> -   [geojsonio-cli](https://github.com/mapbox/geojsonio-cli) lets you shoot geojson from your terminal to geojson.io! (with nodejs)
> -   [geojsonio.py](https://github.com/jwass/geojsonio.py) lets you shoot geojson from your terminal to geojson.io! (with python)
> -   [reproject](https://github.com/perliedman/reproject) reprojects geojson on the fly, and then you can pipe to geojson.io!

PANDOC
=====


barcode isbn qrcode
-----

[daamien/pandoc-latex-barcode: A pandoc filter to insert barcodes and QR codes in a latex/pdf document](https://github.com/daamien/pandoc-latex-barcode)

emphasize lines in code blocks
----

[pandoc-emphasize-code](https://owickstrom.github.io/pandoc-emphasize-code/)

> This filter lets you specify _ranges_ of a code block to emphasize,
> and have the filter generate the appropriate markup for you. It
> recognizes code blocks with the `emphasize` attribute present:.


owickstrom/pandoc-include-code: A Pandoc filter for including code from source files
------
(https://github.com/owickstrom/pandoc-include-code).


level up
----
[daamien/pandoc-latex-levelup: A pandoc filter to shift the level of all headers in a latex/pdf output](https://github.com/daamien/pandoc-latex-levelup)

typademic (python) service
----

[maehr/typademic: Typademic turns distraction freely written markdown files into beautiful PDFs.](https://github.com/maehr/typademic)

> ### Prerequisites
> 
> Install all this to use all functions of typademic.
> 
> -   [Google Fonts](https://github.com/google/fonts)
> -   [LaTeX](https://www.latex-project.org/get/)
> -   [Pandoc](http://pandoc.org/installing.html)
> -   [Pandoc Citeproc](https://github.com/jgm/pandoc-citeproc)
> -   [Python 3](https://www.python.org/downloads/)
> -   [OpenSSL](https://www.openssl.org/source/)
> 
> #### Mac with [Homebrew](https://brew.sh/index_de)
> 
> brew install python openssl mactex pandoc pandoc-citeproc wget


bookmanager yaml
----
[cyberaide/bookmanager](https://github.com/cyberaide/bookmanager)

> Bookmanager is a tool to create a publication from a number of sources
> on the internet. It is especially useful to create customized books,
> lecture notes, or handouts. Content is best integrated in markdown
> format as it is very fast to produce the output. At present we only
> produce ePubs, but it will be easy to also create pdf, html, work, odt
> and others. As we use pandoc we can support the formats supported by
> it..
KOBO
====

[MobileRead Wiki - Kobo Configuration Options]
----

(https://wiki.mobileread.com/wiki/Kobo_Configuration_Options)
pack images in a zip cbz
----
ust copy the files onto the device.  Each file will be listed as it's 
own 'book', (by filename for the title).  Of course, that will become 
hard to manage, so I would suggest putting all your pictures together 
into a zip file, rename the .zip to .cbz, that will become sort of an 
album.



It is a bit of an odd thing to do with an e-ink screen, since most 
people will have some kind of handheld colour device much better suited 
to viewing photos.
		
  
  
  
  
[How to Export Highlights/Annotations from Kobo eReaders
-----
https://medium.com/@angeldan1989/how-to-export-notes-highlights-annotations-from-kobo-ereaders-20606b7159b6)

> Then, add the following code to the file:  
> **_\[FeatureSettings\]  
> ExportHighlights=true_**

OPENWRT
====

netperf and openwrt scripts (a la speedtest)
---

[OpenWrtScripts/README.md at master · richb-hanover/OpenWrtScripts](https://github.com/richb-hanover/OpenWrtScripts/blob/master/README.md)

separate instance of the web server uhttpd for host a web and 
----

practice some HTTP and CSS and installed openssh-sftp-server for edit 
the files from my computer. I planninf to add some DBMS for do some kind
 of web app and practice DB, maybe for record my spends or i don't know.
Remember the Perl Extensions we copied before?
Now it’s the time to load them and make keybinds to call them.
M means meta, or in these modern days called Alt.
To copy some text in the terminal, mark them using mouse then hit Alt+C.
To paste it to URxvt, hit Alt+V.
But if you want to paste it on the other app, just use Ctrl+V normally.
That Perl Extension also contains other useful features.
Like select URL in terminal by pressing Alt+U, then use arrow keys if there are
more than one URL in current buffer. Then hit Enter to launch the selected URL in Firefox.
Hit Esc to exit selection mode.





Monitoring OpenWrt with collectd, InfluxDB and Grafana 
----
[Monitoring OpenWrt with collectd, InfluxDB and Grafana | Just another Linux geek](https://blog.christophersmart.com/2019/09/09/monitoring-openwrt-with-collectd-influxdb-and-grafana/)

BROWSER
====

metabestbest elinks conf (plugs lua) glacambre (tridacy dev ?)
------

[.dotfiles/default/.config at master · glacambre/.dotfiles](https://github.com/glacambre/.dotfiles/tree/master/default/.config)

tridactyl own readability
----


eoirtirt[Keybindings lost in Reader View · Issue #102 · tridactyl/tridactyl](https://github.com/tridactyl/tridactyl/issues/102)

> Would it be hard to implement a reader mode owned by tridactyl?








copy as markdown (tabs) chitsaou/copy-as-markdown
-----

[chitsaou/copy-as-markdown: Copying Link, Image and Tab(s) as Markdown Much Easier.](https://github.com/chitsaou/copy-as-markdown)



[chitsaou/copy-as-markdown: Copying Link, Image and Tab(s) as Markdown Much Easier.](https://github.com/chitsaou/copy-as-markdown)

> **Copy as Markdown** is a browser extension helps you copy the following things as Markdown to your system clipboard:
Current Tab as Link  
A Link in the Page  
An Image in the Page  
An Image that is wrapped with a Link  
All Tabs as a List of Links  
Highlighted Tabs as a List of Links
> 
> ## Keyboard Shortcuts
> 
> You can add keyboard shortuts for copying tab(s) as Markdown. By default, Copy as Markdown does not assign any keyboard shortcuts\\\\

buku To avoid title fetch from the web, add the `--title` option to the script.
----

[System integration · jarun/buku Wiki](https://github.com/jarun/buku/wiki/System-integration)

> To avoid title fetch from the web, add the `--title` option to the script.
> 
> To verify that the bookmark has indeed been added, run:


duckduckgo params 
----

[DuckDuckGo URL Parameters](https://start.duckduckgo.com/params)

[DuckDuckGo URL Parameters](https://start.duckduckgo.com/params)

> You can change [DuckDuckGo settings](https://start.duckduckgo.com/settings) via URL parameters by adding them after the search query, for example:
> 
>     https://duckduckgo.com/?q=search&kp=-1&kl=us-en


[DarkDuckGo | habd.as](https://habd.as/post/darkduckgo/)

> Combining all parameters results in the following otherwise unintelligible URL I use to search the Web more privately:
> 
> [3g2upl4pq6kufc4m.onion/?kp=-2&kn=1&kaf=1&kd=-1&kh=1&kg=p&k5=2&ko-1&kam=osm&kae=t&k1=-1&k7=2e3440](https://3g2upl4pq6kufc4m.onion/?kp=-2&kn=1&kaf=1&kd=-1&kh=1&kg=p&k5=2&ko-1&kam=osm&kae=t&k1=-1&k7=2e3440)
> 
> If you're not running Tor, you can still use the params using clearnet
> search by replacing the Onion domain name with
> [start.duckduckgo.com](https://start.duckduckgo.com). And that's how
> you DarkDuckGo..


firefox usercontent.css not userchrome.css black new page tab
---

This hack may not work if you've secured Firefox to bypass telemetry and
start directly from about:blank or about:newtab. In Linux Manjaro, for
instance, Firefox disregards the user styles unless opening a second
tab. To work around the WTOD showing when the browser starts see Hack
2..

[Burying Firefox's White Tab of Death | habd.as](https://habd.as/post/burying-firefox-white-tab-death/)


body:empty {
  background: black;
}


metabest Swift Selection Search (SSS) is a simple Firefox add-on 
----
[CanisLupus/swift-selection-search: Swift Selection Search (SSS) is a simple Firefox add-on that lets you quickly search for some text in a page using your favorite search engines.](https://github.com/CanisLupus/swift-selection-search)
NEOVIM
=====

metabest justinmk function for lynx in term
-----
[config/init.vim at master · justinmk/config](https://github.com/justinmk/config/blob/master/.config/nvim/init.vim)

> function! s:init_lynx() abort nnoremap <nowait><buffer> <C-F> i<PageDown><C-\\><C-N> tnoremap <nowait><buffer> <C-F> <PageDown> nnoremap <nowait><buffer> <C-B> i<PageUp><C-\\><C-N> tnoremap <nowait><buffer> <C-B> <PageUp> nnoremap <nowait><buffer> <C-D> i:DOWN_HALF<CR><C-\\><C-N> tnoremap <nowait><buffer> <C-D> :DOWN_HALF<CR> nnoremap <nowait><buffer> <C-U> i:UP_HALF<CR><C-\\><C-N> tnoremap <nowait><buffer> <C-U> :UP_HALF<CR> nnoremap <nowait><buffer> <C-N> i<Delete><C-\\><C-N> tnoremap <nowait><buffer> <C-N> <Delete> nnoremap <nowait><buffer> <C-P> i<Insert><C-\\><C-N> tnoremap <nowait><buffer> <C-P> <Insert> nnoremap <nowait><buffer> u i<Left><C-\\><C-N> nnoremap <nowait><buffer> <C-R> i<C-U><C-\\><C-N> nnoremap <nowait><buffer> <CR> i<CR><C-\\><C-N> nnoremap <nowait><buffer> gg i:HOME<CR><C-\\><C-N> nnoremap <nowait><buffer> G i:END<CR><C-\\><C-N> nnoremap <nowait><buffer> zl i:SHIFT_LEFT<CR><C-\\><C-N> nnoremap <nowait><buffer> zL i:SHIFT_LEFT<CR><C-\\><C-N> nnoremap <nowait><buffer> zr i:SHIFT_RIGHT<CR><C-\\><C-N> nnoremap <nowait><buffer> zR i:SHIFT_RIGHT<CR><C-\\><C-N> nnoremap <nowait><buffer> gh i:HELP<CR><C-\\><C-N> nnoremap <nowait><buffer> cow i:LINEWRAP_TOGGLE<CR><C-\\><C-N> tnoremap <buffer> <C-C> <C-G><C-\\><C-N> nnoremap <buffer> <C-C> i<C-G><C-\\><C-N> endfunction command! -nargs=1 Web vnew|call termopen('lynx -use_mouse '.shellescape(<q-args>))|call <SID>init_lynx() command! -nargs=1 Websearch vnew|call termopen('lynx -use_mouse https://duckduckgo.com/?q='.shellescape(substitute(<q-args>,'#','%23','g')))|call <SID>init_lynx() nnoremap gow :Start "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" --no-proxy-server "%:p"<cr> silent! source ~/.vimrc.local
      

      

justinmk dirvish keep netrw gx
-----
[config/init.vim at master · justinmk/config](https://github.com/justinmk/config/blob/master/.config/nvim/init.vim)

> " Disable netrw, but autoload it for \`gx\`. let g:loaded_netrwPlugin = 0 nmap gx <Plug>NetrwBrowseX nnoremap <silent> <Plug>NetrwBrowseX :call netrw#BrowseX(expand((exists("g:netrw_gx")? g:netrw_gx : '<cfile>')),netrw#CheckIfRemote())<CR>
      
        

metatop new plugin - fzf preview (float bling) - more blingy than fzf.vim
-----
https://old.reddit.com/r/neovim/comments/ezs67g/neovim_plugin_that_provides_fzf_preset_with/
[yuki-ycino/fzf-preview.vim: Plugin to handle fzf powerfully with neovim](https://github.com/yuki-ycino/fzf-preview.vim)

> fzf-preview is a Neovim plugin that provides a preset of commands using fzf.  
> Provides multiple resources and a preview command for it.
> 
> fzf-preview mainly uses neovim floating window. vim may work depending on the setting, but it is not recommended.
> 
> This plugin does not use [fzf.vim](https://github.com/junegunn/fzf.vim) but uses the library attached to fzf. Though it is different from this plugin and has a lot of functions, [fzf.vim](https://github.com/junegunn/fzf.vim) has no preview of the project's file list and grep on the interactive project.

SHELL
=====



tree a directroy and create and index.html
-----
	

"I'd love to see an extreeeemely minimal tool which lets you drop some files in a folder and then create an index page that links to those."

I use the tree command on BSD to do just that. It has the option of creating html output with a number of additional options.

An example: tree -P *.txt -FC -H http://baseHREF -T 'Your Title' -o index.html
THESETUP
====

metabest rofi eye candy galore rofi-menus-git
----

[vahnrr / rofi-menus · GitLab](https://gitlab.com/vahnrr/rofi-menus)

> The package is available in the Arch User Repository as [rofi-menus-git](https://aur.archlinux.org/packages/rofi-menus-git).
> 
>     yay -S rofi-menus-git
> 
> You can then call the menus with these commands:
> 
>     rofi-appsmenu
>     rofi-i3layout
>     rofi-mpd
>     rofi-network
>     rofi-power
>     rofi-scrot
>     rofi-vpn


metabestbest dmenu script youtube viewer invidio.us
-----
[Dmenu Hacking Thread (Page 14) / Programming & Scripting / Arch Linux Forums](https://bbs.archlinux.org/viewtopic.php?id=80145&p=14)

> With your advice and some code in this topics i came with a youtube viewer but  get videos from invidio.us :

bashrc mkcdd and bd
---
 change to parent directory matching partial string, eg:
 94 # in directory /home/foo/bar/baz, 'bd f' changes to /home/foo
 95 bd() {
 96   local old_dir=`pwd`
 97   local new_dir=`echo $old_dir | sed 's|\(.*/'$1'[^/]*/\).*|\1|'`
 98   index=`echo $new_dir | awk '{ print index($1,"/'$1'"); }'`
 99   if [ $index -eq 0 ] ; then
100     echo "No such occurrence."
101   else
102     echo $new_dir
103     cd "$new_dir"
104   fi

[Bash/Functions - ArchWiki](https://wiki.archlinux.org/index.php/Bash/Functions)

> her way to do this is to install a specialized package, see [Archiving and compression tools#Convenience tools](https://wiki.archlinux.org/index.php/Archiving_and_compression_tools#Convenience_tools "Archiving and compression tools").
> 
> cd and ls in one
> 
> Very often changing to a directory is followed by the `ls` command to list its contents. Therefore it is helpful to have a second function doing both at once. In this example we will name it `cl` (change list) and show an error message if the specified directory does not exist.
> 
> cl() {
> 	local dir="$1"
> 	local dir="${dir:=$HOME}"
> 	if \[\[ -d "$dir" \]\]; then
> 		cd "$dir" >/dev/null; ls
> 	else
> 		echo "bash: cl: $dir: Directory not found"
> 	fi
> }





free bash and console keys
----
busy stty setterm etc
stty -a

busy bash
bind -psvX

busy keys stty outside bash (CDOQRSUVWZ \ ? )
----
stty -a

Q/S "hides and continues" input
c-o is kind of c-d without logout

intr = ^C
quit = ^\
erase = ^?
kill = ^U
eof = ^D
eol = <undef>
eol2 = <undef>
swtch = <undef>
start = ^Q
stop = ^S
susp = ^Z
rprnt = ^R
werase = ^W
lnext = ^V
discard = ^O

console screensaver and etc issue
-----

/usr/share/doc/arch-wiki/html/en/Display_Power_Management_Signaling.html

 * 4 DPMS interaction in a Linux console with setterm
   + 4.1 Prevent screen from turning off
   + 4.2 Pipe the output to a cat to see the escapes
   + 4.3 Pipe the escapes to any tty (with write/append perms) to modify that
    terminal


DPMS interaction in a Linux console with setterm

The setterm utility issues terminal recognized escape codes to alter the
terminal. Essentially it just writes/echos the terminal sequences to the
current terminal device, whether that be in screen, a remote ssh terminal,
console mode, serial consoles, etc.

setterm Syntax: (0 disables)

setterm -blank [0-60|force|poke]
setterm -powersave [on|vsync|hsync|powerdown|off]
setterm -powerdown [0-60]


Prevent screen from turning off
	$ setterm -blank 0 -powerdown 0
Alternatively 
	# echo -ne "\033[9;0]" >> /etc/issue
Changing 0 (after the semicolon) to e.g. 3, will keep the screen on for
minutes, before entering standby mode.

Pipe the output to a cat to see the escapes
	$ setterm -powerdown 2>&1 | exec cat -v 2>&1 | sed "s/\\^\\[/\\\\033/g"

Pipe the escapes to any tty (with write/append perms) to modify that terminal
	$ setterm -powerdown 0 >> /dev/tty3




cat /etc/machine-id
------

ko

[FOSDEM 2020 - A tool for Community Supported Agriculture (CSA) management, OpenOlitor]
----

(https://fosdem.org/2020/schedule/event/openolitor_community_supported_agriculture/)

> OpenOlitor is a SaaS open-source tool facilitating the organization and
> management of CSAs (Community Supported Agriculture) communities. This tool
> covers a large spectrum of functionalities needed for CSAs such as member
> management, emailing, invoicing, share planning and delivery, absence
> scheduling, etc. This software is organized and monitored by an international
> community that promotes the tool, helps operate it and support the interested
> communities. In order to promote the sustainability of the tool and this
> international community an organization based on CSS (Community Supported
> Software) has been proposed.

[OpenOlitor](https://github.com/OpenOlitor)

> Administrationsplattform für Vertragslandwirtschaftsprojekte, für Initiativen
> der solidarischen Landwirtschaft und für Direktvermarktung im
> Abonnementssystem.

http://openolitor.org/main-page/

OpenSMTPD/OpenSMTPD
----

This is official OpenSMTPD Portable repository. Forks, pull requests and other
contributions are welcome!](https://github.com/OpenSMTPD/OpenSMTPD/)

[FOSDEM 2020 - Orchestrating jails with nomad and pot](https://fosdem.org/2020/schedule/event/orchestrating_jails/)
----

> Docker and Kubernetes are changing the way to deploy services and
> applications in the Linux world. What about FreeBSD? 2 years ago we presented
> pot, another jail abstraction framework. In time, the pot framework has
> developed to provide features containers-alike. The plugin interface provided
> by nomad (a container orchestrator), allowed us to develop a driver for pot,
> enabling nomad to orchestrate pot jails. In this talk, we'd like to present
> this FreeBSD-based ambitious alternative to Docker-Kubernetes


linphone and flexisip - [FOSDEM 2020 - Building an embedded VoIP network for video intercom systems](https://fosdem.org/2020/schedule/event/ema_embedded_voip/)
----

> Linphone (a SIP user-agent) and Flexisip (a SIP proxy server) can be
> integrated into IP video door phones, in-house panels and video surveillance
> devices to build a complete VoIP network..




community/patchutils 0.3.4-3 , dhtmldiff, grepdiff , eee sdiff, 
----
https://en.wikipedia.org/wiki/Diff_utility
    A small collection of programs that operate on patch files


    https://en.wikipedia.org/wiki/Diff_utility

https://en.wikipedia.org/wiki/Diff_utility

community/patchutils	/usr/bin/

/usr/bin/combinediff
/usr/bin/dehtmldiff
/usr/bin/editdiff
/usr/bin/espdiff
/usr/bin/filterdiff
/usr/bin/fixcvsdiff
/usr/bin/flipdiff
/usr/bin/grepdiff
/usr/bin/interdiff
/usr/bin/lsdiff
/usr/bin/recountdiff
/usr/bin/rediff
/usr/bin/splitdiff
/usr/bin/unwrapdiff
/usr/share/man/man1/combinediff.1.gz

by deff in arch
core/diffutils	/usr/bin/
core/diffutils	/usr/bin/cmp
core/diffutils	/usr/bin/diff
core/diffutils	/usr/bin/diff3
core/diffutils	/usr/bin/sdiff

### wdiff and dwdiff


dwdiff is a diff program that operates at the word level instead
of the line level. It is different from wdiff in that it allows
the user to specify what should be considered whitespace, and in
that it takes an optional list of characters that should be
considered delimiters. Delimiters are single characters that are
treated as if they are words, even when there is no whitespace
separating them from preceding words or delimiters. dwdiff is
mostly command-line compatible with wdiff. Only the --autopager,
--terminal and --avoid-wraps options are not supported.


chroot arch-chroot proot fakechroot fakeroot firejail
----


also in home dot.asoundrc  dot.terminfo 
----
https://github.com/lervag/dotfiles


gitconfig includes
---



https://github.com/lervag/dotfiles

[include]
  path = .gitconfig-local

[includeIf "gitdir:~/sintef/"]
  path = .gitconfig-work

[includeIf "gitdir:~/.vim/"]
  path = .gitconfig-personal



NEWTOOLS
===

python (wants gigantic matplot lib dow) [mcastorina/graph-cli
----

: Flexible command line tool to create graphs from CSV data](https://github.com/mcastorina/graph-cli)


metabest [guptarohit/asciigraph: Go package to make lightweight ASCII line graph 
-----
 
 $ seq 1 72 | asciigraph -h 10 -c "plot data from stdin"
╭┈╯ in command line apps with no other dependencies.](https://github.com/guptarohit/asciigraph)


[sharkdp/hexyl: A command-line hex viewer](https://github.com/sharkdp/hexyl)
----

> `hexyl` is a simple hex viewer for the terminal. It uses a colored output to distinguish different categories of bytes (NULL bytes, printable ASCII characters, ASCII whitespace characters, other ASCII characters and non-ASCII).


metabestbest [okbob/pspg: Unix pager designed for work with tables.
----

Designed for PostgreSQL, but MySQL is supported too. Now it can be used as CSV or TSV viewer.](https://github.com/okbob/pspg)


Usage as csv viewer
It works well with miller http://johnkerl.org/miller/doc/index.html


mlr --icsv --opprint --barred put '' obce.csv | pspg --force-uniborder

New version has integrated csv support - just use --csv option.


It can be integrated into mc


copy file from /etc/mc/mc.ext to your ~/.config/mc directory
insert there

#csv
regex/\.csv
    View=pspg -f %f --csv

restart mc

Usage in watch mode
The result of query can be refreshed every n seconds. pspg remembers cursor row,
possible vertical cursor, possible ordering. The refreshing should be paused by pressing
space key. Repeated pressing of this key enables refreshing again.





[zyocum/dedup: Find duplicate text files.](https://github.com/zyocum/dedup)
----


> The script uses locality sensitive hashing (LSH) to compare texts. LSHs are a kind of hashing function that, unlike normal hashing functions, have the property that the probability of a hash collision is proportional to the similarity of objects hashed. In this case, the LSH implemented is simhash (described [here](http://matpalm.com/resemblance/simhash/)).



community/jp2a 1.0.7-2
----
    A small utility for converting JPG images to ASCII
vimdot is a simple script which launches the gvim or vim editor 
----
along with a GUI window showing the dot output of the edited file.
The dot output window automatically refreshes everytime the file
is saved in the editor.

[About Write Freely](https://writefreely.org/about)
----

> WriteFreely is a [Go (golang)](https://golang.org/) application, built with [LESS](http://lesscss.org/) and some plain Javascript on the frontend. This makes it easy to quickly understand and modify to your liking; you can deploy it anywhere; and it's _fast_, too.
> 
> It can be backed by a MySQL or a SQLite database. You can deploy it on a cloud server with as little as 256 MB RAM, or even a Raspberry Pi.

[icyphox/shlide: a slide deck presentation tool written in pure bash](https://github.com/icyphox/shlide)
----


Welcome to ${GRN}shlide${RST}. ${STR}Here${RST} are a few bullet points:

- first point
- second point
    * ${ITA}sub point${RST}
    * ${BLD}another${RST} sub point

simple shell script works with escape sequesces and printf's

	 6 # Color definitions.
	  7 export BLK="\e[38;5;30m"
	    8 export RED="\e[38;5;31m"
	      9 export GRN="\e[38;5;32m"
	       10 export YLW="\e[38;5;33m"


rr-/drill: A CLI program for learning things through spaced repetition.
-----

guys' user case ,  poorly documented card format
The deck format is a simple SQLite database, schema of which can be
easily inspected with any graphical browser / editor. It's left
deliberately undocumented, but the column and table names are pretty
intuitive..

(https://github.com/rr-/drill)


Questions

Q: Why not anki?
A: I like anki, but there's no CLI version I could use remotely, so I decided to roll my own simple program.

Q: Why not SuperMemo or other better algorithms?
A: These are cool, but I wanted drill to stay simple. Additionally, the system used by drill is very similar to the one used by wanikani.com, which I hold in very high regard.


> A CLI program for learning things through [spaced repetition](https://en.wikipedia.org/wiki/Spaced_repetition).
> 
> ### Features
> 
> -   CLI (ideal for `tmux`+`ssh`)
> -   Multiple decks
> -   No configuration needed
> -   Colorful tags
> -   JSON exports/imports for easy deck manipulation
> -   HTML reports

[joelibaceta/xls-cli: A simple cli tool to explore xls files](https://github.com/joelibaceta/xls-cli)
----


gitbatch (go) manage all your repos also (mr joey) and ghq (go)
----
https://github.com/isacikgoz/gitbatch/releases
[x-motemen/ghq: Remote repository management made easy](https://github.com/x-motemen/ghq)

> 'ghq' provides a way to organize remote repository clones, like go get
> does. When you clone a remote repository by ghq get, ghq makes a
> directory under a specific root directory (by default ~/ghq) using the
> remote repository URL’s host and path..


metabest  charmbracelet/glow: markdown go (also mdv python )
----
Render markdown on the CLI, with pizzazz! 💅🏻](https://github.com/charmbracelet/glow)



metabest sdunpack (rust stardict) plato bspwm guy
-----
[baskerville/sdunpack: Unpack a StarDict dictionary as plain text](https://github.com/baskerville/sdunpack)

cargo install --path .

Usage

sdunpack file.dict < file.idx > file.txt

Convert StarDict to dictd

dictzip -d file.dict.dz
sdunpack file.dict < file.idx > file.txt
dictfmt --utf8 --index-keep-orig --headword-separator '|' -s "ShortName" -u "URL" -t file2 < file.txt
dictzip file2.dict


metatop komposition keyboard driven modal haskell vid editor - autodetec clips sentences
----
pandoc guy [owickstrom/komposition: The video editor built for screencasters](https://github.com/owickstrom/komposition)

Komposition automatically detects scenes in screen capture video,
automatically detects sentences in voice-over audio recordings, and
features a high-productivity editing workflow based on keyboard
navigation..


socli - stackexchange cli pip install socli
---

metabest (aur clean simple fzf ) fontpreview (qr transfer arch guy)
----

[sdushantha/fontpreview: 🔡 Very customizable and minimal font previewer written in bash](https://github.com/sdushantha/fontpreview)

drill-srs (pip)
----
[rr-/drill: A CLI program for learning things through spaced repetition.](https://github.com/rr-/drill)

md2html - md4c commonmarkdown compliant c parser
----
[mity/md4c: C Markdown parser. Fast. SAX-like interface. Compliant to CommonMark specification.](https://github.com/mity/md4c)

NEWTOOLSWEB
=====

[mayswind/AriaNg: AriaNg, a modern web frontend making aria2 easier to use.]
----
(https://github.com/mayswind/AriaNg)
AriaNg is a modern web frontend making aria2 easier to use. AriaNg is written in pure html & javascript, thus it does not need any compilers or runtime environment. You can just put AriaNg in your web server and open it in your browser. AriaNg uses responsive layout, and supports any desktop or mobile devices.


foodsharing (repo android app)
----
[foodsharing-dev / foodsharing · GitLab](https://gitlab.com/foodsharing-dev/foodsharing)
> This is the code that powers [foodsharing.de](https://foodsharing.de), [foodsharing.at](https://foodsharing.at), and [foodsharingschweiz.ch](https://foodsharingschweiz.ch).

https://gitlab.com/foodsharing-dev/foodsharing-android

[Intermediate status of the Android App](https://devblog.foodsharing.de/2019/09/01/Android-App-en.html)

> We had considered that we needed an app to improve the manageability
> of food baskets for all users of www.foodsharing.de In the long run,
> all foodsaver functions will be built on this basis without replacing
> the website. Advantages of a smartphone app are the “sensors” that
> come with it, such as camera, GPS and positioning. We have yet to
> focus on the development of the Apple (iOS) App..


https://devdocs.foodsharing.network/getting-the-code.html

[foodsharing is finally Open Source!](https://devblog.foodsharing.de/2019/08/26/open-source.html)

NEWTOOLSCLI
====

yay -S github-cli (official)
----
For many years, hub was the unofficial GitHub CLI tool. gh is a new
project for us to explore what an official GitHub CLI tool can look like
with a fundamentally different design. While both tools bring GitHub to
the terminal, hub behaves as a proxy to git and gh is a standalone
tool..

again alwaysontop bash tput prompt jugglery (2016)
----
[swirepe/alwaysontop: Keep the input line at the top of the terminal](https://github.com/swirepe/alwaysontop)

> It keeps your bash prompt at the top of the screen. It also:
> 
> -   clears the screen automatically
> -   lists the contents of directories upon entering them
> -   abbreviates those contents of there would be too many.
> -   shows the git or svn status in directories that have them

FUCK
====
[MobileRead Wiki - Kobo Configuration Options]
----



(https://wiki.mobileread.com/wiki/Kobo_Configuration_Options)


libinput man libinput and man 4 libinput
-----
the setup
----

### browser display env
[Environment variables - ArchWiki](https://wiki.archlinux.org/index.php/Environment_variables)

> -   `BROWSER` contains the path to the web browser. Helpful to set in an interactive shell configuration file so that it may be dynamically altered depending on the availability of a graphic environment, such as [X](https://wiki.archlinux.org/index.php/X "X"):
> 
> if \[ -n "$DISPLAY" \]; then
>     export BROWSER=firefox
> else 
>     export BROWSER=links
> fi



### tmux setup

tmux list-keys
tmux list-commands
tmux show-environment
DISPLAY=:0
-SSH_AGENT_PID
-SSH_ASKPASS
-SSH_CONNECTION
TERM=rxvt-unicode-256color
WINDOWID=29360137
XAUTHORITY=/home/mmc1/.Xauthority

### tmux and infocmp
pkgfile infocmp
core/ncurses
gets it from /usr/share/terminfo/t/tmux

tmux.conf:

Use "tmux-256color" if available, to enable more capabilities.
if-shell 'infocmp tmux-256color' 'set -g default-terminal "tmux-256color"' 'set -g default-terminal "screen-256color"'
    

### sysctl has nothing to do with systemd ( free pgrep top vmstat ...)
core/procps-ng

core/procps-ng	/usr/bin/free
core/procps-ng	/usr/bin/pgrep
core/procps-ng	/usr/bin/pidof
core/procps-ng	/usr/bin/pkill
core/procps-ng	/usr/bin/pmap
core/procps-ng	/usr/bin/ps
core/procps-ng	/usr/bin/pwdx
core/procps-ng	/usr/bin/slabtop
core/procps-ng	/usr/bin/sysctl
core/procps-ng	/usr/bin/tload
core/procps-ng	/usr/bin/top
core/procps-ng	/usr/bin/uptime
core/procps-ng	/usr/bin/vmstat
core/procps-ng	/usr/bin/w
core/procps-ng	/usr/bin/watch


core/procps-ng 3.3.15-2 [installed]
    Utilities for monitoring your system and its processes

[sysctl - Wikipedia](https://en.wikipedia.org/wiki/Sysctl)

> **sysctl** is a software utility of some
> [Unix-like](https://en.wikipedia.org/wiki/Unix-like "Unix-like") operating
> systems that reads and modifies the attributes of the system
> [kernel](https://en.wikipedia.org/wiki/Kernel_(operating_system) "Kernel
> (operating system)") such as its version number, maximum limits, and security
> settings.[\[1\]](https://en.wikipedia.org/wiki/Sysctl#cite_note-n-sysctl-7-1)
> It is available both as a [system
> call](https://en.wikipedia.org/wiki/System_call "System call") for compiled
> programs, and an administrator command for interactive use and scripting.
> [Linux](https://en.wikipedia.org/wiki/Linux "Linux") additionally exposes
> sysctl as a [virtual file
> system](https://en.wikipedia.org/wiki/Virtual_file_system "Virtual file
> system")

### Arch Linux has deprecated net-tools [net-tools (arp ifconfig netstat route)


core/net-tools	/usr/bin/
core/net-tools	/usr/bin/arp
core/net-tools	/usr/bin/ifconfig
core/net-tools	/usr/bin/ipmaddr
core/net-tools	/usr/bin/iptunnel
core/net-tools	/usr/bin/mii-tool
core/net-tools	/usr/bin/nameif
core/net-tools	/usr/bin/netstat
core/net-tools	/usr/bin/plipconfig
core/net-tools	/usr/bin/rarp
core/net-tools	/usr/bin/route
core/net-tools	/usr/bin/slattach



core/iproute2	/usr/bin/arpd
core/iproute2	/usr/bin/bridge
core/iproute2	/usr/bin/ctstat
core/iproute2	/usr/bin/devlink
core/iproute2	/usr/bin/genl
core/iproute2	/usr/bin/ifcfg
core/iproute2	/usr/bin/ifstat
core/iproute2	/usr/bin/ip
core/iproute2	/usr/bin/lnstat
core/iproute2	/usr/bin/nstat
core/iproute2	/usr/bin/rdma
core/iproute2	/usr/bin/routef
core/iproute2	/usr/bin/routel
core/iproute2	/usr/bin/rtacct
core/iproute2	/usr/bin/rtmon
core/iproute2	/usr/bin/rtpr
core/iproute2	/usr/bin/rtstat
core/iproute2	/usr/bin/ss
core/iproute2	/usr/bin/tc
core/iproute2	/usr/bin/tipc



[Network configuration - ArchWiki](https://wiki.archlinux.org/index.php/Network_manager)

> 
> Arch Linux has deprecated [net-tools](https://www.archlinux.org/packages/?name=net-tools) in favor of [iproute2](https://www.archlinux.org/packages/?name=iproute2).[\[2\]](https://www.archlinux.org/news/deprecation-of-net-tools/)
> 
> Deprecated command
> 
> Replacement commands
> 
> arp
> 
> ip neighbor
> 
> [ifconfig](https://en.wikipedia.org/wiki/ifconfig "wikipedia:ifconfig")
> 
> ip address, ip link
> 
> netstat
> 
> [ss](https://wiki.archlinux.org/index.php/Network_manager#Investigate_sockets)
> 
> route
> 
> ip route

#### wpa_cli MUSTDO (get net list etc)
Optionally, also install the official wpa_supplicant_guiAUR which provides wpa_gui, a graphical front-end for wpa_supplicant, or wpa-cuteAUR which is a fork from an earlier version of wpa_gui with a couple of fixes and improvements. .


At boot (systemd)

The wpa_supplicant package provides multiple systemd service files:

    wpa_supplicant.service - uses D-Bus, recommended for NetworkManager users.
    wpa_supplicant@interface.service - accepts the interface name as an argument and starts the wpa_supplicant daemon for this interface. It reads a /etc/wpa_supplicant/wpa_supplicant-interface.conf configuration file.
    wpa_supplicant-nl80211@interface.service - also interface specific, but explicitly forces the nl80211 driver (see below). The configuration file path is /etc/wpa_supplicant/wpa_supplicant-nl80211-interface.conf.
    wpa_supplicant-wired@interface.service - also interface specific, uses the wired driver. The configuration file path is /etc/wpa_supplicant/wpa_supplicant-wired-interface.conf.

To enable wireless at boot, enable an instance of one of the above services on a particular wireless interface. For example, enable the wpa_supplicant@interface systemd unit.

Now choose and enable an instance of a service to obtain an ip address for the particular interface as indicated in the #Overview. For example, enable the dhcpcd@interface systemd unit.




##### METABEST wpa_cli action script

wpa_cli can run in daemon mode and execute a specified script based on events from wpa_supplicant. Two events are supported: CONNECTED and DISCONNECTED. Some environment variables are available to the script, see wpa_cli(8) for details.

The following example will use desktop notifications to notify the user about the events:

	#!/bin/bash

	case "$2" in
	    CONNECTED)
		notify-send "WPA supplicant: connection established";
		;;
	    DISCONNECTED)
		notify-send "WPA supplicant: connection lost";
		;;
	esac

Remember to make the script executable, then use the -a flag to pass the script path to wpa_cli:



#### you fucknig dont need dhcpcd neither the tool nor the service - sysd-netd has an "internal" one
#### if netctl then dhcpcd ( then openresolv ???)
also some gui's (gigantic deps)


	# netctl enable profile
	This will create and enable a systemd service that will start when the computer boots. Changes to the profile file will not propagate to the service file automatically. After such changes, it is necessary to reenable the profile:
	# netctl reenable profile


#### ip MUST DO
#### package wireless_tools (iwinfo etc) bash completion

/bin/bash: pkgfiles: command not found
core/wireless_tools	/usr/bin/ifrename
core/wireless_tools	/usr/bin/iwconfig
core/wireless_tools	/usr/bin/iwevent
core/wireless_tools	/usr/bin/iwgetid
core/wireless_tools	/usr/bin/iwlist
core/wireless_tools	/usr/bin/iwpriv
core/wireless_tools	/usr/bin/iwspy
#### ifstat
#### no need for 'iw',  'ip' also wireless
#### ss

ss   --tcp --udp --all --resolve  --numeric
resolve is for adds
numeric is for ports




vim dont
----

dont
n thisfile
...stuff
ZZ
n thatfile
...stuf
ZZZ


do
n this that
unimpairad ]a [a
FUCKFUCK
====

inputrc bash
----


	C-- undo
	C-_
	or
	C-X C-u



bash "command list" copy paste a snippet without semi colon encased in parentesis for readability
----

POSIX-compliant systems

If you have curl or wget, you can install pandoc-zotxt.lua by
copy-pasting the following commands into a bourne shell:

(
    set -Cefu
    NAME=pandoc-zotxt.lua VERS=0.3.17
    URL="https://github.com/odkr/${NAME:?}/archive/v${VERS:?}.tar.gz"
    FILTERS="${HOME:?}/.pandoc/filters"
    mkdir -p "${FILTERS:?}"
    cd -P "$FILTERS" || exit
    {
        curl -L "$URL" || ERR=$?
        [ "${ERR-0}" -eq 127 ] && wget -O - "$URL"
    } | tar xz
    mv "$NAME-$VERS/pandoc-zotxt.lua" .
)


###  command grouping

[Command Grouping (Bash Reference Manual)](https://www.gnu.org/software/bash/manual/html_node/Command-Grouping.html)

	> #### 3.2.4.3 Grouping Commands
	> 
	> Bash provides two ways to group a list of commands to be executed as a unit. When commands are grouped, redirections may be applied to the entire command list. For example, the output of all the commands in the list may be redirected to a single stream.
	> 
	> `()`
	> 
	> ( list )
	> 
	> Placing a list of commands between parentheses causes a subshell environment to be created (see [Command Execution Environment](https://www.gnu.org/software/bash/manual/html_node/Command-Execution-Environment.html#Command-Execution-Environment)), and each of the commands in list to be executed in that subshell. Since the list is executed in a subshell, variable assignments do not remain in effect after the subshell completes.
	> 
	> `{}`
	> 
	> { list; }
	> 
	> Placing a list of commands between curly braces causes the list to be executed in the current shell context. No subshell is created. The semicolon (or newline) following list is required.
	> 
	> In addition to the creation of a subshell, there is a subtle difference between these two constructs due to historical reasons. The braces are `reserved words`, so they must be separated from the list by `blank`s or other shell metacharacters. The parentheses are `operators`, and are recognized as separate tokens by the shell even if they are not separated from the list by whitespace.
	> 
	> The exit status of both of these constructs is the exit status of list.



imv icp renameutils
----
METABEST
====
metabest sdunpack (rust stardict) plato bspwm guy
-----
[baskerville/sdunpack: Unpack a StarDict dictionary as plain text](https://github.com/baskerville/sdunpack)

flatten a directory tree and how to copy a list of files to a folder 
----


having a bit of trouble trying to copy a list of files with full paths into a single directory without preserving the paths.

for example the list is a file called 'list' containing the following:

/foo/bar/1.txt
/bar/2.txt
/bar/foo/3.txt
/foo/bar/foooo/baaar/4.txt

and i want to copy all the txt files into a single directory called 'directory' like this:

./directory/1.txt
./directory/2.txt
./directory/3.txt
./directory/4.txt

ive managed to copy all the files into the directory
? / GNU/Linux Discussion / Arch Linux Forums](https://bbs.archlinux.org/viewtopic.php?id=252250)

> rsync -v --files-from=list --no-relative / ./directory


the compiler qutebrowser stikked php curl api pastebin service - qrcodes encrypt etc
------

https://github.com/claudehohl/Stikked
the-compiler.org-pastebin

https://paste.the-compiler.org/about
Stikked is an Open-Source PHP Pastebin, with the aim of keeping a simple and easy to use user interface.


the-compiler.org-pastebin
https://paste.the-compiler.org/api
Create pastes from the commandline

the-compiler.org-pastebin

https://paste.the-compiler.org/api
Examples
Create paste
curl -d text='this is my text' https://paste.the-compiler.org/api/create
Create a paste with the text 'this is my text'.

Create paste from a file
curl -d private=1 -d name=Herbert --data-urlencode text@/etc/passwd https://paste.the-compiler.org/api/create
Create a private paste with the author 'Herbert' and the contents of '/etc/passwd'.

Create paste from a php file
curl -d lang=php --data-urlencode text@main.php https://paste.the-compiler.org/api/create
Create a paste with PHP syntax highlighting.

Create paste via a pipe
echo foo | curl --data-urlencode text@- https://paste.the-compiler.org/api/create
Create a paste based on standard output of a command.

Get paste ;-)
curl https://paste.the-compiler.org/view/raw/[pasteid]
Display paste.



free bash and console keys
----
busy stty setterm etc
stty -a

busy bash
bind -psvX

busy keys stty outside bash (CDOQRSUVWZ \ ? )
----
stty -a

Q/S "hides and continues" input
c-o is kind of c-d without logout

intr = ^C
quit = ^\
erase = ^?
kill = ^U
eof = ^D
eol = <undef>
eol2 = <undef>
swtch = <undef>
start = ^Q
stop = ^S
susp = ^Z
rprnt = ^R
werase = ^W
lnext = ^V
discard = ^O

console screensaver and etc issue
-----

/usr/share/doc/arch-wiki/html/en/Display_Power_Management_Signaling.html

 * 4 DPMS interaction in a Linux console with setterm
   + 4.1 Prevent screen from turning off
   + 4.2 Pipe the output to a cat to see the escapes
   + 4.3 Pipe the escapes to any tty (with write/append perms) to modify that
    terminal


DPMS interaction in a Linux console with setterm

The setterm utility issues terminal recognized escape codes to alter the
terminal. Essentially it just writes/echos the terminal sequences to the
current terminal device, whether that be in screen, a remote ssh terminal,
console mode, serial consoles, etc.

setterm Syntax: (0 disables)

setterm -blank [0-60|force|poke]
setterm -powersave [on|vsync|hsync|powerdown|off]
setterm -powerdown [0-60]


Prevent screen from turning off
	$ setterm -blank 0 -powerdown 0
Alternatively 
	# echo -ne "\033[9;0]" >> /etc/issue
Changing 0 (after the semicolon) to e.g. 3, will keep the screen on for
minutes, before entering standby mode.

Pipe the output to a cat to see the escapes
	$ setterm -powerdown 2>&1 | exec cat -v 2>&1 | sed "s/\\^\\[/\\\\033/g"

Pipe the escapes to any tty (with write/append perms) to modify that terminal
	$ setterm -powerdown 0 >> /dev/tty3




vimdot is a simple script which launches the gvim or vim editor 
----
along with a GUI window showing the dot output of the edited file.
The dot output window automatically refreshes everytime the file
is saved in the editor.

[nickspaargaren/pihole-google: Completely block Google and its services](https://github.com/nickspaargaren/pihole-google)
-----




OpenPrinting 
----
[Open Printing - OpenPrinting](https://openprinting.github.io/)

> OpenPrinting hosts a Printer Compatibility Database. It contains
> entries from both the Foomatic Package and the community.


great book Clif Flynt,_ Sarath Lakshman,_ Shantanu Tushar - Linux Shell Scripting Cookbook (2017, Packt Publishing).epub
----


baskerville guy curl with colours printf commandline fu
-----

https://github.com/baskerville/bin


	#! /bin/sh

	[ "$@" ] || exit 1

	gray=$(printf '\033[1;30m')
	reset=$(printf '\033[0m')
	tmpout=$(mktemp /tmp/fu.XXXX)

	curl -s "https://www.commandlinefu.com/commands/matching/$@/$(printf "%s" "$@" | openssl base64)/plaintext" | grep -v "^# commandlinefu" > "$tmpout"

	if [ -t 1 ] ; then
	    sed 's/^#.*/'$gray'&'$reset'/g' "$tmpout"
	else
	    cat "$tmpout"
	fi

	rm "$tmpout"


habd.as - after dark hugo theme
----

> Pages on [habd.as](https://habd.as) are powered by
> [Hugo](https://gohugo.io) using the [After
> Dark](https://habd.as/code/after-dark/) theme. Most text is written
> and stored in a markdown-like format known as
> [CommonMark](https://commonmark.org) with embedded
> [shortcodes](https://after-dark.habd.as/shortcode/) to facilitate
> reuse of common interface elements such as an
> [alert](https://after-dark.habd.as/shortcode/alert/).

METABESTBEST
=====
a la recutils - yaml file to sqlite  - Niche Museums  simonw
----
[About Niche Museums](https://www.niche-museums.com/about)

> My aim is to add a new museum to this website every week. The most recently
> added museum is always the first item on the homepage.
> 
> The source code for this website is available [on
> GitHub](https://github.com/simonw/museums). You can read more about how it
> works in [niche-museums.com, powered by
> Datasette](https://simonwillison.net/2019/Nov/25/niche-museums/).
> 





[niche-museums.com, powered by Datasette](https://simonwillison.net/2019/Nov/25/niche-museums/)o

The site is now rendered server-side. The previous version used lit-html to
render content using JavaScript.
[lit-html](https://lit-html.polymer-project.org/)


Notably, the site is entirely powered by Datasette. It’s a heavily customized
Datasette instance, making extensive use of custom templates and plugins.

It’s a really fun experiment. I’m essentially using Datasette as a weird twist
on a static site generator—no moving parts since the database is immutable but
there’s still stuff



happening server-side to render the pages.
Continuous deployment

The site is entirely stateless and is published using Circle CI to a serverless hosting provider (currently Zeit Now v1, but I’ll probably move it to Google Cloud Run in the near future.)

The site content—46 museums and counting—lives in the museums.yaml file. I’ve been adding a new museum listing every day by editing the YAML file using Working Copy on my iPhone.

The build script runs automatically on every commit. It converts the YAML file into a SQLite database using my yaml-to-sqlite tool, then runs datasette publish now... to deploy the resulting database.

### hacker discussion apropos recutils


I've been experimenting recently with YAML for this kind of thing, and it's working out really well for me so far.

I have a tool called yaml-to-sqlite ( https://github.com/simonw/yaml-to-sqlite ) which converts a YAML file into a SQLite database, which I can then use with Datasette ( https://github.com/simonw/datasette )

My biggest project with it so far has been my site https://www.niche-museums.com/ - a guide to small and niche museums. The museums themselves live in a single ~100KB YAML file in GitHub: https://github.com/simonw/museums/blob/master/museums.yaml

I have a CI script which builds that YAML file into a SQLite database and deploys it + Datasette + custom templates to https://www.niche-museums.com/

I've been running the site like this for a few months now and I really like it. I love having my content in source control, I find editing the YAML to be reasonably pleasant (I even edit it on my iPhone sometimes using the W


### [simonw/yaml-to-sqlite: Utility for converting YAML files to SQLite](https://github.com/simonw/yaml-to-sqlite)

### I also built a simple JavaScript image gallery 

to better display the 54 photos I published from our trip to Ray Bandar’s basement.

### annotate_nominatim.py uses the OpenStreetMap Nominatim API
to reverse geocode the latitude and longitude of each museum, adding extra
columns for the city, state, country and all kinds of other interesting
geographical details.



###  simon created django ? datasette for journalists ?
[My JSK Fellowship: Building an open source ecosystem of tools for data journalism](https://simonwillison.net/2019/Sep/10/jsk-fellowship/)

[John S. Knight Journalism Fellowships at Stanford | The John S. Knight Journalism Fellowships program supports diverse, resilient leaders with collaborative mindsets who are exploring solutions to journalism’s biggest problems in a time of tremendous change.](https://jsk.stanford.edu/)

https://en.wikipedia.org/wiki/John_S._and_James_L._Knight_Foundation

> I started a new chapter of my career last week: I began a year long
> fellowship with the [John S. Knight Journalism Fellowships
> program](https://jsk.stanford.edu/) at Stanford.

How might we grow an open source ecosystem of tools to help data journalists
collect, analyze and publish the data underlying their stories?

I’ve worked with newspapers a few times in the past: I helped create what would
later become Django at the Lawrence Journal-World fifteen years ago, and I
spent two years working on data journalism projects at the Guardian in London
before being sucked into the tech startup world. My Datasette project was
inspired by the challenges I saw at the Guardian, and I’m hoping to evolve it
(and its accompanying ecosystem) in as useful a way as possible.


simon down csv.zip to git repo and commit to sqlite - clean code
----

[simonw/fara-history: Tracking the history of the FARA data from https://www.justice.gov/nsd-fara](https://github.com/simonw/fara-history)

[simonw/sf-tree-history: Tracking the history of trees in San Francisco](https://github.com/simonw/sf-tree-history)




### Datasette: A tool for exploring and publishing data
### csvs-to-sqlite: Convert CSV files into a SQLite database
[simonw/csvs-to-sqlite: Convert CSV files into a SQLite database](https://github.com/simonw/csvs-to-sqlite)

> Convert CSV files into a SQLite database. Browse and publish that SQLite database with [Datasette](https://github.com/simonw/datasette).
> 
> Basic usage:
> 
>     csvs-to-sqlite myfile.csv mydatabase.db
>     
> 
> This will create a new SQLite database called `mydatabase.db` containing a
> single table, `myfile`, containing the CSV content.



### db-to-sqlite: CLI tool for exporting a MySQL or PostgreSQL database as a SQLite file
### sqlite-utils
[simonw/sqlite-utils: Python CLI utility and library for manipulating SQLite databases](https://github.com/simonw/sqlite-utils)

> Python CLI utility and library for manipulating SQLite databases.
> 
> Read more on my blog: [sqlite-utils: a Python library and CLI tool for building SQLite databases](https://simonwillison.net/2019/Feb/25/sqlite-utils/)
> 
> Install it like this:
> 
>     pip3 install sqlite-utils

### yaml-to-sqlite
[simonw/yaml-to-sqlite: Utility for converting YAML files to SQLite](https://github.com/simonw/yaml-to-sqlite)

### trees: with circleci dotfolder yaml tasks
[simonw/sf-tree-history: Tracking the history of trees in San Francisco](https://github.com/simonw/sf-tree-history)

> This repository [uses CircleCI](https://circleci.com/gh/simonw/sf-tree-history) to retrieve the [official CSV file of trees in San Francisco](https://data.sfgov.org/City-Infrastructure/Street-Tree-List/tkzw-k3nq) once a day and track any changes to it over time using the git commit history.
> 
> It uses [csv-diff](https://github.com/simonw/csv-diff) to generate human-readable commit message
### fara: with a glue shell script and python datasette sqlite utils cvs (local)
[simonw/fara-history: Tracking the history of the FARA data from https://www.justice.gov/nsd-fara](https://github.com/simonw/fara-history)



### convert json to html


[simonw/datasette-json-html: Datasette plugin for rendering HTML based on JSON values](https://github.com/simonw/datasette-json-html)


### irma hurricane
https://github.com/simonw/disaster-data

Data scraped by https://github.com/simonw/disaster-scrapers

See Scraping hurricane Irma for details on a previous iteration of this
project. Data from that project is now archived in irma-2017-archive/.

[Scraping hurricane Irma](https://simonwillison.net/2017/Sep/10/scraping-irma/)

### disaster scrapers (py disaster lib and circle ci with venv)

py reqs


github-contents
requests
bs4
html5lib
 

Github Actions - simon download zipped fbi csv gov files  GitHub Actions 
----
[Deploying a data API using GitHub Actions and Cloud Run](https://simonwillison.net/2020/Jan/21/github-actions-cloud-run/)

> It’s all still pretty fascinating though, in part because it gets updated. A lot. Almost every business day in fact.
> 
> ### Tracking FARA history
> 
> I know this because seven months ago I set up a scraper for it. Every twelve hours I have code which downloads the [four bulk CSVs](https://efile.fara.gov/ords/f?p=API:BULKDATA) published by the Justice department and saves them to [a git repository](https://github.com/simonw/fara-history). It’s the same trick I’ve been using [to track San Francisco’s database of trees](https://simonwillison.net/2019/Mar/13/tree-history/) and [PG&E’s outage map](https://simonwillison.net/2019/Oct/10/pge-outages/).
> 
> I’ve been running the scraper using Circle CI, but this weekend I decided to switch it over to [GitHub Actions](https://github.com/features/actions) to get a better idea for how they work.




metabestbest justinmk function for lynx in term neovim
-----

[config/init.vim at master · justinmk/config](https://github.com/justinmk/config/blob/master/.config/nvim/init.vim)



> function! s:init_lynx() abort nnoremap <nowait><buffer> <C-F> i<PageDown><C-\\><C-N> tnoremap <nowait><buffer> <C-F> <PageDown> nnoremap <nowait><buffer> <C-B> i<PageUp><C-\\><C-N> tnoremap <nowait><buffer> <C-B> <PageUp> nnoremap <nowait><buffer> <C-D> i:DOWN_HALF<CR><C-\\><C-N> tnoremap <nowait><buffer> <C-D> :DOWN_HALF<CR> nnoremap <nowait><buffer> <C-U> i:UP_HALF<CR><C-\\><C-N> tnoremap <nowait><buffer> <C-U> :UP_HALF<CR> nnoremap <nowait><buffer> <C-N> i<Delete><C-\\><C-N> tnoremap <nowait><buffer> <C-N> <Delete> nnoremap <nowait><buffer> <C-P> i<Insert><C-\\><C-N> tnoremap <nowait><buffer> <C-P> <Insert> nnoremap <nowait><buffer> u i<Left><C-\\><C-N> nnoremap <nowait><buffer> <C-R> i<C-U><C-\\><C-N> nnoremap <nowait><buffer> <CR> i<CR><C-\\><C-N> nnoremap <nowait><buffer> gg i:HOME<CR><C-\\><C-N> nnoremap <nowait><buffer> G i:END<CR><C-\\><C-N> nnoremap <nowait><buffer> zl i:SHIFT_LEFT<CR><C-\\><C-N> nnoremap <nowait><buffer> zL i:SHIFT_LEFT<CR><C-\\><C-N> nnoremap <nowait><buffer> zr i:SHIFT_RIGHT<CR><C-\\><C-N> nnoremap <nowait><buffer> zR i:SHIFT_RIGHT<CR><C-\\><C-N> nnoremap <nowait><buffer> gh i:HELP<CR><C-\\><C-N> nnoremap <nowait><buffer> cow i:LINEWRAP_TOGGLE<CR><C-\\><C-N> tnoremap <buffer> <C-C> <C-G><C-\\><C-N> nnoremap <buffer> <C-C> i<C-G><C-\\><C-N> endfunction command! -nargs=1 Web vnew|call termopen('lynx -use_mouse '.shellescape(<q-args>))|call <SID>init_lynx() command! -nargs=1 Websearch vnew|call termopen('lynx -use_mouse https://duckduckgo.com/?q='.shellescape(substitute(<q-args>,'#','%23','g')))|call <SID>init_lynx() nnoremap gow :Start "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" --no-proxy-server "%:p"<cr> silent! source ~/.vimrc.local
metabest [lervag/apy: CLI script for interacting with local Anki collection](https://github.com/lervag/apy)
----

Important: apy uses the python API from the Anki desktop app. So please
make sure to install the Anki source. Note that the releases on Ankiweb
only include precompiled binaries. Ankiweb recommends that one uses
these precompiled binaries, but for apy to work one needs the Anki
source to be available. These are typically included if one installs
from repositories (e.g. with sudo apt install anki or pacman -S anki).
One may also download the source either from the "Development" tab on
Ankiweb or from github.

apy assumes that the Anki source is available at /usr/share/anki. If you
put it somewhere else, then you must set the environment variable
APY_ANKI_PATH, e.g. export APY_ANKI_PATH=/my/path/to/anki.


> [Anki](https://apps.ankiweb.net/index.html) is a flash card program
> which makes remembering things easy. `apy` is a Python script for
> easily adding cards to Anki.


anki vim [tbabej/knowledge: Never forget anything!](https://github.com/tbabej/knowledge)
----

> Knowledge is a (Neo)Vim plugin that helps you actually remember what you wrote down in your notes, forever.
> 
> To achieve its goal, Knowledge generates flash cards that are piped
> into the [SRS
> software](https://en.wikipedia.org/wiki/Spaced_repetition) of your
> choice (currently Anki and Mnemosyne are supported)..




tree a directroy and create and index.html
-----
	
every 50 days ago [-]

"I'd love to see an extreeeemely minimal tool which lets you drop some files in a folder and then create an index page that links to those."

I use the tree command on BSD to do just that. It has the option of creating html output with a number of additional options.

    An example: tree -P *.txt -FC -H http://baseHREF -T 'Your Title' -o index.html
[Feature comparison of ack, ag, git-grep, GNU grep and ripgrep | Hacker
News](https://news.ycombinator.com/item?id=16096824)

metabestbest correct way to tail -f and grep - line buffered - stdbuff in coreutils 
----
> [palotasb](https://news.ycombinator.com/user?id=palotasb) [on Jan 8, 2018](https://news.ycombinator.com/item?id=16099852) [\[-\]](javascript:void(0))
> 
>   
> 
> That's an orthogonal feature, it writes output after each line as opposed to every 4096 bytes, when the output is a pipe instead of a terminal. Useful when the other end of the pipe still goes to the terminal and you want to see it immediately. If \`some-util-with-output\` echoes stdin then without the option the following would not show you the latest grepped lines until the 4096 buffer fills.
> 
>       tail -F output.log | grep --line-buffered TEXT | some-util-with-output
> 
> ![](https://news.ycombinator.com/s.gif)
> 
> [richardwhiuk](https://news.ycombinator.com/user?id=richardwhiuk) [on Jan 8, 2018](https://news.ycombinator.com/item?id=16098345) [\[-\]](javascript:void(0))
> 
>   
> 
> huh?
> 
> ![](https://news.ycombinator.com/s.gif)
> 
> [whacker](https://news.ycombinator.com/user?id=whacker) [on Jan 9, 2018](https://news.ycombinator.com/item?id=16102899) [\[-\]](javascript:void(0))
> 
>   
> 
> I mean you can use grep as a filter for tail -f output.

### do i need it in gnu grep ?

[linux - How to 'grep' a continuous stream? - Stack Overflow](https://stackoverflow.com/questions/7161821/how-to-grep-a-continuous-stream)

> turn on `grep`'s line buffering mode when using BSD grep (FreeBSD, Mac
> OS X etc.)
> 
>     tail -f file | grep --line-buffered my_pattern
>     
> 
> You don't need to do this for GNU grep (used on pretty much any Linux)
> as it will flush by default (YMMV for other Unix-likes such as
> SmartOS, AIX or QNX



[streaming - unix command 'tail' lost option '--line-buffered' - Stack Overflow](https://stackoverflow.com/questions/18227308/unix-command-tail-lost-option-line-buffered)

> As far as can be told by simple googling, `tail` doesn't appear to
> have a `--line-buffered` option, `grep` does. `--line-buffered` is
> useful to force line buffering even when writing to a non-TTY, a
> typical idiom being:
> 
>     tail -f FILE | grep --line-buffered REGEXP > output
>     
> 
> Here the point of `--line-buffered` is to prevent `grep` from
> buffering output in 8K chunks and forcing the matched lines to
> immediately appear in the output file.
> 
> `tail -f` is unbuffered regardless of output type, so it doesn't need
> a `--line-buffered` option equivalent to the one in `grep`. This can
> be verified by running `tail -f somefile | cat` and appending a line
> to the file from another shell. One observes that, despite its
> standard output being a pipe, `tail` immediately flushes the newly
> arrived line.



### [stdio buffering](https://www.pixelbeat.org/programming/stdio_buffering/)

> ## stdio output buffering problems
> 
> Now consider the case where the data source has intermittent output  
> and one wants to both see the data as it appears and filter the data.  
> For example, one wants to filter the output of tcpdump -l or tail -f etc.  
> Note certain filters (like sort) need to buffer all data internally and so  
> can't be used in this application.  
> As a concrete example consider the following pipeline which shows the IP addresses  
> accessing a web site while filtering out consecutive access from a particular IP.  
> 
> $ tail -f access.log | cut -d' ' -f1 | uniq

[Update Aug 2009: We've made the LD_PRELOAD method above easily available in coreutils 7.5
with the a new stdbuf command which can be used with the example presented here like:

tail -f access.log | stdbuf -oL cut -d ' ' -f1 | uniq

Note use stdbuf -o0 if your data is not line oriented.
For full details please see the stdbuf man page or stdbuf info manual.]

### man stdbuff



EXAMPLES
       tail -f access.log | stdbuf -oL cut -d ' ' -f1 | uniq
              This will immediately display unique entries from
	      access.log
### [What does grep line buffering do? - Ask Ubuntu](https://askubuntu.com/questions/562344/what-does-grep-line-buffering-do)




Here's my command that I'm using in a script to grep real-time data. It
doesn't seem to pull real-time data correctly as it just misses some
lines.

tail -f <file> | fgrep "string" | sed 's/stuff//g' >> output.txt

What would the following command do? What is "line buffering"?

tail -f <file> | fgrep --line-buffered "string" | sed 's/stuff//g' >>
output.txt




> When using non-interactively, most standard commands, include `grep`,
> buffer the output, meaning it does not write data immediately to
> `stdout`. It collects large amount of data (depend on OS, in Linux,
> often 4096 bytes) before writing.
> 
> In your command, `grep`'s output is piped to `stdin` of `sed` command,
> so `grep` buffer its output.
> 
> So, `--line-buffered` option causing `grep` using line buffer, meaning
> writing output each time it saw a newline, instead of waiting to reach
> 4096 bytes by default. But in this case, you don't need `grep` at all,
> just use `tail` \+ `sed`:
> 
>     tail -f <file> | sed '/string/s/stuff//g' >> output.txt
>     
> 
> With command that does not have option to modify buffer, you can use
> [GNU coreutils
> stdbuf](http://www.gnu.org/software/coreutils/manual/coreutils.html#stdbuf-invocation)
> 
>     tail -f <file> | stdbuf -oL fgrep "string" | sed 's/stuff//g' >>
>     output.txt
>     
> 
> to turn on line buffering or using `-o0` to disable buffer.
> 
> **Note**
> 
> -   [stdio
>     buffering](http://www.pixelbeat.org/programming/stdio_buffering/)


2do send output to notify-send perpetually, but in chunks instead of line-by-line
----

[unix - Piping to notify-send in chunks - Stack Overflow](https://stackoverflow.com/questions/34778384/piping-to-notify-send-in-chunks)


This puts the complete output of mocha -w in the fourth argument of notify-send

If mocha -w does not terminate, the bash-specific read -t comes in handy:

mocha -w | ( while true; do MSG=""; while read -t .1 LINE; do MSG="$MSG $LINE"; done; if [ "$MSG" != "" ]; then notify-send -t 5000 "$MSG"; fi; done; )

This aggregates all lines which come in in the timeframe of 1/10th second in one message. You can adjust this timeout to fit your needs. Note that this is bash-specific, other shells (i.e. dash) may not support it.
shareimprove this answer

ROLLING
=====


deleteme2
---
deleteme cred username
----


$ ip a | convert label:@- myipaddress.png

In recent Ubuntu Linux distributions, certain convert operations are restricted for security reasons. If you tried the above commands in Ubuntu OS, you might be encountered with the following error message:

convert-im6.q16: not authorized `@-' @ error/property.c/InterpretImageProperties/3516.

hange the policy.

$ sudo nano /etc/ImageMagick-6/policy.xml
Find the following line:

<policy domain="path" rights="none" pattern="@*" />
Comment out or remove the following line:

[...]
<!--  <policy domain="path" rights="none" pattern="@*"/> -->
[...]

### save to existing image
$ convert -font -misc-fixed-*-*-*-*-*-*-*-*-*-*-*-* -fill black -draw "text 270,260 \" `lsb_release -a` \"" image.png systemdetails.png

his command will print the output of “lsb_release -a” command to an image called image.png and saves it with a new name “systemdetails.png”

### tee

You might wanted to write the output of a command to multiple files. Here is how to do it.

$ uname -a | tee file1 file2
The above command w





metabest (imagemagick convert et al ) Images done right: Web graphics, good to the last byte — Martian Chronicles, Evil Martians
-----

TLDR 
However, even with all the WebP’s technical prowess, JPEG and PNG are
not leaving the ring anywhere soon as it only works in browsers
environments: if you save a WebP image to a disk, you most likely won’t
be able to open it with default image viewing software on your system..

- convert (magick) enough for most cases
- mozjpge
- webp is the future
- Using GIFs for animations on your webpage in 2019 is an incredibly bad idea.
- You are better off publishing your animated content as video files: either MP4 or WebM.





To summarize, JPEG is fine to be used in:

    Backgrounds;
    large camera photos: avatars, banners, etc.;
    images when super-precise quality is not our goal.

To summarize, PNG is ideal for:

    Images that need to be transparent;
    charts, schemes, highly detailed maps, and details matter;
    images that contain text.


webp
But as you will soon see, the advantages outweigh compatibility
problems. A lossless flavor of WebP outperforms PNG by still keeping
images sharp and transparent while the lossy version of the format wipes
the floor with JPEG and still supports opacity..

Where WebP really shines is the compression at the lowest possible
quality. WebP at quality 0% is still perceived much better by your eyes
than JPEG at quality 10%..



[Images done right: Web graphics, good to the last byte — Martian Chronicles, Evil Martians’ team blog](https://evilmartians.com/chronicles/images-done-right-web-graphics-good-to-the-last-byte-optimization-techniques)

> `convert -strip -interlace Plane -gaussian-blur 0.05 -quality 85%
> image.jpg image_new.jpg`

identify -format "%[interlace]" your_file_name.jpg


### anim gifs

But enough talk, time to crunch some numbers. We will start with a
cheesy GIF source and convert it to WebP, APNG, AV1 as MP4, H.264 as
MP4, and WebM to detect a winner. We will use CLI tools gif2webp and
gif2apng, as well as ffmpeg. We will also use GIMP as an alternative way
to convert GIF to WebP..

The size of the GIF is reduced by 90% when using video codecs and by 67%
using compressed WebP by GIMP. So if you want to make the web faster
(and better), think about always using MP4 as an animated image instead
of GIF. See, you don’t have to be a 10x engineer to reduce the size of
the assets by 10x!.

PI
===

ROLLING
====

cheapest sonoff basic and a contactor
[High Power Mains Switching with Sonoff - Scargill's Tech Blog](https://tech.scargill.net/high-power-mains-switching-with-sonoff/)

https://pt.wikipedia.org/wiki/Contator
https://pt.wikipedia.org/wiki/Disjuntor
https://en.wikipedia.org/wiki/Circuit_breaker

https://de.wikipedia.org/wiki/Sch%C3%BCtz_(Schalter)
https://en.wikipedia.org/wiki/Contactor

