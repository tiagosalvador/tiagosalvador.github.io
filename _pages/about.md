---
layout: page
permalink: /
title: about
nav: about
description: <a href="http://www.lti.cs.cmu.edu/" class="page-description" target="_blank">Language Technologies Institute</a> • <a href="http://www.cs.cmu.edu/" class="page-description" target="_blank">School of Computer Science</a> • <a href="http://www.cmu.edu/" class="page-description" target="_blank">Carnegie Mellon University</a>
address: <a href="https://www.google.com/maps/place/Gates+Center+for+Computer+Science/@40.4432641,-79.9449469,19.18z/data=!4m5!3m4!1s0x8834f22175d2f3cf:0x963e80aba7fde2d0!8m2!3d40.4435476!4d-79.9446184" class="page-description" target="_blank">Gates Hillman Center, 5000 Forbes Ave, Pittsburgh, PA 15213</a>
---

<div class="col p-0 pt-4 pb-4">
  <h1 class="pb-3 title text-left font-weight-bold">Rishabh Joshi</h1>
  <h6 class="m-0 mb-2" style="font-size: 0.83em;">{{ page.description }}</h6>
  {% if page.address %}
      <h6 class="m-0 mb-2" style="font-size: 0.83em;">{{ page.address }}</h6>
  {% endif %}
</div>

<!-- Introduction -->

<div style="display: flex; flex-wrap: wrap;">
    <div class="text-justify p-0">
        <div class="col-xs-12 col-sm-6 p-0 pt-2 pb-sm-2 pb-4 pl-sm-4 text-center" style="float: right;">
          <img class="profile-img img-responsive" src="{{ 'prof_pic.jpg' | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">
        </div>

        <p>
	I am a MLT (Master's in Language Technologies) student in the <a href="http://www.lti.cs.cmu.edu/" target="_blank">Language Technologies Institute</a>, <a href="http://www.cs.cmu.edu/" target="_blank">School of Computer Science</a> at <a href="http://www.cmu.edu/" target="_blank">Carnegie Mellon University</a>, co-advised by <a href="http://www.cs.cmu.edu/~awb/" target="_blank">Alan W Black</a>, <a href="http://www.cs.cmu.edu/~ytsvetko/" target="_blank">Yulia Tsvetkov</a> and <a href="http://www.cs.cmu.edu/~air/" target="_blank">Alex Rudnicky</a>.
        </p>
        
        <p>
	My research focuses on developing algorithms for machine learning and applying my methods in order to study how machines can mimic humans in congitive tasks, especially those related to Language. My main research project with Alan and Yulia is on negotiation and persuasion in dialogue systems where we are trying to understand the qualities of good/bad sellers/persuaders. We are also trying to build a system that can suggest optimum <i>strategies</i> for a favourable outcome.
	Under Alex, I'm working with CMU's team for the Amazon Alexa Challenge, 2020. 
        </p>

	<p>
    Before I joined CMU, I worked in Samsung Research Institute, Bangalore, India where I was working in the Voice Intelligence Team on dialogue systems and chat-bots. Before that, I spent a wonderful semester working with <a href="http://talukdar.net" target="_blank">Partha Talukdar</a> at <a href="http://malllabiisc.github.io/" target="_blank">Machine and Language Learning (MALL) Lab</a> in the <a href="https://www.iisc.ac.in/" target="_blank">Indian Institute of Science, Bangalore</a>. I graduated with a B.Eng. in Computer Science from <a href="http://www.bits-pilani.ac.in/pilani/" target="_blank">Birla Institute of Technology and Science, Pilani</a>, India.
    In my Bachelor's thesis, I worked on incorporating external knowledge in distantly supervised neural relation extraction methods as part of iNELL (which is based on <a href='http://rtw.ml.cmu.edu/rtw/' target='_blank'>NELL</a>).
	</p>
    </div>
</div>


<!-- News -->
<div class="news mt-3 p-0">
  <h1 class="title mb-4 p-0">news</h1>
  {% assign news = site.news | reverse %}
  {% for item in news limit: site.news_limit %}
    <div class="row p-0">
      <div class="col-sm-2 p-0">
        <span class="badge danger-color-dark darken-1 font-weight-bold text-uppercase align-middle date ml-3">
          {{ item.date | date: "%b %-d, %Y" }}
        </span>
      </div>
      <div class="col-sm-10 mt-2 mt-sm-0 ml-3 ml-md-0 p-0 font-weight-light text">
        <p>{{ item.content | remove: '<p>' | remove: '</p>' | emojify }}</p>
      </div>
    </div>
  {% endfor %}
</div>
