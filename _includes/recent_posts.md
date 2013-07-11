<h3>Recent Posts</h3>
<ul class="posts">{% for post in site.posts limit:5 %}
	<div>{{ post.date | date_to_html_string }}</div>
    	<h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
	{% endfor %}
</ul>

