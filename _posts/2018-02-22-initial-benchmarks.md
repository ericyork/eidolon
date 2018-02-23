---
layout: post
title:  "Initial Benchmarks"
date:   2018-02-22 19:37:16 -0500
categories: dev-docs
---

One of the primary goals of this site build is to create a framework for developing sites that consistently score highly on various metrics, but especially Google's [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/).

Key components of this quest:
+ serve optimized images and compressed (gzip) files
+ remove render-blocking scripts and styles (i.e. inline critical-path CSS and asynchronously load the remainder)
+ leverage browser caching
+ minify my CSS and JS (maybe HTML too)


In order to achieve this, I'll be capturing benchmarks after theme updates to track my progress.

### Initial Benchmarks

Without furter ado, here they are.

#### Mobile

<a href="{{ "/assets/images/mobile-bench-2-22-18.png" | absolute_url }}">![Trial Title]({{ "/assets/images/mobile-bench-2-22-18.png" | absolute_url }})</a>

So . . . a 75%. That's a solid C. Not great, but on the other hand, not too bad. Higher than some of my other projects, unfortunately. That said, most deployment goals are at this time unmet and the site contains basically no content of any real size.

#### Desktop

<a href="{{ "/assets/images/desk-bench-2-22-18.png" | absolute_url }}">![Trial Title]({{ "/assets/images/desk-bench-2-22-18.png" | absolute_url }})</a>

An 82% is like a B—. Many of the same issues with mobile are also present with desktop, as you'd expect. The good news there is that fixing most of the items will improve both scores simultaneously.

### The Big Take Away

Not much to conclude here, other than that I've got a working system and the first data point in the graph. Since there is little site content to gum up the works, and since I've not incorporated many of the build steps to extract styles and scripts, compress images and files, etc., there's really no way to tell how predictive these benchmarks are of anything at all. :(
