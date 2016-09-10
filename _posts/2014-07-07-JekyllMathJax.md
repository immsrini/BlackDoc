---
layout: post
title: Working with MathJax on Jekyll 
comments: True
---

One of the many perks of running Jekyll is that it supports LaTeX-like math equation in a post/pages and in turn on a website. 

I have the tool to now write equations like:<br/>
<div align="center">$$P(A|B) = \dfrac{P(B|A)P(A)}{P(B)}$$</div>

#### What is MathJax?
The [MathJax](https://www.mathjax.org/) website describes itself as, "an open-source JavaScript display engine for LaTeX, MathML, and AsciiMath notation that works in all modern browsers."

#### Getting Started 
Getting MathJax to work is rather simple. The following `script` must be added to each page you want to use MathJax. As Jekyll has a neat structure, I put this `script` in `_layout/post.html`. Practically you can invoke this `script` in any page/post by including it the respective layout.

~~~
<script type="text/javascript" 
    src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
~~~

<br/>
Additionally, I had to change the markdown flavour in `_config.yml` to `markdown: kramdown` as `redcarpet` [didn't support MathJax](https://github.com/vmg/redcarpet/issues/313).  Few other HTML converters that support MathJax are: [Pandoc](http://johnmacfarlane.net/pandoc/), [MultiMarkdown](http://fletcherpenney.net/multimarkdown/).

### Working with MathJax
Although there is a prerequisite knowledge of working with LaTeX, its is rather simple to pick up. The official documentation is available [here](http://docs.mathjax.org/en/latest/#), but you'll probably find the [quick reference](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference) more useful.    

For **inline** equation, I use `<span>$$\left(\frac12\right)$$</span>` that will be displayed as <span>$$\left(\frac12\right)$$</span>.

For **display** equation, I use `$$min_{w,b} \frac{ww^T}2 s.t.: y_i(w^T x_i + b) \gt 1 (\forall x_i)$$` that shall be displayed as: <br/>
<div align="center">$$min_{w,b} \frac{ww^T}2 s.t.: y_i(w^T x_i + b) \gt 1 (\forall x_i)$$ </div>

I use the `<div align="center">` to get the equation neatly centered.

For some reason, the other commands like  `\\(...\\)` for in-line math, and `\\[...\\]` for displayed equations don't seem to work for me. 

Tip: You can use `\text{}` inside equations to enter text like `such that, and`

#### Drawback
As I had to move to `kramdown` from `redcarpet` to get MathJax working, the beautiful *blockquotes* of `redcarpet` are not available in this flavour. But never the less, its a affordable trade-off. <i class="fa fa-thumbs-up"></i>


