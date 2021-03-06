---

title: Schedule & Trainings
layout: event_noheader
permalink: /trainings/

---

<link rel="stylesheet" type="text/css" href="/assets/css/training.css">

# {{ page.title }}
<br>

**Training subject to change based on trainer availability.**
{% if site.data.trainings.size > 0 %}

{% assign jtrainings = site.data.trainings | where: 'Type', 'June Training' | sort: 'Title' %} 
{% assign ytrainings = site.data.trainings | where: 'Type', 'July Training' | sort: 'Title' %} 
{% assign atrainings = site.data.trainings | where: 'Type', 'August Training' | sort: 'Title' %}

<a id='jtrainings' class='active'>June Trainings</a> |
<a id='ytrainings' class='inactive'>July Trainings</a> |
<a id='atrainings' class='inactive'>August Trainings</a>

<div id='June' style='display:block;'>

<strong>Please note: All courses take place simultaneously over two days, only register for one for this month</strong>

{% for trainer in jtrainings %}
<section class="trainer-section" id="{{trainer.SectionId}}">
<hr>
<ul>
<li><h3 class='training-header'>{{ trainer.Title }}<button class="cta-button grey" {%if trainer.Status == 'Postponed' or trainer.Status == 'Canceled' %}disabled='true' {%endif%} onclick="location.href='{{trainer.URL}}';" style="margin-left:1em;cursor: pointer;max-width=80px;">{%if trainer.Status == 'Postponed' or traner.Status == 'Canceled'%}{{trainer.Status}}{%else%}Join Us{%endif%}</button></h3></li>
<li class="training-desc">{{ trainer.Description }}</li>
    <ul>
        {% for tr in trainer.Trainers %}
        <li><div class="training-container"><a href="/trainers/#{{tr.TrainerId}}" title="{{tr.Biography}}"><div class="training-image" style="background-image:url('{{tr.Image}}');"></div>{{tr.Name}}</a></div></li>
        {% endfor %}
    </ul>
</ul>
</section>
{% endfor %}
</div>
<div id='July' style='display:none;'>
<strong>Please note: All courses take place simultaneously over two days, only register for one for this month</strong>
{% for trainer in ytrainings %}
<section class="trainer-section" id="{{trainer.SectionId}}">
<hr>
<ul>
<li><h3 class='training-header'>{{ trainer.Title }}<button class="cta-button grey" {%if trainer.Status == 'Postponed' or trainer.Status == 'Canceled' %}disabled='true' {%endif%} onclick="location.href='{{trainer.URL}}';" style="margin-left:1em;cursor: pointer;max-width=80px;">{%if trainer.Status == 'Postponed' or traner.Status == 'Canceled'%}{{trainer.Status}}{%else%}Join Us{%endif%}</button></h3></li>
<li class="training-desc">{{ trainer.Description }}</li>
    <ul>
        {% for tr in trainer.Trainers %}
        <li><div class="training-container"><a href="/trainers/#{{tr.TrainerId}}" title="{{tr.Biography}}"><div class="training-image" style="background-image:url('{{tr.Image}}');"></div>{{tr.Name}}</a></div></li>
        {% endfor %}
    </ul>
</ul>
</section>
{% endfor %}
</div>
<div id='August' style='display:none;'>
<strong>Please note: All courses take place simultaneously over two days, only register for one for this month</strong>
{% for trainer in atrainings %}
<section class="trainer-section" id="{{trainer.SectionId}}">
<hr>
<ul>
<li><h3 class='training-header'>{{ trainer.Title }}<button class="cta-button grey" {%if trainer.Status == 'Postponed' or trainer.Status == 'Canceled' %}disabled='true' {%endif%} onclick="location.href='{{trainer.URL}}';" style="margin-left:1em;cursor: pointer;max-width=80px;">{%if trainer.Status == 'Postponed' or traner.Status == 'Canceled'%}{{trainer.Status}}{%else%}Join Us{%endif%}</button></h3></li>
<li class="training-desc">{{ trainer.Description }}</li>
    <ul>
        {% for tr in trainer.Trainers %}
        <li><div class="training-container"><a href="/trainers/#{{tr.TrainerId}}" title="{{tr.Biography}}"><div class="training-image" style="background-image:url('{{tr.Image}}');"></div>{{tr.Name}}</a></div></li>
        {% endfor %}
    </ul>
</ul>
</section>
{% endfor %}
</div>
{% endif %}

<script type="text/javascript">
    $(function(){
        $('#jtrainings').click(function(){
            $('#July').hide();
            $('#August').hide();
            $('#June').show();
            $('#ytrainings').removeClass('active');
            $('#atrainings').removeClass('active');
            $('#jtrainings').addClass('active');
            $('#ytrainings').addClass('inactive');
            $('#atrainings').addClass('inactive');            
            $('#jtrainings').removeClass('inactive');
        });

        $('#ytrainings').click(function(){
            $('#June').hide();
            $('#August').hide();
            $('#July').show();
            $('#jtrainings').removeClass('active');
            $('#atrainings').removeClass('active');
            $('#ytrainings').addClass('active');
            $('#jtrainings').addClass('inactive');
            $('#atrainings').addClass('inactive');            
            $('#ytrainings').removeClass('inactive');
        });
        $('#atrainings').click(function(){
            $('#June').hide();
            $('#July').hide();
            $('#August').show();
            $('#ytrainings').removeClass('active');
            $('#jtrainings').removeClass('active');
            $('#atrainings').addClass('active');
            $('#ytrainings').addClass('inactive');
            $('#jtrainings').addClass('inactive');            
            $('#atrainings').removeClass('inactive');
        });
    });
</script>