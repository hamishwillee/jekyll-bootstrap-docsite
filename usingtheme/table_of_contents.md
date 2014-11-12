---
layout: default
title: Table of contents (sidebar)
---

The sidebar table of contents (TOC) is a [CSS](https://github.com/hamishwillee/jekyll-bootstrap-docsite/blob/gh-pages/_sass/_navtree.scss) and [JavaScript](https://github.com/hamishwillee/jekyll-bootstrap-docsite/blob/gh-pages/source/assets/javascripts/CollapsibleLists.compressed.js) component created by [Stephen Morley](http://code.stephenmorley.org/) and released under the terms of the CC0 1.0 Universal legal code. 

The TOC structure is defined in a yml file in **/_data/** (e.g. [toc.yml](https://github.com/hamishwillee/jekyll-bootstrap-docsite/blob/gh-pages/_data/toc.yml)) and [assigned to the page](setting_nav_defaults.html) ```toc``` variable. 

The yml "structure" for a basic tree is shown below.  Top level links are specified using a ```url``` variable for the target. You can optionaly specify the ```name``` to display for the link. 

<div class="alert alert-success" role="alert"><p>Note that the system will fetch the name for a valid document, but you will need to define the name for external links.</p></div>

{% highlight yaml %}
- folder: A folder
  contents:
   - url: /usingtheme/adoc.html
   - url: /usingtheme/adoc2.html

   - folder: Nested
     contents:
      - url: /usingtheme/somedoc.html
      - url: /usingtheme/somedoc2.html


- folder: A peer folder
  contents:
   - url: /test_collection/collection_test1_1.html
     name: Collection

   - url: /test_section/section_test1_1.html
     name: Section (folder)
{% endhighlight %}

Folders (and nested folders) are specified using the ```folder``` variable, with the individual urls defined as a yaml list under the ```contents``` variable as shown above.  

<div class="alert alert-warning" role="alert"><p>The toc structure and parsing code can be nested to any depth. However at a depth of about 4 folders the CSS will no longer work properly and would need to be updated.</p>
</div>

The appearance and colours can be changed by altering navtree variables in [/css/main.scss](https://github.com/hamishwillee/jekyll-bootstrap-docsite/blob/gh-pages/css/main.scss).
