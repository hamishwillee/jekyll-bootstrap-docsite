---
layout: default
title: Welcome
---

This site demonstrates a prototype mobile-friendly Jekyll *documentation* theme based on bootstrap. The site uses no plugins and can be (is) automatically built by Github's version of Jekyll.

Navigation is through a Table of Contents (TOC) sidebar, breadcrumb and navbar. The structure of these navigation elements is defined in data files, and can be automatically applied to articles based on their collection, parent folder, or in the page metadata. This allows multiple documentation sets to be built within a single site. The breadcrumb for the page is calculated from the TOC data structure.

The theme uses [bootstrap-sass](https://github.com/twbs/bootstrap-sass) (bootstrap-sass-official v3.2.0+2 from bower). This provides access to all the [standard bootstrap components](http://getbootstrap.com/components/) and means that the site appearance can be radically changed using the normal bootstrap variables.

Currently the project is a prototype; it is full of debug information and it lacks features that a real site might need (SEO integration, analytics, feedback mechanisms, search). Developers are welcome to extend or fork the project on [Github here](https://github.com/hamishwillee/jekyll-bootstrap-docsite/tree/gh-pages).


<div class="alert alert-success" role="alert"><p>This project borrows heavily from the <a href="https://sendgrid.com/docs/index.html">SendGrid Docs</a> theme, and uses the same CSS and JavaScript for the TOC. </p>

<p>SendGrid a "real" documentation set for a commerical product, and is hence more complete and robust than this project. One of its nicest features is that it uses plugins to generate the TOC and Breadcrumbs based on the folder structure of the source code (this can be much easier for authors to manage than an explicit TOC). It also uses an asset pipeline, which can result in significantly compressed CSS and javascript, along with better management of dependencies (I have chosen not to use that approach in order to allow this project to be built using Github's Jekyll).</p>
</div>



