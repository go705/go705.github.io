---
layout: archive
title: "News"
permalink: /news/
author_profile: true
---

{% include base_path %}

Updates from QuAIL, including publications, grants, awards, invited talks, student achievements, and laboratory milestones.

{% assign news_items = site.news | sort: "date" | reverse %}

{% for post in news_items %}

  {% include archive-single.html %}

{% endfor %}