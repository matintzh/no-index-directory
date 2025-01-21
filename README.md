# no-index-directory
# How to Make a Directory (or Sub-Folder & Sub-Domain) No-Index

## Overview

In SEO and web development, it’s crucial to control which pages or directories of your website are indexed by search engines. There are multiple ways to prevent specific directories, sub-folders, or even entire sub-domains from being indexed by search engines like Google. This repository provides comprehensive solutions for achieving this by using different methods, such as:

- **robots.txt file**
- **Meta Tag**
- **.htaccess file**
- **Google Search Console**
- **WordPress settings**

These methods are widely used by developers, SEO professionals, and website owners to maintain control over their site's visibility in search engine results.

## Introduction

This repository demonstrates how to stop search engines from indexing specific directories, sub-folders, or sub-domains using a variety of tools and techniques. It's essential to implement a "no-index" directive when you want to keep certain content private, avoid duplicate content issues, or prevent low-quality pages from affecting your website's SEO performance.

## Methods to Prevent Indexing

### 1. robots.txt

The **robots.txt** file is the most common method for controlling web crawlers’ access to specific parts of your site. This file can be used to disallow search engines from indexing entire directories or sub-domains.
 - Navigate to the root directory of your subdomain
 - Create or edit a file named robots.txt
 - Add the following lines to the file
#### Simple example
```txt
User-agent: *
Disallow: /
```
Below code is for the times that in your directory you have multiple things and u want to specify the no-index url
for example in your directory you have a folder that you want to only no-index that (private-directory)
```txt
User-agent: *
Disallow: /private-directory/
```


### 2. Add a Meta Tag for No-Indexing
If you have access to the HTML files or templates of your subdomain, include this <meta> tag in the <head> section of each page:
```html
<meta name="robots" content="noindex, nofollow">
```


### 3. Use .htaccess for Apache Servers
If your subdomain runs on an Apache server, edit the **.htaccess** file in the subdomain's root directory.
Add the following code to apply the X-Robots-Tag header:
```txt
<IfModule mod_headers.c>
    Header set X-Robots-Tag "noindex, nofollow"
</IfModule>
```
This ensures search engines avoid indexing the subdomain entirely


### 4. Configure in cPanel or Hosting Dashboard
Some hosting providers allow you to set no-index options for subdomains directly in their dashboard. Check your hosting control panel for any such settings.


### 5. Block the Subdomain in Google Search Console
If your subdomain is already indexed , you can do it through google search console
 - navigate to **Removals** tool in search console
 - submit the directory

### 6. Prevent Indexing Using WordPress
if you're using Wordpress . follow below steps:
 - Go to Settings > Reading
 - Check the option: Discourage search engines from indexing this site
 - Save changes
