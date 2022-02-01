---
---

{% assign sortedreleases = site.data.releases | sort: 'major' | reverse %}
{% for release in sortedreleases %}
<h3>elementary OS {{ release.major }} {{ release.name }}</h3>
<p>First released {{ release.released }}, based on {{ release.base }}.</p>

{% if release.files %}
{% assign sortedfiles = release.files | sort: 'released' | reverse %}
{% for file in sortedfiles %}
<h4>{{ file.filename }}</h4>
<p>{{ file.released }} - {{ file.arch }} - {{ file.size }} - <a href="{{ file.url }}">Download on archive.org</a></p>
{% endfor %}
{% endif %}

{% endfor %}
