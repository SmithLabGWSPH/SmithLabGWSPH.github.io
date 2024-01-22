---
title: "Smith Lab - Team"
layout: homelay
excerpt: "Smith Lab: Team members"
sitemap: false
permalink: /team/
---

<div class="container-fluid our-team">
<section class="container">
<div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 x-p">
<h1 class="w-txt">Our Team</h1>
<p class="a7-w-txt">Discover Our Team: Get to Know the Passionate Professionals Committed to Excellence in Our Department.</p>
</div>
<div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">

</div>
</section>
</div>

<!-- Leadership section starts here -->
<div class="container-fluid">
<section class="container">
<div class="bx section-title-area">
<h2 class="section-title">Leadership</h2>
</div>
<div class="bx leadership-team">
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
{% if member.group == 0 %}
{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}

{% endif %}
<div class="bx team-main-bx clickable-div" data-href="{{ member.url }}">
<div class="media">
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" width="480" height="480" alt="{{ member.name }}">
</div>
<div class="info">
<h4>{{ member.name }}</h4>
<h5>{{ member.info }}</h5>
</div>
</div>

{% if even_odd == 1 %}
</div>
{% endif %}
{% assign number_printed = number_printed | plus: 1 %}
{% endif %}
{% endfor %}
{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
{% endif %}
</section>
</div>
<!-- Leadership section ends -->					

<!-- Trainees section starts -->					
<section class="container">
<div class="bx section-title-area">
<h2 class="section-title">Trainees</h2>
</div>
<div class="bx recent-updates">
{% for member in site.data.team_members %}
{% if member.group == 1 %}
<div class="bx trainee clickable-div" data-href="{{ member.url }}">
<div class="media">
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="320" height="320" alt="{{ member.name }}">
</div>
<div class="info">
<h4>{{ member.name }}</h4>
<h5>{{ member.info }}</h5>
</div>
</div>
{% endif %}
{% endfor %}
</div>
</section>


<!-- Traniees section ends -->					

<!-- Research Staff section starts -->					

<section class="container">
<div class="bx section-title-area">
<h2 class="section-title">Research Staff</h2>
</div>
<div class="bx recent-updates">
{% for member in site.data.team_members %}
{% if member.group == 2 %}
<div class="bx trainee clickable-div" data-href="{{ member.url }}">
<div class="media">
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="320" height="320" alt="{{ member.name }}">
</div>
<div class="info">
<h4>{{ member.name }}</h4>
<h5>{{ member.info }}</h5>
</div>
</div>
{% endif %}
{% endfor %}
</div>
</section>

<section class="container">
<div class="bx section-title-area">
<h2 class="section-title">Alumni</h2>
</div>
<div class="bx recent-updates">
{% for member in site.data.team_members %}
{% if member.group == 8 %}
<div class="bx alumni">
<h4>{{ member.name }}</h4>
<h5>{{ member.info }}{% if member.year %} ({{ member.year }}){% endif %}{% if member.current %}<br>Current: {{ member.current }}{% endif %}</h5>
{% if member.extlink %}
<a class="alumni2" style="padding-left: 0px;" href="{{ member.extlink }}">(Link)</a>
{% endif %}
</div>
{% endif %}
{% endfor %}
</div>
</section>

<script>
document.addEventListener('DOMContentLoaded', (event) => {
document.querySelectorAll('.clickable-div').forEach(div => {
div.addEventListener('click', function() {
window.location.href = this.getAttribute('data-href');
});
});
});
</script>