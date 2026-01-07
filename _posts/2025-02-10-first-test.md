---
layout: default
title: Ashes and Ink
author: Jane Doe
penname: EmberQuill
genre: Poetry
featured: true
---

<h2>{{ page.title }}</h2>

<div class="work-header">
  <p class="work-meta">
    By {{ page.penname | default: page.author }} •
    {{ page.genre }} •
    {{ page.date | date: "%B %d, %Y" }}
  </p>
</div>

---

This is where the poem goes.

Line by line.  
Let the white space breathe.
