FUCK
====


the setup
----

pkgfile infocmp
core/ncurses
gets it from /usr/share/terminfo/t/tmux

tmux.conf:

Use "tmux-256color" if available, to enable more capabilities.
if-shell 'infocmp tmux-256color' 'set -g default-terminal "tmux-256color"' 'set -g default-terminal "screen-256color"'
    
HELPDESK
====

long urls in urxvt (seems no fix)
----
[url-select: selection of long urls · Issue #61 · muennich/urxvt-perls](https://github.com/muennich/urxvt-perls/issues/61)

> When urxvt wraps a line containing an url, url-select only catches the first line.BROWSER
====




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
justinmk function for lynx in term
-----
[config/init.vim at master · justinmk/config](https://github.com/justinmk/config/blob/master/.config/nvim/init.vim)

> function! s:init_lynx() abort nnoremap <nowait><buffer> <C-F> i<PageDown><C-\\><C-N> tnoremap <nowait><buffer> <C-F> <PageDown> nnoremap <nowait><buffer> <C-B> i<PageUp><C-\\><C-N> tnoremap <nowait><buffer> <C-B> <PageUp> nnoremap <nowait><buffer> <C-D> i:DOWN_HALF<CR><C-\\><C-N> tnoremap <nowait><buffer> <C-D> :DOWN_HALF<CR> nnoremap <nowait><buffer> <C-U> i:UP_HALF<CR><C-\\><C-N> tnoremap <nowait><buffer> <C-U> :UP_HALF<CR> nnoremap <nowait><buffer> <C-N> i<Delete><C-\\><C-N> tnoremap <nowait><buffer> <C-N> <Delete> nnoremap <nowait><buffer> <C-P> i<Insert><C-\\><C-N> tnoremap <nowait><buffer> <C-P> <Insert> nnoremap <nowait><buffer> u i<Left><C-\\><C-N> nnoremap <nowait><buffer> <C-R> i<C-U><C-\\><C-N> nnoremap <nowait><buffer> <CR> i<CR><C-\\><C-N> nnoremap <nowait><buffer> gg i:HOME<CR><C-\\><C-N> nnoremap <nowait><buffer> G i:END<CR><C-\\><C-N> nnoremap <nowait><buffer> zl i:SHIFT_LEFT<CR><C-\\><C-N> nnoremap <nowait><buffer> zL i:SHIFT_LEFT<CR><C-\\><C-N> nnoremap <nowait><buffer> zr i:SHIFT_RIGHT<CR><C-\\><C-N> nnoremap <nowait><buffer> zR i:SHIFT_RIGHT<CR><C-\\><C-N> nnoremap <nowait><buffer> gh i:HELP<CR><C-\\><C-N> nnoremap <nowait><buffer> cow i:LINEWRAP_TOGGLE<CR><C-\\><C-N> tnoremap <buffer> <C-C> <C-G><C-\\><C-N> nnoremap <buffer> <C-C> i<C-G><C-\\><C-N> endfunction command! -nargs=1 Web vnew|call termopen('lynx -use_mouse '.shellescape(<q-args>))|call <SID>init_lynx() command! -nargs=1 Websearch vnew|call termopen('lynx -use_mouse https://duckduckgo.com/?q='.shellescape(substitute(<q-args>,'#','%23','g')))|call <SID>init_lynx() nnoremap gow :Start "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" --no-proxy-server "%:p"<cr> silent! source ~/.vimrc.local
      

      

justinmk dirvish keep netrw gx
-----
[config/init.vim at master · justinmk/config](https://github.com/justinmk/config/blob/master/.config/nvim/init.vim)

> " Disable netrw, but autoload it for \`gx\`. let g:loaded_netrwPlugin = 0 nmap gx <Plug>NetrwBrowseX nnoremap <silent> <Plug>NetrwBrowseX :call netrw#BrowseX(expand((exists("g:netrw_gx")? g:netrw_gx : '<cfile>')),netrw#CheckIfRemote())<CR>
      
        

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



FUCK
====

libinput man libinput and man 4 libinput
-----

ROLLING
=====


deleteme2
---
deleteme cred username
----
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


METABESTBEST
=====
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
 

METABESTBESTBEST a la recutils - yaml file to sqlite  - Niche Museums  simonw
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


simon created django ? datasette for journalists ?
----
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


simon down fbi csv GitHub Actions 
----
[Deploying a data API using GitHub Actions and Cloud Run](https://simonwillison.net/2020/Jan/21/github-actions-cloud-run/)

> It’s all still pretty fascinating though, in part because it gets updated. A lot. Almost every business day in fact.
> 
> ### Tracking FARA history
> 
> I know this because seven months ago I set up a scraper for it. Every twelve hours I have code which downloads the [four bulk CSVs](https://efile.fara.gov/ords/f?p=API:BULKDATA) published by the Justice department and saves them to [a git repository](https://github.com/simonw/fara-history). It’s the same trick I’ve been using [to track San Francisco’s database of trees](https://simonwillison.net/2019/Mar/13/tree-history/) and [PG&E’s outage map](https://simonwillison.net/2019/Oct/10/pge-outages/).
> 
> I’ve been running the scraper using Circle CI, but this weekend I decided to switch it over to [GitHub Actions](https://github.com/features/actions) to get a better idea for how they work.

