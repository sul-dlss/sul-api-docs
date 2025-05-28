---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: About
---

<h1>API Documentation</h1>
<h2>
The public facing Stanford Libraries API documentation site
</h2>

Stanford Libraries creates many user facing applications that provide services to patrons, researchers, and the general public. This site services as documentation to the public facing application programming interfaces (APIs) that Stanford Libraries provides.

<h2>
Avaliable APIs
</h2>
<ul class="ps-3">
{%- for doc in site.docs -%}
  <li class="fs-4">
    <a href="{{ doc.url | relative_url }}">{{ doc.title | escape }}</a>
  </li>
{%- endfor -%}
 </ul>