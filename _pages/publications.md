---
title: "Smith Lab - Publications"
layout: homelay
excerpt: "Smith Lab -- Publications."
sitemap: false
permalink: /publications/
---

<div class="container-fluid our-team">
<section class="container">
<div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 x-p">
<h1 class="w-txt">Publications</h1>
<p class="a7-w-txt">Check out some of our recent publications below.</p>
</div>
</section>
</div>

<div class="bx txt-a-c cta-wrapper">
<a href="https://scholar.google.com/citations?hl=en&user=qQx4iIwAAAAJ&view_op=list_works&sortby=pubdate" class="btn btn-primary" target="_blank">See Complete List</a>
</div>
</section>
<!-- Publication section ends -->
</div>

<div class="container-fluid">
<!-- Publication section starts here -->
<section class="container">
<div class="bx section-title-area-new">
<h2 class="section-title">Featured</h2>
</div>

{% assign publications_by_year = site.data.publist | group_by: "year" %}
{% for year_group in publications_by_year %}
<div class="bx section-title-area-new">
<h2 class="section-title">{{ year_group.name }}</h2>
</div>
<div class="bx recent-updates-list">
{% for publi in year_group.items %}
<div class="bx recent-bx">
<div class="media clickable-div" data-href="{{ publi.link.url }}">
<img src="{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="pub-cover" width="225" height="225" alt="{{ publi.title }}"> 
</div>
<div class="info clickable-div" data-href="{{ publi.link.url }}">
<h3 class="title">{{ publi.title }}</h3>
<h5 class="sub-txt">{{ publi.link.display }}</h5>
</div>
</div>
{% endfor %}
</div>
{% endfor %}

<script>
document.addEventListener('DOMContentLoaded', (event) => {
document.querySelectorAll('.clickable-div').forEach(div => {
div.addEventListener('click', function() {
window.location.href = this.getAttribute('data-href');
});
});
});
</script>
