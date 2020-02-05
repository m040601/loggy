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
MICROTOPICS
====

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

> The creators of the Mercury Web Parser initially offered it as a free service via a ReSTful API, but have since open sourced it. The API was shut down April 15, 2019. To continue using the parser, install its command-line driver using [`yarn`](https://github.com/yarnpkg/yarn) or [`npm`](https://github.com/npm/cli) package managers:


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

NEWTOOLSWEB
=====

[mayswind/AriaNg: AriaNg, a modern web frontend making aria2 easier to use.]
----
(https://github.com/mayswind/AriaNg)
AriaNg is a modern web frontend making aria2 easier to use. AriaNg is written in pure html & javascript, thus it does not need any compilers or runtime environment. You can just put AriaNg in your web server and open it in your browser. AriaNg uses responsive layout, and supports any desktop or mobile devices.

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


METABEST
====

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

