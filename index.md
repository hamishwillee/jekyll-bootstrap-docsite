---
layout: default
title: Welcome
---

This site demonstrates a prototype Jekyll *documentation* theme based on bootstrap. It features a top navbar, a sidebar Table Of Contents (TOC) and a page breadcrumb. The layout scales for mobile devices and shrinks the table of contents. 

The main feature of this theme is that the TOC and navbar are defined in datafiles, and that they can be assigned to pages directly, or based on their parent folder or collection. This allows single sites to be built to support multiple documentation sets (possibly for related products).

In addition, the version of bootstrap used is bootstrap-SASS. Jekyll's in-built support for SASS means that the appearance of the theme can easily be changed using bootstrap varianbls in **/css/main.scss**.


<div class="alert alert-success" role="alert"><p>Jekyll has primarily been used for blogging, and there are few themes for supporting *documentation* projects.</p> 

<p>The best I've found so far is the <a href="https://sendgrid.com/docs/index.html">SendGrid Docs</a> theme, which uses a plugin to generate a table of contents (TOC) from the folder structure and displays it on the sidebar.  This approach makes the project very easy for users to structure, but means that the project cannot be run using the "inbuilt" Jekyll on Github pages. It also supports only a single TOC. </p>

<p>My project uses the same idea (and the same CSS and javascript for the sidebar) but instead defines the TOC (and sidebar) as yml data files.</p></div>



