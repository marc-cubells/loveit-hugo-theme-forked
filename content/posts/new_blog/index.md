---
author: "Fabian Knecht"
title: "Welcome to the P-Tech Blog"
subtitle: "Why we started a blog and who's Hugo?"
description: "(Almost) everything you need to know about the new P-Tech Blog built with a static site generator"
date: "2023-10-03"

tags: ["blog", "hugo", "frameworks"]
header_img: "img/new_blog/hugo_bg.png"
toc: true
series: ["Themes Guide"]
comment: true

draft: false
---
:boom: P-Tech has its own blog :tada: and we're glad you found it :smiley:. Below a few words on the why, what and how of this blog. May it prosper!

### The *Why*

Before jumping into any activity, it's always good to ask yourself *Why* you're doing it. And that's not any different for a blog.

Here are the main resons why we think it's a great idea:
- A blog is a great way to **showcase and present our internal projects**. When working on something internally, whatever that maybe, nothing is more anticlimactic than finishing the project with some documentation probably no one will ever read. Sure, we often give presentations in meetings and while they're great (and we'll continue to do them), they are one-offs and only vaguely remembered in a few years time. A blog on the other hand allows us to have all these presentations in a central place where it's interesting to just browse and stumble over something we weren't necessarily looking for.
- A blog also allows us to **build a little knowledge base** consisting of 'how-to' articles that's both convenient and engaging. The blog is searchable and comes with a tagging system that makes it easy to retrieve information. It's also a much better place to store links and ressources than at the end of some slide decks scattered on Google Drive.
- Last but not least, anyone gets the opportunity to **hone their blogging skills**, both the writing/presenting skills as well as the technical skills (of using blogging frameworks, see below). You don't need to aspire to become a professional blogger but improving your writing, how to structure a short article and how to present a topic in an interesting and easy-to-understand way are skills anyone can benefit from. And just like for the internal presentations we do at Philico, with this blog we provide a safe space to practise them.


### The *What*

What we want to blog about has pretty much been answered above already. In short, the goal is to have a balanced mix of short presentations of interesting projects we've been working on, useful 'how-to' guides and posts about anything technical we find worth sharing. Feel free to pitch in with whatever it is you find interesting. Articles should be short and light. Don't aim for complete guides, its style should be colloquial. Think about what the most important points of your topic are and leave out the rest. Including only the things you find interesting enough to mention when casually talking about it to a friend. Everything else should simply be included in the links at the bottom of the post.

![My-blog](my-blog.gif)

### The *How* (or *Who*, as you wish)

OK. Now that you know why the world desparately needed this blog and what kind of content it will host, let's say a few words about how we go about things (technically speaking).

There are a gazillion ways to write and host a blog these days. Popular choices include platforms like [Medium](https://medium.com/) or website building tools like [Wix](https://www.wix.com/), [Webflow](https://webflow.com/?r=0) or [WordPress](https://wordpress.org/). All of them would be viable options but if you're looking for something cheap (free), convenient, flexible and very performant, static site generators are hard to beat.

"What are static site generators anyway?" I hear you say. They are basically "engines that use text input files to generate static web pages" (thank you [Wikipedia](https://en.wikipedia.org/wiki/Static_site_generator)). To simplify slightly, you:
- write your blog post in simple text files ([Markdown](https://www.markdownguide.org/))
- The engine then takes this content and runs it through template to generate HTML, ready to be hosted.

The separation of design (templates) and content (Markdown text files) is extremely convenient. It makes the writing process easier but also allows you change the design of your site easily.

Furthermore, static sites, once generated, do not require a backend which makes them very performant.

![Hugo](hugo-frame.png)

The original gangster in this space is [Jekyll](https://jekyllrb.com/), first released in 2008 by Tom Preston-Werner, founder and former CEO of GitHub. Today, there are many different frameworks available. We've opted for [Hugo](https://gohugo.io/), a SSG written in Go. It's open-source, extremely fast, a mature product with good documentation and tutorials, enjoys good support from most major web hosts, has a big developer community behind it and offers a big selection of themes to pick from. So what's not to like?

Marc has done some research and we've settled on the [Puppet theme](https://themes.gohugo.io/themes/hugo-theme-puppet/) to start off. It has some neat features, more than we need in fact. In order to be able to tweak it to our own liking we've forked the corresponding GitHub repository.

**We hope you're as excited as we are and that you can't wait to get your hands on this thing yourself!**

![We-want-you-blogging](we-want-you-blog-frame.png)

*Stay tuned: a step-by-step how-to guide describing the entire workflow (local installation of Hugo, cloning of the GitHub repo, adding a new post, testing it, pushing it back to GitHub etc.) will follow in due course.*

## References

### Courses and Tutorials
- [Quick start | Hugo](https://gohugo.io/getting-started/quick-start/)

### Links

- [Static site generator | Wikipedia](https://en.wikipedia.org/wiki/Static_site_generator)
- [The world’s fastest framework for building websites | Hugo](https://gohugo.io/)
- [P-Tech Blog repo | GitHub](https://github.com/philico-tech/ptech-blog)
