---
layout: page
title: 梦回蜀川
description: "huhb's Blog"
---
{% include JB/setup %}

<table width="100%" rowspan="0" colspan="0">
<tr>
<td width="70%">
	<div class="home-page-content">
		{% for post in site.posts limit:5 %}
		<div class="home-page-post">
			<div class="post-header">
				<div class="date">{{ post.date | date_to_string }}</div>
				<div class="tags"> 
					<label>标签: </label>
						<a href = "{{ BASE_PATH }}{{ site.JB.tags_path }}#{{ post.tags }}-ref">{{ post.tags | array_to_sentence_string }} </a>
				</div>
				<div class="category"> 
					<label>分类: </label>
						<a href = "{{ BASE_PATH }}{{ site.JB.categories_path }}#{{ post.category }}-ref"> <span>{{ post.category }}</span> </a>
				</div>
			</div>
			<div class="post-content">
				<div class="title"><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></div>
				<div class="abstract">{{ post.description | markdownify }}</div>
				<div style="float:right;"><a href="{{ BASE_PATH }}{{ post.url }}">阅读全文</a></div>
			</div>
			{% if forloop.index != 5 %}
			<div class="post-footer">&nbsp;</div>
			{% endif %}
		</div>
		{% endfor %}
	</div>
</td>

<td width="30%" style="vertical-align:top;">
	<div class="home-page-sidebar">
		<div class="sidebar-title">文章分类</div>
		<div>
			<ul class="tag_box inline">
			{% assign categories_list = site.categories %}
			{% include JB/categories_list %}
			</ul>
		</div>
		<br>
		<div class="sidebar-title">标签</div>
		<div>
			<ul class="tag_box inline">
			{% assign tags_list = site.tags %}  
			{% include JB/tags_list %}
			</ul>
		</div>
	</div>
</td>
</tr>
</table>
<hr>
<div style="width:50%;margin-left:auto;margin-right:auto;text-align:center;clear:both;">
	<a href="/archive.html">查看所有{{site.posts.size}}篇文章</a>
</div>



