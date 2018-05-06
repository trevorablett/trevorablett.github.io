---
layout: page
title: Research
published: true
---

<p>For a full list of my published work, see my <a href="scholar.google.com/citations?user=p3NT2IoAAAAJ&hl=en"><b>Google Scholar page</b></a>. My previous research focussed on increasing robot autonomy via novel sensor applications, but now I am investigating the use of data-driven machine learning techniques, as opposed to traditional model-based methods, for allowing manipulators to leverage prior knowledge to complete novel tasks.</p>

<hr/>

<div>
{% assign sorted_research = site.research | sort:"order" %}

{% for project in sorted_research %}

    <div>
    
    <h3>{{ project.title }}</h3>
    
    {% if project.img %}
        <img class="left" src="{{ project.img }}">
    {% endif %}
    
    {% assign sorted_pubs = project.publications | sort:"date" %}
    
    {% for publication in sorted_pubs reversed %}

        {% if publication.img %}
            <img class="left" src="{{ publication.img }}">
        {% elsif publication.vid %}
            <video class="left" autoplay loop muted>
                <source src="{{ publication.vid }}" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        {% endif %}
  
        {% if publication.doi %}
            <a href="{{ publication.doi }}" target="_blank"><b>{{ publication.title }}</b></a>
        {% else %}
            <b>{{ publication.title }}</b>
        {% endif %}
        <br/>

        <i>{{ publication.authors }}</i>
        <br/>

        {{ publication.venue }}
        <br/>

        {% if publication.note %}
            <i>{{ publication.note }}</i><br/>
        {% endif %}

        {% if publication.award %}
            <b>{{ publication.award }}</b><br/>
        {% endif %}
        
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
    {% endfor %}

    </div>
    {% unless forloop.last %}
        <hr/>
    {% endunless %}
{% endfor %}
</div>
