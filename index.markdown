---
layout: default
title: Home
permalink: /
---

<h1>Welcome to My Blog</h1>
---
<br>
<div class="profile">
  <div class="profile-photo">
    <img src="assets/images/Foto Rede Social.png" alt="Pedro's photo" />
  </div>
  <div class="profile-text">
    <p>Hi, I’m Pedro! I’m a Computer Science student who loves exploring technology, solving problems, and working with data.</p>
    <p>I’m always curious and enjoy diving into programming challenges, machine learning experiments, and web development projects. Research and building unique ideas are some of my favorite things to do, always looking for ways to bring something new to the table.</p>
    <p>In my work, I’ve developed a system for generating random numbers using radioactive decay and applied Python to study dissimilarity spaces in concept drift, creating a classifier with scikit-learn. I like blending theory and practice to come up with creative solutions.</p>
    <p>If you’re into data, programming, or just curious about how things work, feel free to reach out. I’m always excited to learn, share, and build something cool together!</p>
  </div>
</div>

## Latest News
---

<div class="news-section">
  {% assign all_posts = site.articles | concat: site.projects | concat: site.posts %}
  {% assign sorted_posts = all_posts | sort: "date" | reverse %}
  {% assign latest_posts = sorted_posts | slice: 0, 3 %}

  {% for post in latest_posts %}
  <div class="news-item">
    <a href="{{ post.url | relative_url }}">
      <h4>{{ post.title }}</h4>
      <p class="news-category">Category: {{ post.collection | capitalize }}</p>
      <p><strong>Published on:</strong> {{ post.date | date: "%B %d, %Y" }}</p>
      <p>{{ post.excerpt | strip_html | truncate: 150 }}</p>
    </a>
  </div>
  {% endfor %}
</div>

## Explore More
---
<br>
Take a look at my [Lattes CV](http://lattes.cnpq.br/9195968586080246) (in Portuguese) or explore the sections below:
- [Articles]({{ "/articles/" | relative_url }})
- [Projects]({{ "/projects/" | relative_url }})
- [Posts]({{ "/posts/" | relative_url }})