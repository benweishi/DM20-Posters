---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<div class="hero">
  <img alt="world cloud" src="{{ '/assets/images/wordcloud.png' | relative_url }}">
</div>

<div class="projects-grid">
{% assign projects = site.data.projects | sort:"EPVT" %}
{% for project in projects %}
{% capture project_title %} {% if project.Title.size > 0 %} {{ project.Title }} {% else %} {{ project.Group_Name }} {% endif %} {% endcapture %}
<div class="projects-cell">
  <a href="{{ project.Zoom_link }}">
    <div class="projects-image">
      <img alt="{{ project_title }}" src="{{ '/assets/images/no_image.png' | relative_url }}" class="poster-image">
    </div>
    <div class="projects-name">
      {{ project_title }}
    </div>
  </a>
  <div class="projects-members">
    {{ project.members }}
  </div>
  <div class="projects-time">
    {{ project.time_slots }} ({{ project.EPVT }})
  </div>
  <div class="projects-members">
    ID: {{ project.ID }}
  </div>
</div>
{% endfor %}
</div>