---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---
<div id="blogBubble" class="rounded_panel txt_lightgrey">
        <div class="top-rounded-panel grey-bg">
            <h1>Blog posts</h1>
        </div>
        <div class="content-rounded-panel">
            <div id="blogArticles">
                <ul style="list-style-type: none;">
                    {% for post in site.posts %}
                        <li ><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
                    {% endfor %}
                </ul>
            </div>
            <p class="rss-subscribe">subscribe <a href="{{ site.url }}/feed.xml">via RSS</a></p>
        </div>
    </div>