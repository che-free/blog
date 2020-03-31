---
title: Posts
permalink: /test/posts
---

## site.posts
> Page Variables 참고 https://jekyllrb.com/docs/variables/

- page.content
- page.excerpt

|title|url|date|id|categories|tags|dir|name|path|next|previous|
|--|--|--|--|--|--|--|--|--|--|--|
{{ "" }}
{%- for page in site.posts -%}
    {%- assign row = "|" -%}
    {%- assign row = row | append : page.title | append : "|" -%}
    {%- assign row = row | append : page.url | append : "|" -%}
    {%- assign row = row | append : page.date | append : "|" -%}
    {%- assign row = row | append : page.id | append : "|" -%}
    {%- assign row = row | append : page.categories | append : "|" -%}
    {%- assign row = row | append : page.tags | append : "|" -%}
    {%- assign row = row | append : page.dir | append : "|" -%}
    {%- assign row = row | append : page.name | append : "|" -%}
    {%- assign row = row | append : page.path | append : "|" -%}
    {%- assign row = row | append : page.next.url | append : "|" -%}
    {%- assign row = row | append : page.previous.url | append : "|" -%}
    {{ row }}
    {{ "" }}
{%- endfor -%}
