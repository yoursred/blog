#### Welcome to my blog!

{% for post in site.posts %}
{% if post.visible %}
- <a href="{{ post.url }}">{{ post.title }}</a>
    > {{  post.content | strip_html | truncatewords: 50 }}
{% endif %}
{% endfor %}

{% include footer.html %}