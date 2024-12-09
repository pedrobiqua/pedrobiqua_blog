---
layout: default
title:
permalink: /
---

<style>
  /* Estilo para a seção do perfil */
  .profile {
    display: flex;
    align-items: center;
    gap: 40px;
  }

  .profile-photo img {
    max-width: 200px;
    height: auto;
    border-radius: 50%;
  }

  .profile-text {
    flex: 1;
    text-align: justify;
  }

  /* Adicionar espaçamento superior à seção de notícias */
  .news-section {
    margin-top: 40px;
  }

  /* Estilo para os itens da notícia */
  .news-item {
    border: 1px solid #ddd;
    padding: 15px;
    margin-bottom: 15px;
    border-radius: 8px;
    transition: box-shadow 0.2s ease;
  }

  .news-item:hover {
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  }

  .news-item a {
    text-decoration: none;
    color: inherit;
  }

  /* Media query para telas menores, como celulares */
  @media (max-width: 768px) {
    .profile {
      flex-direction: column; /* Coloca os itens em uma coluna em telas menores */
      align-items: flex-start; /* Alinha os itens à esquerda */
      gap: 20px; /* Reduz o espaçamento entre a imagem e o texto */
    }

    .profile-photo img {
      max-width: 150px; /* Reduz o tamanho da foto */
    }

    .profile-text {
      text-align: left; /* Alinha o texto à esquerda */
    }

    /* Esconde a foto no celular */
    .profile-photo {
      display: none;
    }
  }
</style>

# Welcome to My Blog
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