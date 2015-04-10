---
layout: page
title: categories
description: tiankonguse 的文章归档。
keywords: tiankonguse, GitHub, Archives, linux, css, html, javascript, python, Jekyll, plugins, php, 大数据, 分布式, 机器学习, acm, 算法
isArchive: true
updateData:  21:25 2015/4/2
---



<div class="row-fluid">
    <div class="accordion" id="accordion2">
        {% for category in site.categories %}
        {% capture categoryName %}{{ category | first }}{% endcapture %}
        {% capture categoryNameMD5 %}{{ categoryName | md5 }}{% endcapture %}
        <div class="accordion-group">
            <div class="accordion-heading">
                <a class="accordion-toggle list-of-categories" data-toggle="collapse" data-parent="#accordion2" href="#{{ categoryNameMD5 }}-ref">
                    {{ categoryName }}<span>{{  category | last | size }}</span>
                </a>
            </div>
            <div id="{{ categoryNameMD5 }}-ref" class="accordion-body collapse">
                <div class="accordion-inner">
                    <ul class="list-articles-category">
                        {% for article in category.last %} 
                        <li>
                            <time pubdate="pubdate" datetime="{{ article.date|date:"%Y-%m-%d %H:%M:%S" }}">
                                {{ article.date|date:"%Y-%m-%d" }}
                            </time>
                            <a href="{{ site.url }}{{ article.url }}">{{ article.title }}</a>
                        </li>
                        {% endfor %}
                    </ul>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>
</div>

