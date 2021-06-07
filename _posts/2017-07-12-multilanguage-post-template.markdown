---
layout:       post
title:        "multilanguage post template"
subtitle:     "Feature"
date:         2017-07-12 12:00:00
author:       "PC"
header-img:   "img/photo-with-title.png"
header-mask:  0.3
catalog:      true
multilingual: true
tags:
    - Web
    - PWA
---

<!-- Chinese Version -->
<div class="zh post-container">
    {% capture about_zh %}{% include posts/2017-07-12-multilanguage-post-template/zh.md %}{% endcapture %}
    {{ about_zh | markdownify }}
</div>

<!-- English Version -->
<div class="en post-container">
    {% capture about_en %}{% include posts/2017-07-12-multilanguage-post-template/en.md %}{% endcapture %}
    {{ about_en | markdownify }}
</div>
