<%
// Custom listing template for the project list.
//
// Renders projects as a plain, single-column list (title, keyword-tag
// badges, date range, description) — no card chrome, no thumbnails. Order
// comes from projects/index.yml, not from sorting metadata.
//
// The title is plain text. A chain icon after it links to the project's
// own page on this site (set `no-page-link: true` on a project to skip
// this — e.g. when there's nothing on the page worth a separate visit); a
// further icon links out to the project's external homepage if it has
// one, otherwise to its GitHub repo if that's all it has.
%>

```{=html}
<div class="project-list">
<% for (const item of items) { %>
  <div class="project-item">
    <div class="project-item-head">
      <span class="project-item-title"><%= item.title %></span>
      <% if (!item['no-page-link']) { %>
      <a href="<%- item.path %>" class="project-item-icon" title="Project page"><i class="bi bi-link-45deg"></i></a>
      <% } %>
      <% if (item.homepage) { %>
      <a href="<%- item.homepage %>" class="project-item-icon" title="Project website" target="_blank" rel="noopener"><i class="bi bi-box-arrow-up-right"></i></a>
      <% } else if (item.github) { %>
      <a href="<%- item.github %>" class="project-item-icon" title="GitHub repository" target="_blank" rel="noopener"><i class="bi bi-github"></i></a>
      <% } %>
    </div>
    <div class="project-item-meta">
      <% if (item.categories) { %>
      <div class="listing-categories">
        <% for (const category of item.categories) { %>
        <div class="listing-category cat-<%= category.toLowerCase().replace(/[^a-z0-9]+/g, '-') %>"><%= category %></div>
        <% } %>
      </div>
      <% } %>
      <% if (item['start-date']) { %>
      <span class="project-item-dates"><%= item['start-date'] %><% if (item['end-date']) { %> – <%= item['end-date'] %><% } %></span>
      <% } %>
    </div>
    <div class="project-item-desc"><%= item.description %></div>
  </div>
<% } %>
</div>
```
