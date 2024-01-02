---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
redirect_from:
  - /wordpress/blog-posts/
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{https://scholar.google.ca/citations?user=6N2hANkAAAAJ&hl=en}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.publications reversed %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}
