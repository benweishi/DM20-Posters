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
  <div class="projects-image">
    {% capture image_path %}/assets/images/thumbnails/{{ project.ID }}.jpg{% endcapture %}
    {% assign find = false %}
    {% for static_file in site.static_files %}
      {% if static_file.path == image_path %}
          {% assign find = true %}
      {% endif %}
    {% endfor %}
    {% if find %} {% else %} {% assign image_path = '/assets/images/no_image.png' %} {% endif %}
    <img alt="{{ project_title }}" src="{{ image_path | relative_url }}" class="poster-image">
  </div>
  <div class="projects-name">
    {{ project_title }}
  </div>
  <div class="projects-members">
    {% if project.show_names == 'No' %} Names are not available {% else %} {{ project.members }} {% endif %}
  </div>
  <div class="projects-time">
    {% if project.tw300.size > 0 %} <a href="{{ project.tw300 }}" target="zoom_link">03:00</a>; {% endif %}
    {% if project.tw330.size > 0 %} <a href="{{ project.tw330 }}" target="zoom_link">03:30</a>; {% endif %}
    {% if project.tw400.size > 0 %} <a href="{{ project.tw400 }}" target="zoom_link">04:00</a>; {% endif %}
    {% if project.tw430.size > 0 %} <a href="{{ project.tw430 }}" target="zoom_link">04:30</a>; {% endif %}
    {% if project.tw500.size > 0 %} <a href="{{ project.tw500 }}" target="zoom_link">05:00</a>; {% endif %}
    {% if project.tw530.size > 0 %} <a href="{{ project.tw530 }}" target="zoom_link">05:30</a>; {% endif %}
    ({{ project.EPVT }})
  </div>
  <div class="projects-members">
    ID: {{ project.ID }}
  </div>
</div>
{% endfor %}
</div>