---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

You can also find my articles on [my Google Scholar profile](https://scholar.google.nl/citations?user=MPCBlq4AAAAJ&hl=en)


{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
