---
lang: en
layout: post
title: |
  Let's English Puzzle! - Learn English Vocabulary Enjoyably with Transforming Cubes
description: |
  Development of Infrared Communication Blocks and Games for Elementary School Students to Learn English Vocabulary While Playing.

permalink: /english/projects/2018/lets_eigo_puzzle
thumbnail: /assets/img/projects/2018/lets_eigo_puzzle.webp
twitter_card: summary_large_image
---

{% assign pj = site.data.projects | where_exp: "pj", "pj.id == 'lets_eigo_puzzle'" | first %}

<div style='margin-top: 50px; margin-bottom: 30px;'>
  <img class='top-img lazyload' src='/assets/img/spinner.svg' alt='Thumbnail - {{ pj.title }}'
  {% if pj.thumbnail %}    data-src='/assets/img/projects/{{ pj.year }}/{{ pj.thumbnail }}'
  {% else %}               data-src='/assets/img/projects/tbu.webp'
  {% endif %}                 title='{{ pj.title }}' style='border-radius: 6px;' loading='lazy' />
</div>

{{ pj.description_en }}

<div class='flex'>
  {% if pj.link %}
    {% if pj.link contains 'github.com' and pj.link contains 'releases' %}
       <a href='{{ pj.link }}' target='_blank' class='button'>Donwload codes on GitHub</a>
    {% elsif pj.link contains 'github.com' %}
       <a href='{{ pj.link }}' target='_blank' class='button'>View project on GitHub</a>
    {% else %}
       <a href='{{ pj.link }}' target='_blank' class='button'>View official website</a>
    {% endif %}
  {% endif %}

  <a href="https://twitter.com/intent/tweet?text={{ pj.title }}&via=MitouJr&hashtags=未踏ジュニア{% if pj.tags %},{{ pj.tags | join: ','}}{% endif %}&related=MitouJr&lang=jp&url={{ site.url }}/projects/{{ pj.year }}/{{ pj.id }}" class="button" target="_blank" rel="noopener">ツイートする</a>
</div>

### Creator {#creator}
<p>
  {% for creator_id in pj.creator_ids %}
    {% assign creator = site.data.creators | where: "id", creator_id | first %}
    {% if forloop.index > 1 %}<span>/</span>{% endif %}

    {{ creator.id | split: '_' | first | capitalize }}
    {{ creator.id | split: '_' | last  | capitalize }}
  {% endfor %}

  <small>
    (Year: <a href='/english/projects/#{{ pj.year }}'>{{ pj.year }}</a> /
     Mentor: {% include link-to-mentor.html id=pj.mentor_id %})
  </small>
</p>

{% comment %}
{% if pj.comment %}
### Mentor's Comment {#comment}
<p class="project-comment">{{ pj.comment }}</p>
{% endif %}
{% endcomment %}

{% if pj.promotion %}
{% if pj.promotion contains '.gif' %}
## Demo {#demo}
<img class='top-img lazyload' src='/assets/img/spinner.svg' alt='デモ動画 (Gif)'
     data-src='/assets/img/projects/{{ pj.year }}/{{ pj.promotion }}' loading='lazy'
     style='margin-bottom: 10px; border-radius: 6px;' />
{% else %}
## Demo {#demo}
<div class="youtube">
  <iframe width="560" height="315" class="lazyload" data-src="https://www.youtube.com/embed/{{ pj.promotion }}?rel=0" frameborder="0" allowfullscreen=""></iframe>
</div>
<a href="https://youtu.be/{{ pj.promotion }}" target="_blank" rel="noopener" class="button">Watch on YouTube</a>
{% endif %}
{% endif %}

{% if pj.final %}
## Pitch {#final}
<div class="youtube">
  <iframe width="560" height="315" class="lazyload" data-src="https://www.youtube.com/embed/{{ pj.final }}?rel=0{% if pj.final_start %}&start={{ pj.final_start }}{% endif %}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>
</div>

{% if page.lang == 'en' %}
<div class="note" style="margin-top: 30px;">
  <span style="font-weight: bold; margin-left: -4px;">To show English subtitles:</span><br>
  Play video <span class='ignore-sp'>&rarr;</span><span class='ignore-pc'>&darr;</span><br class='ignore-pc'>
  Click CC icon <span class='ignore-sp'>&rarr;</span><span class='ignore-pc'>&darr;</span><br class='ignore-pc'>
  Click Settings <span class='ignore-sp'>&rarr;</span><span class='ignore-pc'>&darr;</span><br class='ignore-pc'>
  Click Subtitles/CC <span class='ignore-sp'>&rarr;</span><span class='ignore-pc'>&darr;</span><br class='ignore-pc'>
  Click Auto-translate <span class='ignore-sp'>&rarr;</span><span class='ignore-pc'>&darr;</span><br class='ignore-pc'>
  Click English <small>(or other language you prefer)</small>
</div>
{% endif %}

<a href="https://youtu.be/{{ pj.final }}{% if pj.final_start %}?t={{ pj.final_start }}{% endif %}" target="_blank" rel="noopener" class="button">Watch on YouTube</a>
{% endif %}

<nav>
  <p class='nav prev'><a href='utips' title='UTIPS - Household Information Sharing Service'>&larr; Prev<br>
    UTIPS - Household Information ...</a></p>
  <p class='nav next'><a href='smile_meeting_room' title='Smile Conference Room - Efficient Use of Conference Rooms with IoT'>Next &rarr;<br>
    Smile Conference Room - Effici...</a></p>
</nav>

<ul style="list-style: none; text-align: center; padding: 30px 0px;">
  <li style="display: inline-block; margin: auto 10px;">
    <a href="/english/projects">&raquo; Back to Project Showcase</a>
  </li>
</ul>