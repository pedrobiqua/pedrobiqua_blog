---
layout: allposts
title: Posts
permalink: /posts/
---

<style>

  /* Estilo para o layout de dois painéis */
  .posts-container {
    display: flex;
    flex-direction: row;
    gap: 30px;
    margin: 30px 0;
  }

  /* Estilo para a lista à esquerda */
  .posts-list {
    width: 30%; /* Largura da lista */
    max-height: 80vh; /* Limita a altura da lista */
    overflow-y: scroll; /* Adiciona barra de rolagem se necessário */
    padding-right: 10px; /* Espaço para a rolagem */
    border-right: 1px solid #ddd; /* Adiciona borda à direita */
  }

  .post-item {
    font-size: 1.3em; /* Aumentando o tamanho do texto */
    margin-bottom: 20px; /* Aumentando o espaçamento entre os itens */
  }

  .post-item a {
    text-decoration: none;
    color: #333;
  }

  .post-item a:hover {
    color: #007bff;
  }

  /* Estilo para o painel de pré-visualização à direita */
  .post-preview {
    width: 65%; /* Largura do preview */
    max-height: 80vh; /* Limita a altura do painel de preview */
    overflow-y: scroll; /* Adiciona barra de rolagem se necessário */
    padding-left: 30px; /* Aumentando o padding à esquerda */
  }

  .post-preview-title {
    font-size: 2.2em; /* Tamanho maior para o título do preview */
    font-weight: bold;
    margin-bottom: 15px; /* Mais espaço abaixo do título */
  }

  .post-preview-date {
    font-size: 1.1em;
    color: #777;
    margin-bottom: 20px; /* Espaço maior entre a data e o resumo */
  }

  .post-preview-excerpt {
    font-size: 1.3em; /* Tamanho maior para o resumo */
    margin-bottom: 30px; /* Mais espaço abaixo do resumo */
  }

  .post-preview-footer a {
    color: #007bff;
    text-decoration: none;
    font-weight: bold;
  }

  .post-preview-footer a:hover {
    text-decoration: underline;
  }

  /* Ajuste para o título da página */
  h1 {
    font-size: 1.5em; /* Maior tamanho para o título da página */
    font-weight: bold;
  }

  /* Ajuste no link da lista para que o clique vá até o preview do post */
  .post-item a {
    cursor: pointer;
  }

  /* Ajustes para dispositivos móveis */
  @media screen and (max-width: 768px) {
    .posts-container {
      flex-direction: column; /* Altera para coluna em telas pequenas */
    }

    .posts-list {
      width: 100%; /* A lista ocupa toda a largura */
      margin-bottom: 20px; /* Adiciona um espaço entre a lista e o preview */
    }

    .post-item {
      font-size: 1em; /* Diminui o tamanho da fonte na lista */
    }

    .post-preview {
      width: 100%; /* O painel de preview ocupa toda a largura */
      padding-left: 0; /* Remove o padding à esquerda */
    }

    .post-preview-title {
      font-size: 1.8em; /* Diminui o tamanho do título do preview */
    }

    .post-preview-excerpt {
      font-size: 1.1em; /* Diminui o tamanho do resumo */
    }
  }
</style>

# All Posts

<div class="posts-container">
  <!-- Lista de Títulos dos Posts -->
  <div class="posts-list">
    {% if site.posts.size > 0 %}
      {% for post in site.posts %}
        <div class="post-item">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </div>
      {% endfor %}
    {% else %}
      <p>No posts have been published yet. Stay tuned for updates!</p>
    {% endif %}
  </div>

  <!-- Preview do Post -->
  <div class="post-preview">
    {% if site.posts.size > 0 %}
      {% for post in site.posts %}
        <div class="post-preview-item" id="{{ post.id }}">
          <div class="post-preview-title">{{ post.title }}</div>
          <div class="post-preview-date">{{ post.date | date: "%B %d, %Y" }}</div>
          <p class="post-preview-excerpt">{{ post.excerpt | strip_html | truncatewords: 100 }}</p> <!-- Aumentando o número de palavras no preview -->
          <div class="post-preview-footer">
            <a href="{{ post.url | relative_url }}">Read More</a>
          </div>
        </div>
      {% endfor %}
    {% else %}
      <p>No posts have been published yet. Stay tuned for updates!</p>
    {% endif %}
  </div>
</div>
