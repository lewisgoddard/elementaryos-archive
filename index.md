---
---

{% assign sortedreleases = site.data.releases | sort: 'major' | reverse %}
{% for release in sortedreleases %}
<h2>elementary OS {{ release.major }} {{ release.name }}</h2>
<p>First released {{ release.released }}, based on {{ release.base }}.</p>

{% if forloop.index == 1 %}
<p><a href="https://elementary.io/">Download @ elementary.io</a></p>
{% elsif release.files %}
{% assign sortedfiles = release.files | sort: 'released' | reverse %}
{% for file in sortedfiles %}
<h3>{{ file.filename }}</h3>
<p>{{ file.released }} - {{ file.arch }} - {{ file.size }} - <a href="{{ file.url }}">Download on archive.org</a></p>
{% endfor %}
{% endif %}

{% endfor %}
