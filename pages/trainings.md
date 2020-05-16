---

title: Schedule & Trainings
layout: event_noheader
permalink: /trainings/

---

<link rel="stylesheet" type="text/css" href="/assets/css/training.css">

# {{ page.title }}
<br>

**Monday, April 27** 
* Free Lightning Conference
* 12:00pm to 1:30pm EDT/1800pm to 2000pm CET 
* Register for login instructions
* Will be livestreamed to our [YouTube channel](https://www.youtube.com/OWASPGlobal)

**Tuesday, April 28** and **Wednesday, April 29** 
* Virtual Training Courses
* 12:00pm to 4:00pm EDT/1800pm to 2000pm CET 

**Thursday, April 30** to **Saturday, May 1** 
* Virtual Capture the Flag
* 12:00pm (Apr 30) to 12:00pm (May 1) EDT/1800pm to 1800pm CET 

**Training subject to change based on trainer availability.**

{% assign trainings = site.data.trainings | sort: 'Title' %}
{% for trainer in trainings %}
<section class="trainer-section" id="{{trainer.SectionId}}">
<hr>
<ul>
<li><h3 class='training-header'>{{ trainer.Title }}<button class="cta-button grey" onclick="location.href='{{trainer.URL}}';" style="margin-left:1em;cursor: pointer;max-width=80px;">Register</button></h3></li>
<li class="training-desc">{{ trainer.Description }}</li>
    <ul>
        {% for tr in trainer.Trainers %}
        <li style="font-size:smaller;"><hr><div class="training-container"><div class="training-image" style="background-image:url('{{tr.Image}}');"></div><div class='trainer-container'><a href="/trainers/#{{tr.TrainerId}}">{{tr.Name}}</a></div></div><div class='trainer-container-mobile'><a href="/trainers/#{{trainer.TrainerId}}">{{tr.Name}}</a></div>{{tr.Biography}}</li>
        {% endfor %}
    </ul>
</ul>
</section>
{% endfor %}
