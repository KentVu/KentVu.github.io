---
layout: post
author: kent
title: Embed react tic-tac-toe
---

{% capture source %}
<div id="root"></div>
<style> h1{font-size:22px}h1,h2{margin-top:0}h2{font-size:20px}h3{font-size:18px}h3,h4{margin-top:0}h4{font-size:16px}h5{font-size:14px}h5,h6{margin-top:0}h6{font-size:12px}code{font-size:1.2em}ul{padding-inline-start:20px}*{box-sizing:border-box}body{font-family:sans-serif;margin:20px;padding:0}.square{background:#fff;border:1px solid #999;float:left;font-size:24px;font-weight:700;height:34px;line-height:34px;margin-right:-1px;margin-top:-1px;padding:0;text-align:center;width:34px}.board-row:after{clear:both;content:"";display:table}.status{margin-bottom:10px}.game{display:flex;flex-direction:row}.game-info{margin-left:20px}
/*# sourceMappingURL=main.9c5c5444.css.map*/</style>
<script src="{% link 7thh9p/build/static/js/main.f0863143.js %}"> </script>
{% endcapture %}

### The game:

{{ source }}

### Steps I've done:
- define `root` element in this post's body. (should be before the `script` tag)
- Copy content of `main.xxxxxx.css` into a `style` tag.
- Include the script `main.f0863143.js`.

### Code needed:

{%- highlight html -%}
  {{ source }}
{% endhighlight %}


See [Source code for this post](https://github.com/KentVu/KentVu.github.io/blob/master/{{page.path}}?plain=1) to see how to use Jekyll's Liquid [capture variable tag filter](https://shopify.github.io/liquid/tags/variable/).
