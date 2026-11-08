```{=html}
<div class="list article-grid">

<% for (const item of items) { %>
  <article class="article-card" <%= metadataAttrs(item) %>>

    <% if (item.image) { %>
      <a href="<%- item.path %>" class="article-card-image">
        <img src="<%- item.image %>"
             alt="<%- item['image-alt'] || item.title %>">
      </a>
    <% } %>

    <div class="article-card-content">

      <% if (item.categories) { %>
        <div class="listing-categories">
          <% for (const category of item.categories) { %>
            <span class="article-category"><%- category %></span>
          <% } %>
        </div>
      <% } %>

      <h3 class="article-title">
        <a href="<%- item.path %>" class="listing-title">
          <%- item.title %>
        </a>
      </h3>

      <% if (item.subtitle) { %>
        <p class="article-subtitle listing-subtitle">
          <%- item.subtitle %>
        </p>
      <% } %>

      <div class="article-meta">
        <% if (item.author) { %>
          <span class="listing-author"><%- item.author %></span>
        <% } %>

        <% if (item.date) { %>
          <span class="meta-separator">·</span>
          <span class="listing-date"><%- item.date %></span>
        <% } %>

        <% if (item['reading-time']) { %>
          <span class="meta-separator">·</span>
          <span class="listing-reading-time">
            <%- item['reading-time'] %> read
          </span>
        <% } %>
      </div>

    </div>
  </article>
<% } %>

</div>
```