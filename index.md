#### Welcome to my blog!

{% for post in site.posts %}
 - <a href="{{ post.url }}">{{ post.title }}</a>
    > {{  post.content | strip_html | truncatewords: 50 }}
{% endfor %}