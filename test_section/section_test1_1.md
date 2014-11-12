---
layout: default
title: Section Test Document 1
toc: toc_test_section_page
navmenu: navmenu_test_section_page
---

This test page assigns a specific TOC and menu to a page. These should be used in place of the general settings for the **test-section** folder path in the [Front Matter Defaults](how_is_nav_implemented.html).

{% highlight yaml %}
---
layout: default
title: Section Test Document 1
toc: toc_test_section_page
navmenu: navmenu_test_section_page
---
{% endhighlight %}

The test passes if the navmenu includes the item "NAV SECTION PAGE TEST" and the TOC first item should be "TOC SECTION PAGE" (from **/_data/toc_test_section_page.yml**).

