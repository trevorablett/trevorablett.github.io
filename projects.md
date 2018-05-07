---
layout: page
title: Projects
---

<p> Here are number of the projects that I've worked on that don't directly relate to research. </p>

<p> This page is a work in progress, check back soon! </p>

<div>
{% assign sorted_projects = site.projects | sort:"order" %}

{% for project in sorted_projects %}

    <div style="clear: both; padding-top: 10px">
    
    <hr/>
    
    <h3>{{ project.title }}</h3>
    
    {% if project.img %}
        <img class="right" src="{{ project.img }}">
    {% endif %}
    
    <p>{{ project.description }} </p>
    
    {% assign sorted_subprojects = project.publications | sort:"date" %}
    
    {% for publication in sorted_subprojects reversed %}
    
        <div style="clear: both">
            {% if publication.img %}
                <img class="left" src="{{ publication.img }}">
            {% elsif publication.vid %}
                <video class="left" autoplay loop muted>
                    <source src="{{ publication.vid }}" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            {% endif %}

            <div style="overflow: hidden">
      
                {% if publication.main-link %}
                    <a href="{{ publication.main-link }}" target="_blank"><b>{{ publication.title }}</b></a>
                {% else %}
                    <b>{{ publication.title }}</b>
                {% endif %}
                <br/>

                <i>{{ publication.description }}</i>
                <br/>

                {% if publication.links.preprint %}
                    <a href="{{ publication.links.preprint }}" target="_blank"><i class="far fa-file-alt"></i>&nbsp;Preprint</a>&nbsp;
                {% endif %}

                {% if publication.links.code %}
                    <a href="{{ publication.links.code }}" target="_blank"><i class="fas fa-code-branch"></i>&nbsp;Code</a>&nbsp;
                {% endif %}

                {% if publication.links.slides %}
                    <a href="{{ publication.links.slides }}" target="_blank"><i class="fas fa-desktop"></i>&nbsp;Slides</a>&nbsp;
                {% endif %}

                {% if publication.links.poster %}
                    <a href="{{ publication.links.poster }}" target="_blank"><i class="far fa-image"></i>&nbsp;Poster</a>&nbsp;
                {% endif %}

                {% if publication.links.video %}
                    <a href="{{ publication.links.video }}" target="_blank"><i class="fab fa-youtube"></i>&nbsp;Video</a>&nbsp;
                {% endif %}

                {% if publication.links %}
                    <br/>
                {% endif %}
                
                <br/>
            </div>
        </div>
    {% endfor %}

    </div>
{% endfor %}
</div>