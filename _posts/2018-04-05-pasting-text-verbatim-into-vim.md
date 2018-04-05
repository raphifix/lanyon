---
published: true
layout: post
tags: vim TIL
---
It is possible to paste directly into Vim without changing anything inside Vim, but it will auto-indent the text (which you may not want). Here's how to avoid this.

Make sure you're in command mode. If you're not, press `Esc` on your keyboard.

Type `:set paste` and then `Enter`. Then type `i` to go back into insert mode. After pasting your text, you can re-enable auto-indenting by going back into command mode and typing `:set nopaste` and `Enter`.
