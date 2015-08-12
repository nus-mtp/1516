---
layout: default
title: Home
---
The information [about the module](about.html) and the [FAQs](faq.html) have been shifted to sub-pages.  This home page will be updated to show a list of blog posts, notes, and announcements, as the semester moves along.

<!-- This loops through the paginated posts -->
{% for post in paginator.posts %}
<h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
<p class="author">
  <span class="date">{{ post.last_modified_at }}</span>
</p>
<div class="content">
  {{ post.excerpt }}
</div>
{% endfor %}
<!-- Pagination links -->

{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&laquo; Prev</a>
  {% else %}
    <span>&laquo; Prev</span>
  {% endif %}

  {% for page in (1..paginator.total_pages) %}
    {% if page == paginator.page %}
      <em>{{ page }}</em>
    {% elsif page == 1 %}
      <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">{{ page }}</a>
    {% else %}
      <a href="{{ site.paginate_path | prepend: site.baseurl | replace: '//', '/' | replace: ':num', page }}">{{ page }}</a>
    {% endif %}
  {% endfor %}

  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Next &raquo;</a>
  {% else %}
    <span>Next &raquo;</span>
  {% endif %}
</div>
{% endif %}

