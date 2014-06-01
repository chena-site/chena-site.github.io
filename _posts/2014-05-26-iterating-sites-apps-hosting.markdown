---
layout: post
title: "Frugal Development : Iterating Online Websites/Apps"
tags: web static-sites
categories: websites hosting
date: 2014-05-26
---

In the past, the classic way of iterating over web apps/sites on the web (other than a local Apache/Nginx server) was utilizing free hosting services (assuming no budget). It's 2014 and the trends have changed tremendously over the past decade. I moved my site to using Jekyll and Github Pages recently, and it led me to reflect on what I saw in the market over the years with respect to solutions for sites on very low/nearly no budget.

## The Sites of Yester-decade :

For pure HTML sites, getting an initial iteration over a free/ultra-low cost host was simple, as long as the HTTP service was equipped to handle the load.

Many of my first sites that required some essence of dynamicness were originally written in PHP (since this is what most of the free hosts had always used), prior to me discovering or being able to utilize PaaS (Platform-As-A-Service). Many free webhosts had their incarnation based off of the popular CPanel, which easily allowed for a newbie like me to configure parked/addon domains, subdomains, and other things with simple clicks. If one wanted to be fancy, one would pick (Joomla, Wordpress, or Drupal) and start from there. This trend is still pretty apparent today, given the popularity and widespread use of PHP CMS systems.

There was a point in time where file-size constraint unlimited free hosting was extremely popular (e.g. Max file size of 15MB). One had to be wary of the caveats (such as ads) of using such a service. Many hosting companies, under the guise of eBay unlimited reseller accounts, came and go during this period. Shared resources would be often oversold though it was still fine for relatively low-traffic websites.

The first iteration of this site was written in PHP, which was later ported to Node.js on Heroku.

## Enter 2014

Today, there seems to be many more (and better) options on the market.

- *Heroku* - Platform-as-a-Service (PaaS) that has a free-tier that offers one virtual instance per application. With the use of Heroku buildpacks + Nginx, it's possible for one to run multiple sites on a single application instance. Compared to the CPanel/FTP days, assuming one has to configure Nginx for their needs, the learning curve for doing so can be a little steeper in the beginning. A custom domain can be assigned via CNAME records to point to the particular application instance. Heroku supports other web application stacks such as PHP/Node.js/Ruby/Golang/Python and more.

- *Github Pages* - An account includes one instance of Github Pages, which allows one to host a static site. Compared to Heroku, Github Pages only accepts fully static content or a Jekyll setup. Jekyll is a static site generator that helps with making static sites very simple and easy. It's definitely easier than Heroku to set up, but may still be initially a bit more difficult compared to tried and tested CPanel. Github Pages also allows one to assign a CNAME record to a particular instance of a site.

- *000Webhost/ Byethost / X10Hosting* - These are the free hosts that have survived over the last half-decade or so. They aim to be fairly user-friendly to site administrators, but the drawbacks tend to include: PHP-only or their free Servers commonly used for Spam/Phlishing (and hence may be blocked by some Internet Service Providers), Speeds are much more variable compared to Heroku/Github Pages

- *DigitalOcean* - Servers on the cloud. Their lowest tier instance starts at $5/month, which affords one a very generous offering of server resources. Compared to a Heroku instance, the level of involvement (and also the level of control) for getting a site up can be much more substantial compared to PaaS offerings, Github Pages, or traditionally free/shared hosting environments.

I had initially ran my own personal site on an Heroku instance with Node.js. Like many others, the instance spin-up time after idle inactivity irritated me from time to time, so I sought something better than just pinging my site once every 55 minutes. Here comes Jekyll/Github Pages.

Jekyll (using 1.5 at this time in writing), in its stock configuration, allows one to easily architect a site (much like how it is done through raw HTML) without any headaches and contains features that would allow one to easily run a news site/blog.

## Reliability

It's not enough to simply cross one's fingers and hope for at least 99.9% uptime, especially when services like CloudFlare exists to optimize static content delivery and provide basic intrusion protection to sites that are live on the web. In my particular use case, it has been convenient to use Cloudflare also for their DNS management features. Waiting for DNS changes to propagate through the web used to be rather painful and potentially time-consuming.

## Closing

The number of low-cost/free options has improved/certainly expanded over the past decade. For the frugal/no-budget developers/webmasters , the use of Heroku/Github Pages (depending on the situation) coupled with Cloudflare is certainly one of the best deals one doesn't have to use money to buy.
