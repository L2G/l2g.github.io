---
layout: post
title: "What the hell am I doing? (February 25, 2013)"
date: 2013-02-25 12:00
comments: true
categories: status Chef Windowtint Ruby-REST-Client Ostiary
---
I'm doing a lot with [Chef](http://www.opscode.com/chef/) these days. I'm
trying to stomp on Windows-related bugs in Chef and one of its supporting gems,
[Ohai](https://github.com/L2G/ohai).  I've also forked the [timezone
cookbook](http://community.opscode.com/cookbooks/timezone-ii) to develop it
further.  To
test it, I'm using [test-kitchen](https://github.com/opscode/test-kitchen) along
with Vagrant boxes built with [bento](https://github.com/opscode/bento) (and
I'm building on bento a little in the process).

I have a new Ruby gem called [Windowtint](https://rubygems.org/gems/windowtint)
-- my first official RubyGems-hosted gem. It's meant to abstract the chore of
supporting so-called ANSI color output on Windows. Most Ruby tools that output
color tell Windows users just to install
[ANSICON](https://github.com/adoxa/ansicon), which actually is a great add-on
because it makes ANSI color available to _everything_ that outputs to the
command line. Unfortunately, it's a system-level driver that has to be
copied directly into the Windows system directory, and this is <span lang="de"
xml:lang="de">verboten</span> in some lab environments (like my employer's) with
strict IT usage policies. So Windowtint tries to smooth things over in this
way: it looks for ANSICON or win32console and silently uses those if available,
but if they aren't, it advises the user to install one.
([win32console](https://rubygems.org/gems/win32console) is a gem
and should be installable by anyone.)

[rest-client](https://github.com/archiloque/rest-client) is a nice little Ruby gem for accessing Web services via HTTP, particularly nice for those using REST. However, the second maintainer seems to have his attention elsewhere these days, so I set up a @rest-client "organization" to promote the idea of collective maintenance of the project. Now there is a third maintainer who has the blessing of the original author to maintain [the rest-client repository there](https://github.com/rest-client/rest-client).

While researching port knocking, I stumbled upon [Ostiary](http://ingles.homeunix.net/software/ost/).  It uses a client/server protocol that has a very simple design, yet still manages to resist eavesdropping, man-in-the-middle attacks, and replay attacks.  Likewise, its implementation is so simple that it's resistant to denial-of-service and buffer overflow attacks, and lightweight enough that the author has run a client on a Palm handheld and a server on a Macintosh SE/30 (which makes it a pretty mature protocol as well!). I've created repos for the basic [C server and client](https://github.com/L2G/ostiary) and the [Java client](https://github.com/L2G/java-ostiary), and I've already squashed a bug in the latter.

I've started a stupid little project called [rubar](https://github.com/L2G/rubar) (etymology: "Ruby" + "fubar") that will allow for use of the social network/game [fubar.com](http://fubar.com/) from a command-line interface. It is designed to be a tool, not a robot.
