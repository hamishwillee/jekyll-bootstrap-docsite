---
layout: default
title: Array functions
description: This page describes some "functions" you might use in Jekyll to create liquid arrays and push and pop items from them.
---

{{page.description}}

## Introduction

This section explains some [functions](https://github.com/hamishwillee/jekyll-bootstrap-docsite/tree/gh-pages/_includes/functions/arrays) that you might use to dynamically add or pop items from an array. The functions take arrays as parameters, and return a comma-separated string that you can convert back into an array.


Note that these aren't real functions - they are [Jekyll include files](http://hamishwillee.github.io/2014/11/13/jekyll-includes-are-functions/).

<div class="alert alert-success" role="alert"><p>If all you want to do is add to an array, you can probably do this more efficiently by building pattern-separated strings in application-specific code. What these functions are useful for is stripping items off the ends of the array/string - this is not so easy with the string functions provided by Liquid. </p></div>

## Functions

### push()

Function to add a string of comma separated items to an array, "returning" the combined comma separated string representing the array.

Function file location: **/functions/array/push.html**

Parameters

* ```array```: An array to add to. This need not be specified, or may be specified as an empty string ```''```
* ```add```: Comma-separated list of items to add to the array. For example: ```add="Carl, John, Fred"``` or ```add="Albert"```

Returns: comma-separated list of the items in ```array``` and ```add```.

The code fragment below shows how to create an array:

{% highlight liquid %}
{% raw %}
{% assign an_array = "first item, second item, third item" | split: "," %}
{% endraw %}
{% endhighlight %}

The code fragment below shows how to add two items "Carl" and "Jim" to that array. ```capture``` assigs the result of the ```push``` fucnction ot a variable. This is then turned back into an array.

{% highlight liquid %}
{% raw %}
{% capture newstring %}{% include /functions/array/push.html array=an_array add="Carl, Jim" %}{% endcapture %}
{% assign resultsarray = newstring | strip_newlines | split: "," %}
{% endraw %}
{% endhighlight %}


### pop()

Function to remove a specified number of items from the end of an array, "returning" a comma-separated string representing remainder of the array.

Function file location: **/functions/array/pop.html**

Parameters

* ```array```: The array to pop items from. 
* ```pop``` (optional): The number of items to remove from the array. If pop is not specified, one item is removed from the array.

Returns: The remainder of the array, as a comma separated list.


The code fragment below shows how to remove the last two items from an array. 

{% highlight liquid %}
{% raw %}
{% assign an_array = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}
{% capture newstring %}{% include /functions/array/pop.html array=an_array pop='2' %}{% endcapture %}
{% assign resultsarray = newstring | strip_newlines | split: "," %}
{% endraw %}
{% endhighlight %}





-----
## Tests

TEST INDCLUDE 

Create with no array, and add variable Fred:

{% capture newstring %}{% include /functions/array/push.html add="fred" %}{% endcapture %}
{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 

-----

Create with "empty" array, and add variable Carl:

{% assign myarray = '' %}
{% capture newstring %}{% include /functions/array/push.html array=myarray add="Carl" %}{% endcapture %}
{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 

----
Use array returned, and add variable "Gary":

{% capture newstring %}{% include /functions/array/push.html array=resultsarray add="Gary" %}{% endcapture %}
{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 

-----

Create normal array then add item to it:

{% assign explicitarray = "first item,second item,third item" | split: "," %}


{% capture newstring %}{% include /functions/array/push.html array=explicitarray add="Jim" %}{% endcapture %}
{% assign resultsarray = newstring | strip_newlines | split: "," %}


Size: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 


-----

Create normal array then add multiple items to it:

{% assign explicitarray = "first item, second item, third item" | split: "," %}

{% capture newstring %}{% include /functions/array/push.html array=explicitarray add="Albert1,Albert2,Albert3" %}{% endcapture %}
{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 


-----

Pop 2 items from array

{% highlight liquid %}
{% raw %}
{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray pop='2' %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 
{% endraw %}
{% endhighlight %}



{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray pop='2' %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 



-----

Pop first items from array

{% highlight liquid %}
{% raw %}
{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 
{% endraw %}
{% endhighlight %}



{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 


-----

Pop all but 1 items from array

{% highlight liquid %}
{% raw %}
{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray pop='5' %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 
{% endraw %}
{% endhighlight %}



{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray pop='5' %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 


-----

Pop all items from array

{% highlight liquid %}
{% raw %}
{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray pop='6' %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 
{% endraw %}
{% endhighlight %}



{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray pop='6' %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %}



-----

Pop more items from array than exist

{% highlight liquid %}
{% raw %}
{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray pop='7' %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 
{% endraw %}
{% endhighlight %}



{% assign explicitarray = "first item, second item, third item, fourth item, fifth item, sixth item" | split: "," %}

Size before pop: {{ explicitarray.size }}

{% capture newstring %}{% include /functions/array/pop.html array=explicitarray pop='7' %}{% endcapture %}

String returned after pop: {{ newstring }}

{% assign resultsarray = newstring | strip_newlines | split: "," %}

Size after pop: {{ resultsarray.size }}

Iterate the result:

{% for item in resultsarray %} 
  item:{{forloop.index0}}: {{ item }}
{% endfor %} 



