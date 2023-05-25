---
layout: post
title: IRC FTW!
categories:
- cli
tags: []
---

#What is IRC? A chat protocol.

####Why would you want to use it?

+ it is free!
+ supports file transfer
+ has clients for every platform
+ is super efficient
+ many networks, public and private

IRC is amazing for learning and asking questions. Say, for instance, you are learning the Ruby programming language. The *official* ruby language IRC channel exists on irc.freenode.net

I've spent years fiddling around with IRC, have settled on a wonderful commandline client, and am happy to share my configuration with the world.

**On a mac with homebrew installed, this guide should be easy to follow.** If you're using linux, the instructions should make sense and you can still use my config.

**If this command-line stuff feels scary..  I feel bad for you, son.** I got 99 problems, but IRC aint one. You might want to take a look at [Colloquy](http://colloquy.info/), it's self explanatory.


#Let's get started
If you don't have homebrew installed, [follow the official instructions](http://brew.sh/)

Open up your terminal and type in ```brew install irssi```
Congratulations! You now have the best irc client!!

You can totally use it, as is, but I recommend tweaking the settings a bit.

Load irssi for the first time by typing in ```irssi```. This will create the default configuration files that we will be editing. ```/quit``` to exit.

####Themes make things pretty!

1. [find a theme you like](http://irssi.org/themes)
2. copy the .theme link
3. in terminal run ```wget -P ~/.irssi copied_link``` to install theme (if wget doesn't work, simply run ```brew install wget```)
4. load up irssi and run ```/set theme theme_name```
5. ```/save```

####Scripts make life easier!
*Lets set up a highlight window*, this will log every time someone mentions your name:

1. in terminal run ```wget -P ~/.irssi/scripts/autorun/ http://static.quadpoint.org/irssi/hilightwin.pl```
2. load up irssi
3. we're going to set up a split window to view the hilights
4. ```/window new split```
5. ```/window name hilight``` this name is important so the script knows where to send the info
6. ```/window size 4```
7. ```/hilight -word yournick```
8. ```/help hilight``` for advanced features.
9. ```/layout save``` to save this configuration

*Advanced Windowlist!* install the same way as hilight:

1. ```wget -P ~/.irssi/scripts/autorun/ http://anti.teamidiot.de/static/nei/*/Code/Irssi/adv_windowlist.pl```
2. load up irssi
3. to see all available settings for type ```/set awl```

*Usercount* displays the number of users in the channel

1. I think you know the drill by now
2. http://scripts.irssi.org/scripts/usercount.pl

#Configuration is unlimited
*I'll make it easy for the world by sharing my config file.*

Exit out of irssi by typing it ```/quit```

Lets open the config file ```open ~/.irssi/config```

Copy what you like. Be careful with formatting...

1. find YOURNAME and replace with your own nickname
2. find THEMENAME and replace with your installed theme

```bash
  servers = (
    {
      address = "irc.freenode.net";
      chatnet = "freenode";
      port = "7000";
      use_ssl = "yes";
      ssl_verify = "no";
      autoconnect = "yes";
    }
  );

  chatnets = {
    freenode = { type = "IRC"; };
  };

  channels = (
    { name = "#ruby"; chatnet = "freenode"; autojoin = "yes"; },
    { name = "#ruby-lang"; chatnet = "freenode"; autojoin = "yes"; },
    { name = "#kickhash"; chatnet = "freenode"; autojoin = "yes"; }
  );

  aliases = {
    J = "join";
    WJOIN = "join -window";
    WQUERY = "query -window";
    LEAVE = "part";
    BYE = "quit";
    EXIT = "quit";
    SIGNOFF = "quit";
    DESCRIBE = "action";
    DATE = "time";
    HOST = "userhost";
    LAST = "lastlog";
    SAY = "msg *";
    WI = "whois";
    WII = "whois $0 $0";
    WW = "whowas";
    W = "who";
    N = "names";
    M = "msg";
    T = "topic";
    C = "clear";
    CL = "clear";
    K = "kick";
    KB = "kickban";
    KN = "knockout";
    BANS = "ban";
    B = "ban";
    MUB = "unban *";
    UB = "unban";
    IG = "ignore";
    UNIG = "unignore";
    SB = "scrollback";
    UMODE = "mode $N";
    WC = "window close";
    WN = "window new hide";
    SV = "say Irssi $J ($V) - http://irssi.org/";
    GOTO = "sb goto";
    CHAT = "dcc chat";
    RUN = "SCRIPT LOAD";
    CALC = "exec - if command -v bc >/dev/null 2>&1\\; then printf '%s=' '$*'\\; echo '$*' | bc -l\\; else echo bc was not found\\; fi";
    SBAR = "STATUSBAR";
    INVITELIST = "mode $C +I";
    Q = "QUERY";
    "MANUAL-WINDOWS" = "set use_status_window off;set autocreate_windows off;set autocreate_query_level none;set autoclose_windows off;set reuse_unused_windows on;save";
    EXEMPTLIST = "mode $C +e";
    ATAG = "WINDOW SERVER";
    UNSET = "set -clear";
    RESET = "set -default";
  };

  statusbar = {
    # formats:
    # when using {templates}, the template is shown only if it's argument isn't
    # empty unless no argument is given. for example {sb} is printed always,
    # but {sb $T} is printed only if $T isn't empty.

    items = {
      # start/end text in statusbars
      barstart = "{sbstart}";
      barend = "{sbend}";

      topicbarstart = "{topicsbstart}";
      topicbarend = "{topicsbend}";

      # treated "normally", you could change the time/user name to whatever
      time = "{sb $Z}";
      user = "{sb {sbnickmode $cumode}$N{sbmode $usermode}{sbaway $A}}";

      # treated specially .. window is printed with non-empty windows,
      # window_empty is printed with empty windows
      window = "{sb $winref:$tag/$itemname{sbmode $M}}";
      window_empty = "{sb $winref{sbservertag $tag}}";
      prompt = "{prompt $[.15]itemname}";
      prompt_empty = "{prompt $winname}";
      topic = " $topic";
      topic_empty = " where the cool kids hang out ";

      # all of these treated specially, they're only displayed when needed
      lag = "{sb Lag: $0-}";
      act = "{sb Act: $0-}";
      more = "-- more --";
    };

    # there's two type of statusbars. root statusbars are either at the top
    # of the screen or at the bottom of the screen. window statusbars are at
    # the top/bottom of each split window in screen.
    default = {
      # the "default statusbar" to be displayed at the bottom of the window.
      # contains all the normal items.
      window = {
        disabled = "no";

        # window, root
        type = "window";
        # top, bottom
        placement = "bottom";
        # number
        position = "1";
        # active, inactive, always
        visible = "active";

        # list of items in statusbar in the display order
        items = {
          barstart = { priority = "100"; };
          time = { };
          user = { };
          window = { };
          window_empty = { };
          lag = { priority = "-1"; };
          more = { priority = "-1"; alignment = "right"; };
          barend = { priority = "100"; alignment = "right"; };
          usercount = { };
        };
      };

      # statusbar to use in inactive split windows
      window_inact = {
        type = "window";
        placement = "bottom";
        position = "1";
        visible = "inactive";
        items = {
          barstart = { priority = "100"; };
          window = { };
          window_empty = { };
          more = { priority = "-1"; alignment = "right"; };
          barend = { priority = "100"; alignment = "right"; };
        };
        disabled = "yes";
      };

      # we treat input line as yet another statusbar :) It's possible to
      # add other items before or after the input line item.
      prompt = {
        type = "root";
        placement = "bottom";
        # we want to be at the bottom always
        position = "100";
        visible = "always";
        items = {
          prompt = { priority = "-1"; };
          prompt_empty = { priority = "-1"; };
          # treated specially, this is the real input line.
          input = { priority = "10"; };
        };
      };

      # topicbar
      topic = {
        type = "root";
        placement = "top";
        position = "1";
        visible = "always";
        items = {
          topicbarstart = { priority = "100"; };
          topic = { };
          topic_empty = { };
          topicbarend = { priority = "100"; alignment = "right"; };
        };
      };
      awl_0 = {
        items = {
          barstart = { priority = "100"; };
          awl_0 = { };
          barend = { priority = "100"; alignment = "right"; };
        };
      };
      awl_1 = {
        items = {
          barstart = { priority = "100"; };
          awl_1 = { };
          barend = { priority = "100"; alignment = "right"; };
        };
      };
      awl_2 = {
        items = {
          barstart = { priority = "100"; };
          awl_2 = { };
          barend = { priority = "100"; alignment = "right"; };
        };
      };
    };
  };
  settings = {
    core = {
      real_name = "YOURNAME";
      user_name = "YOURNAME";
      nick = "YOURNAME";
    };
    "fe-text" = { actlist_sort = "refnum"; };
    "fe-common/core" = { theme = "THEMENAME"; };
    "perl/core/scripts" = {
      awl_block = "0";
      awl_display_key = "$Q%K|$H$C$S";
      awl_display_key_active = "$Q%K|$H%U$C%n$S";
      awl_display_nokey = "[$N]$H$C$S";
      awl_height_adjust = "2";
    };
  };
  ignores = (
    {
      level = "JOINS PARTS QUITS NICKS";
      channels = (
        "#ruby",
        "#ruby-lang",
        "#kickhash"
      );
    }
  );
```

#### How to Navigate

* ```/s server.address``` to connect to a server
* ```/j #channel``` to join a channel
* ```/msg nick``` to send a private message
* ```escape [channel number]``` to switch channels
* in the status window ```ctrl x``` changes the server you are interacting with
* ```/quit``` exits irssi
