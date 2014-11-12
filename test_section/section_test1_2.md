---
layout: default
title: Section Test Document 2
---

This test page assigns should have the default TOC and navmenu assigned in the [Front Matter Defaults](how_is_nav_implemented.html).

{% highlight yaml %}
---
layout: default
title: Section Test Document 2
---
{% endhighlight %}

The test passes if the navmenu includes the item "NAV SECTION PAGE TEST" and the TOC first item should be "TOC SECTION PAGE" (from **/_data/toc_test_section_page.yml**).


