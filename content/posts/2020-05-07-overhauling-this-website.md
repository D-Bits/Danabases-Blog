---
title: Overhauling This Website
publishdate: 2020-05-11T00:16:11.299Z
tags:
  - other
draft: true
---
For those of who have been following this blog for a while now, you will have noticed I completely overhauled my website/blog to have an entirely new design, along with a new domain name, and a new hosting service. In this blog post, I would like to go over how I went about overhauling the website, as well as my reasons for doing so.

## Why?

In the previous iteration, this blog was built on Jekyll, and hosted on GitHub Pages, without a custom domain. While that setup worked out well enough for starting out, I found myself in the market for a different static site generator, and consequently, a new service to host my website. While Jekyll served my needs well enough for the short term, I increasingly found that my lack of Ruby knowledge was making things difficult for me. Furthermore, as this was the only Ruby project I have ever worked on, I didn't really have much incentive to immerse myself in the language. 

## Choosing a Static Site Generator

With this in mind, I set out on finding a new static site generator. The two main alternatives to Jekyll that I looked at were Pelican and Hugo. While Pelican certainly appealed to me, being a Pythonista and all, I ultimately decided to opt for Hugo, due to the fact that didn't require any setup or configuration (other than downloading and installing a binary), it's extensive selection of themes, as well as its incredibly fast, and auto-reloading, development server.  

## Building the Website

With a choice of a new static site generator made, I set out to redevelop my website. Ultimately, I do not consider myself a front-end web developer, or any kind of expert on CSS. Therefore, rather than code the entire website from scratch, I made to choose to use one of Hugo's pre-built themes from their [gallery](https://themes.gohugo.io/tags/gallery/). Eventually, I settled on a rather nice theme called [Notepadium](https://themes.gohugo.io/hugo-notepadium/).

## Hosting

Since GitHub Pages is powered by Jekyll, which I am no longer using, I found myself in need of a new hosting service. For static website, I found the most ideal option to be Netlify. Netlify not only allows you to host static sites for free, but also allows you to easily add a lot of functionality to them, that would normally be associated with web applications. 

## Final Thoughts

Currently, I am quite satisfied with the new setup. Although I still have a lot to learn about Hugo, and everything I can do with it, I found it pretty easy to get started with. Furthermore, while the theme I choose was pretty nice