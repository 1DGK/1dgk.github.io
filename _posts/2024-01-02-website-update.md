---
layout: post
title: How I run my Jekyll site locally on Windows
category: website
tags: linux jekyll windows
---

I got it working. I'm now able to run my site locally on Windows. Here's how I did it:

```sh
apt install bundle
apt install ruby
apt install jekyll
```

cd into site directory

```sh
bundle exec jekyll serve
```

I ran into problems before, but it ran without a hitch this time. 

Except you get this warning about how the auto-regenerate function might not work.

A bit of google-fu and I found this add-on to the command:

```sh
bundle exec jekyll serve --force_polling
```

And that did the trick!

P.S. I forgot that there's an extension for this exact thing. It's called Live Server. I could've saved myself a lot of headache, but that's okay. 


---

So, to update my website from Windows, I use the following:

- VSCode
    - It's easy to create new files and update them through the source control window
    - I also run a terminal with wsl so I can run the site locally

- Github Desktop
    - This is like a fall-back option, in case I forget how to do everything from the terminal or VSCode

- Windows Subsystem for Linux (wsl)
    - I run Ubuntu

---

I continue to struggle with footnotes in Jekyll / markdown. Not the end of the world, but it shouldn't be this annoying. 