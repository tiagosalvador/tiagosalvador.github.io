---
layout: page
title: news
permalink: /news/
description: What has been going on
nav: true
nav_order: 2
---
<div>
    <table>
    {% assign news = site.news | reverse %}
    {% for item in news %}
      <tr>
        <td class="date" style="width:100px" VALIGN=TOP>{{ item.date | date: "%b %-d, %Y" }}</td>
        <td class="announcement">
          {% if item.inline %}
            {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
          {% else %}
            <a class="news-title" href="{{ item.url | prepend: site.baseurl }}">{{ item.title }}</a>
          {% endif %}
        </td>
      </tr>
    {% endfor %}
    </table>
</div>
