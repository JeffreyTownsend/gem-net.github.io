---
layout: home
title: GEM-NET Home
---

<header class="masthead">
    <div class="container header-content">
        <div class="header-content-inner">
            <h1 id="homeHeading">Center for Genetically Encoded Materials</h1>
            <hr>
            <h3>Transforming the fabric of society with genetically encoded chemical polymers</h3>
            <a class="btn btn-primary btn-xl" href="#about">Learn More</a>
        </div>
    </div>
    <div style="position:absolute;right:5px;bottom:0px"><h6 class="text-faded"><small>Illustration by Nicolle Rager, NSF</small></h6></div>
</header>


<section id="about" class="front-section">
    <div class="container">
        <div class="row">
            <div class="col-lg-12 text-center">
                <h2 class="section-heading">About C-GEM</h2>
                <hr class="primary">
            </div>
        </div>
    </div>
    <div class="container">
        <div class="row">
            <div class="col-lg-3 col-md-6 text-center">
                <div class="service-box">
                    <i class="fa fa-3x fa-flag text-primary sr-icons"></i>
                    <a href="#mission"><h3>Our mission</h3></a>
                    <h5 class="text-muted">Establish a fundamentally new form of chemical matter</h5>
                </div>
            </div>
            <div class="col-lg-3 col-md-6 text-center">
                <div class="service-box">
                    <i class="fa fa-3x fa-flask text-primary sr-icons"></i>
                    <a href="#science"><h3>The Science</h3></a>
                    <h5 class="text-muted">Re-engineering the cell's protein synthesizing machine</h5>
                </div>
            </div>
            <div class="col-lg-3 col-md-6 text-center">
                <div class="service-box">
                    <i class="fa fa-3x fa-users text-primary sr-icons"></i>
                    <a href="#team"><h3>Our Team</h3></a>
                    <h5 class="text-muted">A multi-institution collaboration</h5>
                </div>
            </div>
            <div class="col-lg-3 col-md-6 text-center">
                <div class="service-box">
                    <i class="fa fa-3x fa-newspaper-o text-primary sr-icons"></i>
                    <a href="news"><h3>Latest News</h3></a>
                    <h5 class="text-muted">Hot off the press</h5>
                </div>
            </div>
        </div>
    </div>
</section>


<section class="bg-primary front-section" id="mission">
    <div class="container">
        <div class="row">
            <div class="col-lg-10 offset-lg-1 text-center">
                <h2 class="section-heading text-white">Our mission</h2>
                <hr class="light">
                <div class="text-faded" markdown="1">{% include txt/mission.txt %}</div>
                <a class="btn btn-primary btn-xl sr-button" href="#science">How it works</a>
            </div>
        </div>
    </div>
</section>


<section id="science" class="front-section">
    <div class="container">
        <div class="row">
            <div class="col-lg-10 offset-lg-1 text-center">
                <h2 class="section-heading">The science</h2>
                <!-- <i class="fa fa-2x fa-flask text-primary sr-icons"></i> -->
                <hr class="primary">
                <div markdown="1">{% include txt/science.txt %}</div>
            </div>
        </div>
    </div>
    <div class="container-fluid">
        <div class="row no-gutter popup-gallery">
        {% for im in site.data.slideshow_ims %}
            <div class="col-lg-4 col-sm-6">
                <a class="portfolio-box" href="{{ im.full }}">
                    <img class="img-fluid" src="{{ im.thumb }}" alt="" style="width: 100%;">
                    <div class="portfolio-box-caption">
                        <div class="portfolio-box-caption-content">
                            <div class="project-category text-faded">
                                {{ im.categ }}
                            </div>
                            <div class="project-name">
                                {{ im.name }}
                            </div>
                        </div>
                    </div>
                </a>
            </div>
        {% endfor %}
        </div>
    </div>
    <div class="text-center mt-3">
        <a class="btn btn-primary btn-xl sr-button" href="#team">Our Team</a>
    </div>

</section>


<section id="team" class="bg-faded front-section">
    <div class="container">
        <div class="row">
            <div class="col-lg-10 offset-lg-1 text-center">
                <h2 class="section-heading">Meet the team</h2>
                <hr class="primary">
            </div>
        </div>
{% for person in site.data.key_members %}
    {% assign row_ind = forloop.index0 | modulo:3 %}
    {% assign offset_class = "" %}
    {% if row_ind == 0  %}
        {% if forloop.rindex == 1  %}  <!-- SET OFFSET FOR LAST ROW -->
            {% assign offset_class = "offset-sm-4" %}
        {% elsif forloop.rindex == 2 %}
            {% assign offset_class = "offset-sm-2" %}
        {% endif %}  
        <div class="row">
    {% endif %}
            <div class="col-sm-4 {{ offset_class }}">
                <a href="{{ person.page }}">
                    <div class="vira-card">
                        <div class="vira-card-header">
                            <img class="rounded-circle" src="img/team/{{ person.pic }}" alt="{{ person.name }}" width="140" height="140">
                        </div>
                        <div class="vira-card-content">
                            <h4>{{ person.name }}</h4>
                            <p class="text-muted">{{ person.role }}</p>
        <!--                         <div class="social-icons">
                                <ul>
                                    <a href="#"><li><span class="ion-social-facebook"></span></li></a>
                                    <a href="#"><li><span class="ion-social-twitter"></span></li></a>
                                </ul>
                            </div> -->
                        </div>
                    </div>
                </a>
            </div>
    {% if row_ind == 2 or forloop.rindex0 == 0 %}
        </div><!-- END OF PEOPLE ROW -->
    {% endif %}
{% endfor %}
    </div>
</section>


<!-- <section class="no-padding" id="portfolio">

</section> -->


<!-- <div class="call-to-action bg-dark">
    <div class="container text-center">
        <h2>Free Download at Start Bootstrap!</h2>
        <a class="btn btn-default btn-xl sr-button" href="http://startbootstrap.com/template-overviews/creative/">Download Now!</a>
    </div>
</div> -->

<section id="contact" class="front-section">
    <div class="container">
        <div class="row">
            <div class="col-lg-8 offset-lg-2 text-center">
                <h2 class="section-heading">Let's Get In Touch!</h2>
                <hr class="primary">
                <p>Contact us on Twitter or send us an email and we will get back to you as soon as possible!</p>
            </div>
            <div class="col-lg-4 offset-lg-2 text-center">
                <i class="fa fa-twitter fa-3x sr-contact"></i>
                <p><a href="https://twitter.com/{{ site.twitter_username }}">@{{ site.twitter_username }}</a></p>
            </div>
            <div class="col-lg-4 text-center">
                <i class="fa fa-envelope-o fa-3x sr-contact"></i>
                <p><a href="mailto:{{ site.email }}">{{ site.email }}</a></p>
            </div>
        </div>
    </div>
</section>

