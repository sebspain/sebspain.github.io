<div class="unit w-1-4 hide-on-mobiles">
<h3>Recent Posts</h3>
<ul class="recent-posts">{% for post in site.posts limit:5 %}
	<li><div>{{ post.date | date_to_html_string }}</div>
    	<a href="{{ post.url }}">{{ post.title }}</a></li>
	{% endfor %}
</ul>
</div>
