# yoursred's magical blog

<!--List all pages in collection posts-->

{% for post in site.posts %}
### [{{ post.title }}]({{ post.url }})
{% endfor %}

{{ site.posts.directory }}