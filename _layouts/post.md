---
layout: default

---
<h1> {{ page.title }} </h1>
<h3> {{ page.date | date_to_string }} </h3>

{{ content }}

{% include footer.html %}