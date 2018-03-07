---
author: sspain
comments: true
layout: post
slug: autogenerate-bibliographies-jekyll-liquid-yaml
title: Automatically generated bibliographies with Jekyll, Liquid and YAML
tags:
- science
- code
- jekyll
- liquid
- yaml
---

I recently updated how this site is built behind the scenes including more auto-generated code for bibliographies such as those found on the [publications page](/publications/) or on the [home](/) page.
There other ways of doing this (e.g. [Jekyll-Scholar](https://github.com/inukshuk/jekyll-scholar)) but these usually rely on [CSL styles](https://github.com/citation-style-language/) which don't do what I wanted to do and are relatively long and complex to make your own.
Here is how I get my bibliographies to auto-generate using [jekyll](http://jekyllrb.com), [Liquid](https://shopify.github.io/liquid/) and [YAML](http://yaml.org/).
As always, the code is available on [github](https://github.com/sebspain/sebspain.github.io).

## Why would I (or you) want to auto-generate bibliographies?

Before this update, my publications list was hand-coded in HTML.
If I wanted to repeat part of the list on another page (e.g. the [home](/) page) I had to copy that code over manually.
I wanted a way that I could automatically generate my publications list that would also update other bibliographies around the site.
For example, now when I add a new paper to my database and rebuild the site, it gets added to the main publications page *and* the recent papers list on the home page gets updated.
It can also be used on other places throughout the site (see below).

## Process and Requirements

As jekyll can handle Liquid  and YAML natively, that is the only software requirement.
Find out how to [install jekyll](https://jekyllrb.com/docs/installation/).

The process for producing the bibliography is pretty simple.
The information for each paper is stored in a YAML file.
Wherever a bibliography should appear there is some Liquid code.
When jekyll is called to build the site, it parses the Liquid code, retrieves the appropriate parts from the YAML file, and produces the appropriate HTML ready for use.

## YAML file structure

The complete file is [available on github](https://github.com/sebspain/sebspain.github.io/blob/master/_data/papers.yml).

For each paper there is an entry as shown below.
Most of this should be reasonably self-explanatory, some fields are less obvious but I will come back to those.

{% highlight yml linenos %}

-   id: Neal2018
    authors: Thomas J. Neal, Deborah L. Beattie, Sarah J. Byard, Gregory N. Smith, Martin W. Murray, Neal S. J. Williams, Simon N. Emmett, Steven P. Armes, Sebastian G. Spain* and Oleksandr O. Mykhaylyk
    title: Self-assembly of amphiphilic statistical copolymers and their aqueous rheological properties
    journal: Macromolecules
    year: 2018
    volume: 51
    pages: 1474-1487
    doi: 10.1021/acs.macromol.7b02134
    doi_short: acs.macromol.7b02134
    openaccess: false
    pdf: false
    toc: true
    tags:
        - self assembly
        - characterisation
        - solution behaviour
{% endhighlight %}

## Liquid Code
The simplest example for the liquid is below.
{% highlight liquid linenos %}
{% raw %}
{% for paper in site.data.papers %}
      {{ paper.authors }}
      "{{ paper.title }}",
      <em>{{ paper.journal }}</em>,
      {{ paper.year }},
      {% if paper.volume %} <strong>{{ paper.volume }}</strong>,{% endif %}
      {{ paper.pages }}.
      <a href="http://dx.doi.org/{{ paper.doi }}">[DOI]</a>
{% endfor %}
{% endraw %}
{% endhighlight %}

The first line starts a for loop that goes through each entry in the yaml file papers.yml located in the \_data in the jekyll root folder (hence ```site.data.papers```).
The entry is then assigned to the variable ```paper```.

The second line is where it decides the output and mixes Liquid code with standard HTML to combine data from papers.yml with your formatting.
For example, {% raw %}{{ paper.title }}{% endraw %} gets the content of the ```title``` field and puts that into the code and so on.
One line 5 there is also a conditional (if) statement that allows for journals that don't have volumes (e.g. old *Chem. Commun.* articles).
If the volume field is present, the field value is reported (with additional html attributes) otherwise it moves on to the page numbers.

For the single entry YAML file, jekyll then produces the following HTML code.

{% highlight html linenos %}
Thomas J. Neal, Deborah L. Beattie, Sarah J. Byard, Gregory N. Smith, Martin W. Murray, Neal S. J. Williams, Simon N. Emmett, Steven P. Armes, Sebastian G. Spain* and Oleksandr O. Mykhaylyk
"Self-assembly of amphiphilic statistical copolymers and their aqueous rheological properties",
<em>Macromolecules</em>,
2018,
 <strong>51</strong>,
1474-1487.
<a href="http://dx.doi.org/10.1021/acs.macromol.7b02134">[DOI]</a>
{% endhighlight %}

Which you browser then interprets as:

<p>
{% for paper in site.data.papers limit:1 %}
    {{ paper.authors }}
    "{{ paper.title }}",
    <em>{{ paper.journal }}</em>,
    {{ paper.year }},
    {% if paper.volume %} <strong>{{ paper.volume }}</strong>,{% endif %}
    {{ paper.pages }}.
    <a href="http://dx.doi.org/{{ paper.doi }}">[DOI]</a>
{% endfor %}
</p>

## Advanced examples

For a single citation this doesn't make sense, but with suitable use of the power of Liquid and additional fields in the database it becomes very powerful. Some examples.

### Latest Publications

A simple modification to the code can be used to retrieve the first 5 (for example) entries and list them (this time without authors).

{% highlight liquid linenos %}
{% raw %}
<ul>
{% for paper in site.data.papers limit:5 %}
    <li>
      "{{ paper.title }}",
      <em>{{ paper.journal }}</em>,
      {{ paper.year }},
      {% if paper.volume %} <strong>{{ paper.volume }}</strong>,{% endif %}
      {{ paper.pages }}.
      <a href="http://dx.doi.org/{{ paper.doi }}">[DOI]</a>
    </li>
{% endfor %}
</ul>
{% endraw %}
{% endhighlight %}

#### Output:

<ul>
{% for paper in site.data.papers limit:5 %}
    <li>
      "{{ paper.title }}",
      <em>{{ paper.journal }}</em>,
      {{ paper.year }},
      {% if paper.volume %} <strong>{{ paper.volume }}</strong>,{% endif %}
      {{ paper.pages }}.
      <a href="http://dx.doi.org/{{ paper.doi }}">[DOI]</a>
    </li>
{% endfor %}
</ul>

### Publications by topic

In my database, some entries have a field called ```tags```. In this example, papers that have the tag "DNA based vehicles" are the ones that get picked. A similar approach can be used to get author specific bibliographies.

{% highlight liquid linenos %}
{% raw %}
<ul>
{% for paper in site.data.papers %}
{% if paper.tags contains "DNA based vehicles" %}
<li>
    {{ paper.authors }}
    "{{ paper.title }}",
    <em>{{ paper.journal }}</em>,
    {{ paper.year }},
    {% if paper.volume %} <strong>{{ paper.volume }}</strong>,{% endif %}
    {{ paper.pages }}.
    <a href="http://dx.doi.org/{{ paper.doi }}">[DOI]</a>
</li>
{% endif %}
{% endfor %}
</ul>
{% endraw %}
{% endhighlight %}

Output:

<ul>
{% for paper in site.data.papers %}
{% if paper.tags contains "DNA based vehicles" %}
<li>
    {{ paper.authors }}
    "{{ paper.title }}",
    <em>{{ paper.journal }}</em>,
    {{ paper.year }},
    {% if paper.volume %} <strong>{{ paper.volume }}</strong>,{% endif %}
    {{ paper.pages }}.
    <a href="http://dx.doi.org/{{ paper.doi }}">[DOI]</a>
</li>
{% endif %}
{% endfor %}
</ul>

### More detailed options

In my database, I have entries for ```toc```, ```pdf``` and ```openaccess```.
These are true/false fields and are used to determine what content is displayed in the main publication list in a similar manner to volume conditional earlier.
For example, ```pdf: true``` signifies that the copyright agreement allows me to put the PDF on my website.
A link to the file is then produced (I still have to put the file in the correct place!).

{% highlight liquid linenos %}
{% raw %}
<ul>
{% for paper in site.data.papers %}
  <li>
  <p>
      {{ paper.authors }};
      "{{ paper.title }}",
      <em>{{ paper.journal }}</em>,
      {{ paper.year }},
      {% if paper.volume %} <strong>{{ paper.volume }}</strong>,{% endif %}
      {{ paper.pages }}.
      <a href="http://dx.doi.org/{{ paper.doi }}">[DOI]</a>
      {% if paper.pdf == true %}<a href="/non_foss/publications/PDFs/{{ paper.year }}/{{ paper.doi_short }}.pdf">[PDF]</a>{% endif %}
      {% if paper.openaccess == true %}<img height="14" src="/img/oa.svg" class="oa" alt="open access logo" /> {% endif %}
  </p>
  {% if paper.toc == true %}
      <p><img width="300" src="/non_foss/publications/img/{{ paper.doi_short }}_toc.png" alt="TOC Graphic" /></p>
  {% endif %}
  <div data-badge-popover="right" data-badge-type="1" data-doi="DOI: {{ paper.doi }}" data-hide-no-mentions="true" class="altmetric-embed"></div>
  </li>
{% endfor %}
</ul>
{% endraw %}
{% endhighlight %}
