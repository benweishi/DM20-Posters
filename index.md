---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<div class="hero">
  <img alt="world cloud" src="{{ '/assets/images/wordcloud.png' | relative_url }}">
</div>

<div class="projects-grid">
{% for project in site.data.projects %}
<div class="projects-cell">
  <a href="{{ project.address }}">
    <div class="projects-image">
        <img alt="{{ project.name }}" src="https://images-na.ssl-images-amazon.com/images/I/91wkoe9lV4L._AC_UL480_SR480,480_.jpg" class="poster-image" height="210" width="230">
    </div>
    <div class="projects-name">
      {{ project.name }}
    </div>
  </a>
  <div class="projects-members">
    {{ project.members }}
  </div>
  <div class="projects-time">
    {{ project.time }}
  </div>
  <div class="projects-members">
    ID: {{ project.number }}
  </div>
</div>
{% endfor %}
</div>