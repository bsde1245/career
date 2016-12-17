---
layout: page
title: ടാഗുകൾ
permalink: /categoryview/
---
<div class="post-link1">
{% assign categories = site.categories | sort %}
{% for category in categories %}
 <span class="site-tag">
    <a class="post-link1" href="#{{ category | first | slugify }}">
            {{ category[0] | replace:'-', ' ' }} ({{ category | last | size }})
    </a>
</span>
{% endfor %}
</div>

<div id="index">

{% for category in categories %}
<a name="{{ category[0] }}"></a><h4>{{ category[0] | replace:'-', ' ' }} ({{ category | last | size }}) </h4>
{% assign sorted_posts = site.posts | sort: 'title' %}
{% for post in sorted_posts %}
{%if post.categories contains category[0]%}

  <h5><a class="post-link1" href="{{ site.url }}{{site.baseurl}}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h5>
   

{%endif%}
{% endfor %}

{% endfor %}
</div>
