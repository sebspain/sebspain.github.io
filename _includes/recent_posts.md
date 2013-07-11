<div class="sidebar-includes">
<h3>Recent Posts</h3>
<ul class="posts">{% for post in site.posts limit:5 %}
	<li><div>{{ post.date | date_to_html_string }}</div>
    	<a href="{{ post.url }}">{{ post.title }}</a></li>
	{% endfor %}
</ul>
</div>
