---
layout: default
title: Collections Test 1
toc: toc_test_collection_page
---

This test page assigns a specific TOC to a page in a collection but uses the general collection navmenu (ie does not define it.). 

{% highlight yaml %}
---
layout: default
title: Collections Test
toc: toc_test_collection_page
---
{% endhighlight %}

The test passes if the navmenu includes the item "NAV TEST COLLECTION" and the TOC first item should be "TOC TEST COLLECTION PAGE" (from **/_data/toc_test_collection_page.yml**).


