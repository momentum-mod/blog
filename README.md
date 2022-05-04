![](static/logo.png)

> Momentum Mod's [main blog website](https://blog.momentum-mod.org), compiled via [Hugo](https://gohugo.io/) and using the [PaperMod theme](https://github.com/adityatelange/hugo-PaperMod/).

## Motivation

The Momentum Mod blog was, for the longest time, hosted on Tumblr. Yes, *that* Tumblr.

Over the recent years, static site generation has not only become very easy to do, but coupled with GitHub or Cloudflare Pages, it has become extremely easy and extremely cheap (***FREE***) to host your own blog publicly. This, combined with the facts that:
1. We were never really using Tumblr to the fullest (social features like reblogging, or followers etc)
2. Tumblr took forever to load the posts (compared to the sub-1 second load time for the majority of this site)
3. Tumblr might not last forever, and if it goes/did go down, the entirety of our blog would disappear instantly (except *some* manual backups on Google Drive)

We're already using Jekyll for the [documentation website](https://docs.momentum-mod.org), but I always wanted to try out Hugo for something, and the blog was a perfect fit. I'm really enjoying it over Jekyll!

Since the blog is [very public](https://blog.momentum-mod.org), and given reason #3 above, there's no reason to *not* back it up publicly on GitHub, and potentially even allow people to contribute spelling/style fixes, so here we are!

## Making a Post

*Also known as "Here's how to use it, future me..."*

1. [Download Hugo](https://gohugo.io/getting-started/quick-start/) (and Go if you haven't already)
2. Clone this repo using `git clone --recursive` as there's the submodule for the theme (or use `git submodule update --init` if you already have it cloned)
3. You can then use hugo to serve locally with `hugo serve -D`
4. You can then use hugo to create a new page with `hugo new posts/name-of-post.md`
5. Pushing to main should deploy a new version on Cloudflare Pages

## Contributing

**The blog is an official Momentum Mod communications site, so any random articles by random contributors will be unfortunately rejected!**

However, any spelling or style-related issues can be fixed by direct contribution via this repository. Simply create a branch off of main and PR it in. It'll get reviewed and (hopefully, eventually) merged, and pushed directly to our blog site!