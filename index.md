---
---

{% assign sortedreleases = site.data.releases | sort: 'major' | reverse %}
{% for release in sortedreleases %}
{% capture releasedate %}{{release.released | date: '%s'}}{% endcapture %}
<h3>elementary OS {{ release.major }} {{ release.name }}</h3>

{% if release.files %}
{% assign sortedfiles = release.files | sort: 'released' | reverse %}
{% for file in sortedfiles %}
<h4>{{ file.filename }}</h4>
<small>{{ file.arch }} - {{ file.released }}</small>
<p><a href="{{ file.url }}">Download on archive.org</a></p>
{% endfor %}
{% endif %}

{% endfor %}
