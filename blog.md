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
                {% for post in site.posts %}
                  {% assign loopindex = forloop.index %}
                    {{loopindex}} - <a target='_blank' href='{{ post.url }}'>{{ post.title }}, {{ post.date | date: '%B %Y'}}</a><br><br>
                {% endfor %}
            </div>
            <br>
        </div>
    </div>