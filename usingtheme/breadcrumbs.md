---
layout: default
title: Breadcrumbs
---

The breadcrumb for the current page is created from the same data file as the [TOC](table_of_contents.html). 

Nothing "special" needs to be done, other than to remember:

* You can have the same URL at multiple places in the tree, but the breadcrumb will be the first time the url is found.
* Breadcrumbs link to the first item in the folder. If that item is a folder (rather than a page) then the folder will be shown as non-clickable.
* If the current page is the first item in a folder then the folder is not shown as a link.
* The current page is not shown as a link in the breadcrumb.
