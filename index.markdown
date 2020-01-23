---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default

---

<div class="home-title">
<h1>Computer Science Journal</h1>
<p>belongs to Daniel Stahl</p>
</div>

<ul>
	  {% for post in site.posts %}
	    {% unless post.next %}
	      <h3>{{ post.date | date: '%B' }}</h3>
	    {% else %}
	      {% capture year %}{{ post.date | date: '%Y %b' }}{% endcapture %}
	      {% capture nyear %}{{ post.next.date | date: '%Y %b' }}{% endcapture %}
	      {% if year != nyear %}
	        <h3>{{ post.date | date: '%B' }}</h3>
	      {% endif %}
	    {% endunless %}

	    <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: '%B %d, %Y' }}</li>
	  {% endfor %}
</ul>
