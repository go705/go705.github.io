---
layout: archive
title: "About PI"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

Education
======
* Ph.D in Physics (minor: optical sciences)
  * The University of Arizona (USA), 2022
* M.S. in Physics
  * National Tsing Hua University (Taiwan), 2014
* B.S. in Electrophysics
  * National Chiao Tung University (Taiwan), 2011

Work experience
======
* 2025-Present: Assistant Professor
  * University of Hawaiʻi at Mānoa
  * Department: Electrical and Computer Engineering
  * Research area: Quantum machine learning, quantum network, quantum optics

* 2023-2025: Postdoctoral Research Associate
  * Massaschusetts Institute of Technology
  * Department: Research Laboratory or Electronics
  * Research area: Optical neural network, quantum network, machine learning
  * Supervisor: Dirk Englund

* 2018-2022: Research Associate
  * The University of Arizona
  * Department: Materials Science and Engineering
  * Research area: Continuous-variable Photonic Quantum Information Processing
  * Supervisor: Zheshen Zhang

* 2017-2018: Teaching Assistant
  * The University of Arizona
  * Department: Physics

* 2015-2017: Research Assistant
  * Academia Sinica
  * Department: Institute of Atomic and Molecular Science
  * Research area: Experiment and Theoretical Atomic Physics
  * Supervisor: Ying-Cheng Chen

* 2012-2014: Research Assistant
  * National Tsing Hua University
  * Department: Physics
  * Research area: Theoretical Atomic Physics
  * Supervisor: Ite Yu
  
Skills
======
* Quantum information theory
  * Quantum sensing (e.g., quantum radar, distributed sensor network)
  * Quantum error correection
  * Quantum optics
* Machine learning
  * Quantum machine learning (e.g., variational quantum circuit)
  * Optical neural network
* Photonics experiment
  * Free-space optics (e.g., optical cavity cavity locking)
  * Integrated photonics (e.g., fabrication and characterization)
  * FET simulation (e.g., COMSOL)

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
{% comment %} 
  Sort talks by date (latest first) and then group by title.
{% endcomment %}
{% assign sorted_talks = site.talks | sort: "date" | reverse %}
{% assign talks_by_title = sorted_talks | group_by: "title" %}

{% for group in talks_by_title %}
  <div style="margin-bottom: 1.5em;">
    <strong>{{ group.name }}</strong>
    <ul style="list-style-type: none; margin-top: 5px; margin-left: 15px;">
      {% assign group_items = group.items | sort: 'date' | reverse %}
      {% for talk in group_items %}
        <li style="font-size: 0.95em; margin-bottom: 5px;">
          <i class="fa fa-fw fa-calendar" aria-hidden="true"></i> {{ talk.date | date: "%B %Y" }} — {{ talk.venue }}
        </li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>


[**Download CV as PDF**](https://go705.github.io/assets/files/AP_Bo-Han-Wu_CV.pdf){: .btn .btn--info}