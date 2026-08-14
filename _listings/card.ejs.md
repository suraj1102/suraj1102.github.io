<%
// Custom listing template for the project grid.
//
// Differs from Quarto's built-in `grid` type in two ways:
//   1. Projects without an image render as a clean text tile. The built-in
//      substitutes a generated placeholder, which reads as a broken image.
//   2. The category badge sits above the title, where it works as a label.
//
// The whole card is a single <a>, so the entire tile is the click target.
%>

```{=html}
<div class="list grid quarto-listing-cols-2">
<% for (const item of items) { %>
  <div class="g-col-1">
    <a href="<%- item.path %>" class="quarto-grid-link">
      <div class="quarto-grid-item card h-100 card-left<%= item.image ? '' : ' no-image' %>">
        <% if (item.image) { %>
        <p class="card-img-top">
          <img src="<%- item.image %>" class="thumbnail-image card-img" alt="<%= item['image-alt'] || item.title %>" loading="lazy">
        </p>
        <% } %>
        <div class="card-body post-contents">
          <% if (item.categories) { %>
          <div class="listing-categories">
            <% for (const category of item.categories) { %>
            <div class="listing-category cat-<%= category.toLowerCase().replace(/[^a-z0-9]+/g, '-') %>"><%= category %></div>
            <% } %>
          </div>
          <% } %>
          <h3 class="no-anchor card-title listing-title"><%= item.title %></h3>
          <div class="card-text listing-description delink"><%= item.description %></div>
        </div>
      </div>
    </a>
  </div>
<% } %>
</div>
```
