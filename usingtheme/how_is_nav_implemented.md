---
layout: default
title: Implementation
---

The navigation is implemented using a number of [_include](https://github.com/hamishwillee/jekyll-bootstrap-docsite/tree/gh-pages/_includes) files (the interesting files are mostly in [_includes/functions](https://github.com/hamishwillee/jekyll-bootstrap-docsite/tree/gh-pages/_includes/functions)). 

The [Liquid templating language](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers) allows you to query the page variables to get the desired ```toc``` and ```navmenu``` (either defined in the page or in the Front Matter defaults). When the variable is retrieved it is a *string*, so we compare this string against the name of each of the data files in ```site.data``` to get a handle to the desired menu or toc.

<div class="alert alert-warning" role="alert"><p>It is not possible in Jekyll to specify and get the toc variable directly in the Front Matter, which is why we find the correct object by iterating <b>site.data</b>. If you're willing to use plugins, you can use variables in front matter and other yaml <a href="https://github.com/gjtorikian/jekyll-conrefifier">using a plugin</a>.  </p></div>

Once we have the ```toc``` and ```navmenu``` we pass it into the appropriate functions to iterate the tree structure and generate the appropriate HTML for our CSS. The best way to understand the code is to review it, but there are some things to keep in mind:

* **f_navtree_open.html** is called to find the folder-path to the first intance of the current document. This is what defines the breadcrumb, and is also used to work out and mark which TOC folder path needs to be opened up when the page is loaded. After the "open path" has been worked out, this is passed into the navtree function with the toc variable to render the toc.
* It might not immediately be obvious, but included files are FUNCTIONS. You can call them recursively, and you can use them to return objects (and capture the result). This allows the HTML for a tree to be called recursively with progressively smaller tocs.
* Care needs to be taken with scope of variables for nested function calls.
