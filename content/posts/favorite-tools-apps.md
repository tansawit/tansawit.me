---
author: "Sawit Trisirisatayawong"
author_link: "https://tansawit.me"
title: "My Favorite Tools and Apps"
date: 2020-03-07T09:53:16+07:00
draft: true
description: "Optimizing for speed, productivity...and laziness."
categories:
  - tools
  - productivity

description_as_summary: true
show_in_homepage: true
featured_image: /images/favorite-tools-apps/featured.jpg
images:
- /images/favorite-tools-apps/featured.jpg
---

I use a lot of tools and apps on a daily basis, both for work and other computer-related tasks. Some of them are pretty standard (Xcode, Chrome, Sketch, Dropbox, etc.), others are personal preferences ([NeoVim](https://neovim.io/) (go-to text editor), [tmux](https://github.com/tmux/tmux) (terminal multiplexer), [alacritty](https://github.com/alacritty/alacritty) (terminal emulator)), and others just seems cool and useful to me. In this post, I wanted to highlight some of those in the third category that really had an impact on how I work or those that I think people might find useful. 

Alternatively, a complete list of all of the apps I use can be found on my [Github repo](https://github.com/tansawit/my-mac-setup) on the topic.

While this might come out more like a list than a proper blog post, I'll try to elaborate on each of the items as much as possible.

### [Alfred](https://www.alfredapp.com/): A more powerful Mac Spotlight

One of the reasons I initially fell in love with macOS was its amazing search using Spotlight. Then I found Alfred and was even more impressed by it. Apart from its built-in features, its [Workflows](https://www.alfredapp.com/workflows/) features allow for incredible extensibility. Some of these that I use most often are:

- [alfred-github-jump](https://github.com/lox/alfred-github-jump): Quickly search and open your repositories or those you starred in your default browser.
- [dash-alfred-workflow](https://github.com/Kapeli/Dash-Alfred-Workflow): Search and open Dash documentation sets through GitHub. (More on this below)
- [ask-create-share](https://github.com/nikitavoloboev/alfred-ask-create-share): Quickly create web submissions (GitHub repos/gist, Stack Exchange, Google Doc files, etc.)
- [alfred-localhost](https://github.com/simonguest/alfred-localhost): Open localhost with the input port in a new tab in the default browser

### [Dash](https://kapeli.com/dash): API and Language Documentation Browser

API Documentation browser for Mac. After combining it with [Alfred](https://www.alfredapp.com/), the [Dash Alfred workflow](https://github.com/Kapeli/Dash-Alfred-Workflow) and [Karabiner](https://pqrs.org/osx/karabiner/), it has become indispensable for me when looking up language libraries/functions and other things.

Demo:

{{<youtube dtvA35W1BvM>}}

### [Expressions](https://www.apptorium.com/expressions): Regular Expressions Sandbox

A really easy way to test and play with [Regular Expressions](https://en.wikipedia.org/wiki/Regular_expression) (regex) without having to think about specific language library libraries/functions/syntax. Simply enter the expressions and the test string(s). Plus I love the minimalistic and clean UI.

![Expressions RegEx](/images/lists/expressions.jpg)

### [Karabiner](https://pqrs.org/osx/karabiner/): Keyboard Customization

This tool completely changed the way I interact with my computer, and I personally feel a lot more productive with it. Beyond describing it as somewhat similar to Windows' [AutoHotKey](https://www.autohotkey.com/), being a kernel extension that gives you a virtual keyboard you can heavily customize, I don't exactly know how to describe it, so instead, I'll outline some of the keys and key combinations I've configured with it:

*Note: `x-y` means press key `y` while holding down `x`*

- `Caps Lock` now acts as my `esc` key. This greatly helps when I'm using (neo)vim (my main text/code editor) as I don't need to stretch as far or to try to find the virtual key on my MacBook's touchbar.
- `right command` brings up Alfred, instead of having to press the usual `command-space`
- `left command` quickly brings up the previous application, replacing the traditional `command-tab`

When combined with Alfred workflows or [Keyboard Maestro](https://www.keyboardmaestro.com/main/), it becomes even more powerful: 

- `n-f` brings up `alfred-github-jump`
- `n-a` brings up `ask-create-share`
- `l-c` brings up `alfred-localhost`

And so on. While it might seem like these improvements are minor, I assure you the time and effort saved is definitely noticeable over time. 

To that extent, I'm also only just getting started with exploring what it can do so for more information on Karabiner and combining it with other tools, I urge you to check out Nikita Voloboev's [post on the topic](https://medium.com/@nikitavoloboev/karabiner-god-mode-7407a5ddc8f6). He's how I got started on all of this whole customization and optimization thing as well.

### [Sip](https://sipapp.io/): Color Picker and Palette Manager

Whenever I needed to get the color value of some digital assets before, I've always used macOS's built-in Digital Color Meter. But I always ran into the issue of having no integrated way to store the retrieved colors, let alone multiple color sets or palettes. Sip solves these issues with its color palette manager, a more fully-fledged and easy to use the color picker, and cloud sync.

![Sip Color Palette Manager](/images/lists/sip.png)

### [TablePlus](https://tableplus.com/): GUI for SQL and NoSQL Databases

A really nice-looking and modern GUI for databases that supports quite [a lot of databases](https://docs.tableplus.com/#supported-databases), both SQL and NoSQL. Bonus points for having native apps for Mac and Windows. A really refreshing change coming from [Sequel Pro](http://sequelpro.com/). 

Some features are still incomplete/buggy though like the import functions seem to fail in some cases that Sequel Pro can handle. Plus I hope the app is a little less expensive, but then again I'm using it through my [SetApp subscription](https://setapp.com/). Ultimately, I still think it's completely worth it for anyone who works a lot with databases.

![TablePlus UI (Light Mode)](/images/lists/tableplus.png)

### [Vimac](https://vimacapp.com/): Vim-like Mac Navigation

After falling down the Vim rabbit-hole, I've been trying to find ways to use Vim-based/keyboard-only navigations in as many contexts as possible. And other than my terminal, the two contexts that I normally use my mouse are in my browser (Chrome) and general app/program navigation. Having found [Surfingkeys](https://github.com/brookhong/Surfingkeys) for Chrome, I tried to find a similar solution for general application and interface navigation. Thus, enters Vimac.

The app allows you to assign a hotkey which, once pressed, will show a layer of shortcut keys over any recognized clickable elements on the screen (example below). After pressing the desired key combination, the app will simulate a mouse click on that element. Even though the app seems to work pretty well most of the time, its beta status definitely shows. Sometimes the assigned keyboard shortcut does not register, and some places that are buttons/navigation are not recognized. But overall I'm definitely happy with it.

![Vimac Demo on the Finder Applications folder](/images/lists/vimac.png)

## Wrapping Up

Again these are just some of the apps that are particularly useful or interesting to me. For a complete and updated list of all of the tools I use, please see my [GitHub repo](https://github.com/tansawit/my-mac-setup) on the topic.

If you have any questions, want to discuss something, or just want to talk, you can always reach me through my [Twitter](https://twitter.com/tansawit).
