---
author_profile: true
permalink: /publishments/
title: "全部发布"
layout: home
pagination:
  enabled: true
  per_page: 5
  permalink: '/publishments/page:num/'
  title: ':title - 第 :num 页'
  sort_field: 'date'
  sort_reverse: true


---
{% if paginator %}
当前页：{{ paginator.page }} / {{ paginator.total_pages }}
{% else %}
⚠️ 没检测到分页
{% endif %}