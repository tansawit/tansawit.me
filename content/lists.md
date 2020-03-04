---
title: "Lists"
---

A collection of things I am currently watching/reading/listening/using etc.

## Tools/Apps
I use [a lot of tools and apps](https://github.com/tansawit/my-mac-setup) on a daily basis, both for work and other computer-related tasks. Some of them are pretty standard (Xcode, Chrome, Sketch, Dropbox, etc.), others are personal preferences ([NeoVim](https://neovim.io/), [tmux](https://github.com/tmux/tmux)), and others are just seems cool and useful to me. 

### [Alfred](https://www.alfredapp.com/): A more powerful Mac Spotlight

One of the reasons I initially fell in love with macOS was its amazing search using Spotlight. Then I found Alfred and was even more impressed by it. Apart from its built-in features, its [Workflows](https://www.alfredapp.com/workflows/) features allow for incredible extensibility. Some of these that I use most often are:

- [alfred-github-jump](https://github.com/lox/alfred-github-jump): Quickly search and open your repositories or those you starred in your default browser.
- [dash-alfred-workflow](https://github.com/Kapeli/Dash-Alfred-Workflow): Search and open Dash documentation sets through GitHub. (More on this below)
- [ask-create-share](https://github.com/nikitavoloboev/alfred-ask-create-share): Quickly create web submissions (GitHub repos/gist, Stack Exchange, Google Doc files, etc.)
- [alfred-localhost](https://github.com/simonguest/alfred-localhost): Open localhost with the input port in a new tab in the default browser

### [Dash](https://kapeli.com/dash): API and Language Documentation Browser

API Documentation browser for Mac. After combining it with [Alfred](https://www.alfredapp.com/), the [Dash Alfred workflow](https://github.com/Kapeli/Dash-Alfred-Workflow) and [Karabiner](https://pqrs.org/osx/karabiner/), it has been indispensable for me when looking up language libraries/functions and other things.

Demo:

{{<youtube dtvA35W1BvM>}}

### [Expressions](https://www.apptorium.com/expressions): Regular Expressions playground

A really easy way to test and play with [Regular Expressions](https://en.wikipedia.org/wiki/Regular_expression) (regex) without having to think about specific language library libraries/functions/syntax. Simply enter the expressions and the test string(s). Plus I love the minimalistic and clean UI.

![Expressions RegEx](/images/lists/expressions.jpg)

### [Karabiner](https://pqrs.org/osx/karabiner/): Keyboard Customization

This tool completely changed the way I interact with my computer, and I personally feel a lot more productive with it. Beyond describing it as somewhat similar to Windows' [AutoHotKey](https://www.autohotkey.com/), being a kernel extension that gives you a virtual keyboard you can heavily customize, I don't exactly know how to describe it, so instead, I'll outline some of the keys and key combinations I've configured with it:

*Note: `x-y` means press key `y` while holding down `x`*

- `Caps Lock` now acts as my `esc` key. This greatly helps when I'm using NeoVim (my main text/code editor) as I don't need to stretch as far or try to find Mac's virtual key on the trackpad.
- `left command` brings up Alfred, instead of having to press two or more key
- `right command` replaces the traditional `command-tab` or `alt-tab`, again minimizing the keys I have to press

When combined with Alfred workflows or [Keyboard Maestro](https://www.keyboardmaestro.com/main/), it becomes even more powerful: 

- `n-f` brings up `alfred-github-jump`
- `n-a` brings up `ask-create-share`
- `l-c` brings up `alfred-localhost`

And so on. While it might seem like these improvements are minor, but I assure you the time and effort saved is definitely noticeable over time. 

To that extent, I'm also only just getting started with exploring what it can do so for more information on Karabiner and combining it with other tools, I urge you to check out Nikita Voloboev's [post on the topic](https://medium.com/@nikitavoloboev/karabiner-god-mode-7407a5ddc8f6). He's how I got started on all of this workflow customization and optimization thing as well.

### [Sip](https://sipapp.io/): Color Picker and Palette Manager
Whenever I needed to get the color value of some digital assets before, I've always used macOS's built-in Digital Color Meter app. But I always ran into the issue of having no integrated way to store the retrieved colors, let alone multiple color sets or palettes. Sip solves these issues with its color palette manager, a more fully-fledged and easy to use the color picker, and cloud sync.

![Sip Color Palette Manager](/images/lists/sip.png)

### [TablePlus](https://tableplus.com/): GUI for SQL and NoSQL Databases

A really nice-looking and modern GUI for databases that supports quite [a lot of databases](https://docs.tableplus.com/#supported-databases), both SQL and NoSQL. Bonus points for having native apps for Mac and Windows. A really refreshing change coming from [Sequel Pro](http://sequelpro.com/). 

Some features are still incomplete/buggy though like the import functions seem to fail in some cases that Sequel Pro can handle. Plus I hope the app is a little less expensive, but then again I'm using it through my [SetApp subscription](https://setapp.com/). Ultimately, I still think it's completely worth it for anyone who works a lot with databases.

Oh, and it has dark mode support!

![TablePlus UI (Light Mode)](/images/lists/tableplus.png)

### [Vimac](https://vimacapp.com/): Vim-like Mac Navigation

After falling down the Vim rabbit-hole, I've been trying to find ways to use Vim-based/keyboard-only navigations in as many contexts as possible. And other than my terminal, the two contexts that I normally use my mouse are in my browser (Chrome) and general app/program navigation. Having found [Surfingkeys](https://github.com/brookhong/Surfingkeys) for Chrome, I tried to find a similar solution for general application and interface navigation. Thus, enters Vimac.

The app allows you to assign a hotkey which, once pressed, will show a layer of shortcut keys over any recognized clickable elements on the screen (example below). After pressing the desired key combination, the app will simulate a mouse click on that element. Even though the app seems to work pretty well most of the time, its beta status definitely shows. Sometimes the assigned keyboard shortcut does not register, and some places that are buttons/navigation are not recognized. But overall I'm definitely happy with it.

![Vimac Demo on the Finder Applications folder](/images/lists/vimac.png)
## Books

### Philisophy 

- [Tao Te Ching](https://www.amazon.com/gp/product/0679724346?ie=UTF8) - The one book that I’m sure that I’ll reread on and on: each time learning and understanding something new from it. For such a small book, the idea it presents, and the way it is presented is absolutely unmatched.

## Podcasts

- [a16z Podcast](https://www.listennotes.com/podcasts/a16z-podcast-andreessen-horowitz-IWF2alEr-9h/): Podcast by Silicon-Valley-based venture capital firm [Andreessen Horowitz](https://a16z.com/) discussing tech/culture/trends/news and the future.
- [Aritificial Intelligence Podcast](https://www.listennotes.com/podcasts/artificial-intelligence-ai-podcast-with-lex-YRs7Zkd0n4l/): By MIT researcher [Lex Fridman](https://twitter.com/lexfridman). Conversations about technology, science, and the human condition
- [The Knowledge Project](https://www.listennotes.com/podcasts/the-knowledge-project-with-shane-parrish-RoXxgNCyDmE/): Interviews by [Shane Parrish](https://twitter.com/ShaneAParrish) with experts in various fields.
- [My First Million](https://www.listennotes.com/podcasts/my-first-million-the-hustle-shaan-puri-Vmz8LP7xJOS/): Conversations with millionaires on their stories and strategies behind their success
- [Waveform Podcast](https://www.listennotes.com/podcasts/waveform-the-mkbhd-podcast-studio71-vliqrx6DSMG/): Tech podcast by Youtuber [MKBHD](https://www.youtube.com/user/marquesbrownlee) discussing gadgets and technology.
