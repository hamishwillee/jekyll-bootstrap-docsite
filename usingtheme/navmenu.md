---
layout: default
title: Navigation menu (bar)
---

The navigation menu is a bootstrap [Navbar](http://getbootstrap.com/components/#navbar). 

The value of the left navigation element is defined in the **site.title** variable in **_config.yml**. The rest of the menu structure is defined in a yml file in **/_data/** (e.g. [navmenu.yml](https://github.com/hamishwillee/jekyll-bootstrap-docsite/blob/gh-pages/_data/navmenu.yml)) and [assigned to the page](setting_nav_defaults.html) ```navmenu``` variable. 

The yml "structure" for a basic menu is shown below. Top level links are specified using a ```url``` variable for the target. You can optionaly specify the ```name``` to display for the link and whether it should ```align``` right (floated). 

{% highlight yaml %}
- url: /docs/test1_1.html
   name: TOC Defined Name
   align: navbar-right
- url: /about.html
- folder: FolderName
   contents:
      - url: /docs/test1_2.html
      - url: /docs/test1_3.html
        name: Toc-set name
      - divider: true
      - url: /docs/folder2/test2_2.html
      - url: http://hamishwillee.github.io/
        name: Site
        align: navbar-right
      - url: /docs/folder2/test2_1.html
{% endhighlight %}

<div class="alert alert-success" role="alert"><p>Note that the system will fetch the name for a valid document, but you will need to define the name for external links.</p>
</div>


Dropdown lables are specified using the ```folder``` variable, with the individual urls defined as a yaml list under the ```contents``` variable as shown above. Note the use of the ```divider``` variable. 

The appearance and colours can be changed by altering bootstrap variables in [/css/main.scss](https://github.com/hamishwillee/jekyll-bootstrap-docsite/blob/gh-pages/css/main.scss).

<div class="alert alert-success" role="alert"><p>Bootstrap 3 only supports 2 level menus, so there is no further nesting.</p>
</div>
