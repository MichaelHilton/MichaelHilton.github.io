---
layout: page
permalink: /teaching/
title: teaching
description: Materials for courses you taught. Replace this text with your description.
nav: true
---



<div class="projects grid">

  {% assign sorted_courses = site.courses | sort: "importance" %}
  {% for class in sorted_courses %}
  <div class="grid-item">
    {% if class.redirect %}
    <a href="{{ course.redirect }}" target="_blank">
    {% else %}
    <a href="{{ course.url | relative_url }}">
    {% endif %}
      <div class="project hoverable">
        {% if class.img %}
        <img src="{{ class.img | relative_url }}" alt="class thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title text-lowercase">{{ class.title }}</h2>
          <p class="card-text">{{ class.description }}</p>
          <div class="row ml-1 mr-1 p-0">
            {% if class.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ class.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if class.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ project.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div>