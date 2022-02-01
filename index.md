---
---

{% assign sorted = site.data.releases | sort: 'major' | reverse %}
{% for release in sorted %}

{% capture posttime %}{{release.released | date: '%s'}}{% endcapture %}

<h3>elementary OS {{ release.major }} {{ release.name }}</h3>

{% endfor  %}
