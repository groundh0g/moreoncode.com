---
layout: page
title: Categories
showTitle: true
---

This is a list of the categories that are used in the posts. They're listed alphabetically.

{% assign sorted = site.categories | sort %}
{% for category in sorted %}
{% assign catName = category | first | uri_escape | downcase %}
* [{{ catName | capitalize }}]({{ site.baseurl }}categories#{{ catName }}-ref) (x{{ category | last | size }})
{% assign categories = site.categories[catName] | sort: "title" %}
{% for post in categories %}
  * [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{% endfor %}
{% endfor %}
