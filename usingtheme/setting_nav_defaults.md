---
layout: default
title: Setting navigation elements used by a page
---

The navigation elements (TOC, navmenu) are typically set using the ```toc``` and ```navmenu``` page variables in the [Front Matter Defaults](http://jekyllrb.com/docs/configuration/#front-matter-defaults) (or for a particular page in its Front Matter). The variables should point to data files with the correct structure in the **/_data** folder.

The defaults for this project are shown below. These demonstrate how to set the global values, and how to provide different values for specific folder paths and collections (types). 


{% highlight yaml %}
 defaults:

  - # Global default is use structures in /_data/toc.yml and /_data/navmenu.yml
    scope:
      path: ""

    values:
      toc: toc
      navmenu: navmenu


  - # Specify values for a collection using the scope type "test_collection"
    scope:
      path: ""
      type: "test_collection"

    values:
      toc: toc_test_collection
      navmenu: navmenu_test_collection

  - # Specify values for particular folder path using the scope > path variable.
    scope:
      path: "test_section"
      type: "pages"

    values:
      toc: toc_test_section
      navmenu: navmenu_test_section
{% endhighlight %}

<div class="alert alert-success" role="alert"><p>Collections are not required in order to give sets of topics common navigation - you can simply group the topics in folders and sepcify the path in the scope.</p>
</div>