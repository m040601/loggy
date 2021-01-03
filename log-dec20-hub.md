GEMINI
=====

carcosa.net

MORERSS
====

via nojs.club
interesting geeks
https://datagubbe.se
https://datagubbe.se/atom.xml


SHELL
===


fuck cat EOF and redir
----

[about - zakaria's web log](https://zakaria.org/about.html)

Contact:

	cat <<EOF | uudecode -o /dev/stdout
	begin-base64 644 -
	emFrYXJpYWtAdHV0YS5pbwo=
	====
	EOF


NEW TOOLS
====


syngesture (new critic of libinput)
----

is a configurable, multi-device capable, and rust-powered userland daemon that brings basic multi-touch support for one-, two-, and three-finger gestures to the vener
https://neosmart.net/blog/2020/multi-touch-gestures-on-linux/

[mqudsi/syngesture: Swipes and gestures for Linux with the MT multitouch protocol](https://github.com/mqudsi/syngesture/)


[JoseExposito/touchegg: Linux multi-touch gesture recognizer](https://github.com/JoseExposito/touchegg)
----


JEKYLL and co
======

This website is a single HTML file
----


[John Doe’s page](https://john-doe.neocities.org/)

. It simply uses the #anchor suffix (from 1992) and the :target CSS selector to show and hide pages/content.


more lean css
----

http://bettermotherfuckingwebsite.com/

gross css CSS file that makes your webpage look good with just 144 bytes.
-----
[gross.css – Style in just 144 chars](https://to1ne.gitlab.io/gross.css/)
Browser default styles are great, they take care of most of the styling,
they use system fonts, they respect accessibility settings, etc. But
they are pretty ugly. It looks like your visiting a page from 90’s. With
these 144 characters of CSS you get most of the browser defaults, with a
tiny set of tweaks to make the page look more modern.


more recent m4 bakery
----
[The /bin/sh Blog. Part I: Timmy's Templates - zakaria's web log](https://zakaria.org/posts/2020-08-01-shblog.html)

hhhmmm.. good for busybox ? [e-zk/shlog: a static blog generator in /bin/sh](https://github.com/e-zk/shlog)
----

lowdown     Markdown to HTML converter (https://kristaps.bsd.lv/lowdown/).

GOALS
    - Be a shell script.
    - Minimal external dependencies.
    - Be fast.
    - Be cross-platform (POSIX?).

NON-GOALS
    - JavaScript (though it should be easy to add it yourself).
    - Post tags/categories.



nojs.club
----

https://sjmulder.nl/en/textonly.html


simple css min site without js (via nojs.club)
----

https://en.wikipedia.org/wiki/Minification_(programming)

Minification can be distinguished from the more general concept of data compression in that the minified source can be interpreted immediately without the need for an uncompression step: the same interpreter can work with both the original as well as with the minified source.

[mincss - CSS Minifier | datagubbe.se](https://datagubbe.se/mincss/)

i[Site Colophon and Mission Statement for a Better Web | datagubbe.se](https://datagubbe.se/colophon/)

Autumn 2020

This website has been built with a number of key concepts in mind. Among them are the following:
Speed

Terse, hand edited HTML. Basic, minified CSS. No gratuitous use of images. And above all, no JavaScript at all.
 This site is designed to look as good as possible on as many platforms and in as many browsers as possible, while still adhering to current standards and practices. It's regularly tested in Firefox, Links2, w3m, Chromium and Safari (on iOS).

The markup and CSS code is regularly checked with W3C's validators and some effort has been taken to provide useful alt attributes on images, meaningful link texts and a markup structure that's hopefully friendly to screen readers.
Rtia






hugo no js
----

https://github.com/J-Siu/hugo-theme-sk1/
 When I created this website I did not know about the “Small Internet”, so I decided to use Hugo framework with a theme that does not have Javascript and CSS but thanks to nice people in the fosstodon they show me two good alternatives:

https://jrballesteros05.codeberg.page/posts/webopinion/

METABEST
=====

interesting use of github issues with github automaitions
-----

[Building noJS.club](https://goel.io/nojs-club)


 full flow in nojs.club is like this:



    Someone opens an issue suggesting a new website. The issue must follow the set template.

    A Github Actions Workflow kicks off and

    a. Extracts the domain of the request (code ref)

    b. Find any use of <script> tags on the web page. Good ol’ curl and grep come in handy here (code ref)

    c. Post a comment on the issue with any Javascript found (code ref)

Once that happens, someone (me) must manually approve the request. I must post a comment in the format /approve example.com 123.45 where the numbers refer to the total size of downloaded assets in KB. Another workflow then kicks off and adds the domain to a CSV file in the same repo (code ref).

;w
;w


github now has discussions
----


ROLLING
====





It's fucking nine-year-olds. Our fans have, like, a
------

             > When I was nine years old, I bought Vanilla Ice's "Ice Ice Baby", and I
             listened to that shit (I'm not joking) like, 250 times in a week. Like a
             fucking idiot. That's who's listening to this shit. Getting a billion
             streams in a month. It's fucking nine-year-olds. Our fans have, like, a
             hundred and fifty albums that they listen to, on a sort of rotation, at
             least one of them once a month.


