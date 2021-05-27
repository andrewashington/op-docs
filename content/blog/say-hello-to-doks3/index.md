---
title: "This site is basically free"
description: "A quick description of building a lightweight documentation site for non-developers."
lead: "A quick description of building a lightweight documentation site for non-developers."
date: 2020-11-04T09:19:42+01:00
lastmod: 2020-11-04T09:19:42+01:00
draft: false
weight: 50
images: ["say-hello-to-doks.png"]
contributors: ["Andre Washington"]
---

## This site is free

Well, not completely free -- but closer to free than most non-engineering documentation sites out there. If I make a very small change... 

If you work in software, your product might have a documentation resource that looks a lot like this site. Engineering and API products are frequently make use of lightweight documentation resources like this one. 

Meanwhile, the average go-to-market team uses a mixture of the following for internal documentation and process descriptions:
- **Doc collaboration tools like** Google Docs
- **Intranet tools like** Google Sites, Sharepoint, etc. 
- **Some mixture of the above like** Notion, Confluence, etc.

These tools are actually all great. With some budget and buy in, you can put together documentation portals that are easy to navigate, fun to use, and invite collaboration across the org. 

The challenge is, for many of these, many business units need to get on board and agree to start getting the documentation ball rolling. Before you know it, you're wading through budget approvals and vendor evaluations. 

What I really hate about this phase is while all of this tool acquisition and adoption work is happening, you're distracted from the real task at hand: ironing out your business processes and writing them down.

For this personal project, this creates an even bigger problem. I cannot possibly hope to create ROI from OpDocs. 

## Tools for a docs site just like this

Here's the quick and dirty list of tools that made this site: 
1. [Hugo.](https://gohugo.io/) A static site generator that makes contributing here easy and fast.
2. [Netlify.](www.netlify.com) Makes it really easy to launch directly from my Github repo for the site.
3. [Doks for Hugo](https://themes.gohugo.io/doks/). Just a sleek Hugo starter for documentation sites.

This works for a public-facing site like this. I haven't scoped the work required, but [using Netlify and Auth0, you could theoretically implement authentication for your documentation.](https://www.netlify.com/technology-partners/auth0)

## I want docs like this for my internal business case

If you like this and could see your sales ops knowledgebase living on a site like this, there are basically two paths you can go down:

### Technical

If you have an beginners grasp of code, CLI, and Github, you could start a site like this in a matter of hours. 

### Non-Technical

If you're not comfortable at all with code, then a site like this might still be much easier to get started then getting budget and organization approval for a bigger software suite. 

Bribe an engineer and a product manager to look the other way, and this project could still take as little as an hour to get started. 