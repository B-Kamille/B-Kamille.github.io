---
title: "留言板"
permalink: /guestbook/
layout: single
staticman: true  # 启用 Staticman
staticman_slug: "guestbook"  # 用于分类存储（对应 _data/comments/guestbook/）
---

## ✍️ 欢迎留言！
填写以下表单，你的留言会 **自动保存到 GitHub 仓库**。

<form method="post" action="https://api.staticman.net/v3/entry/github/你的GitHub用户名/你的仓库名/main/guestbook">
  <input name="options[slug]" type="hidden" value="guestbook">
  <label for="name">名字</label>
  <input type="text" name="fields[name]" id="name" required>
  
  <label for="email">邮箱（不会公开）</label>
  <input type="email" name="fields[email]" id="email" required>
  
  <label for="message">留言内容</label>
  <textarea name="fields[message]" id="message" required></textarea>
  
  <button type="submit">提交</button>
</form>

<!-- 显示历史留言 -->
<h2>历史留言</h2>
{% assign comments = site.data.comments.guestbook | sort: "date" | reverse %}
{% for comment in comments %}
  <div class="comment">
    <strong>{{ comment.name }}</strong> 
    <small>{{ comment.date | date: "%Y-%m-%d %H:%M" }}</small>
    <p>{{ comment.message }}</p>
  </div>
{% endfor %}
