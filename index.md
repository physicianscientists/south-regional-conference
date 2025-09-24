---
layout: default
---

<!-- Header -->
<header class="header-object">

  <!-- Header Nav Bar -->
  <div class="navbar">

    <!-- BCM Logo -->
    <img src="assets/img/BCM_MSTP_SVG.png" alt="BCM logo" class="BCM-logo">

    <!-- Toggle Button Hamburger Menu -->
    <div class="toggle-button" id="toggleButton">
      <div class="bar"></div>
    </div>

    <!-- Navbar Links -->
    <ul class="nav-links" id="navLinks">
      <li class="li-nav"><a href="#purpose-section" class="li-anchor">Purpose</a></li>
      <li class="li-nav"><a href="#schedule-section" class="li-anchor">Schedule</a></li>
      <li class="li-nav"><a href="#speakers-section" class="li-anchor">Speakers</a></li>
      <li class="li-nav"><a href="#travel-section" class="li-anchor">Travel Info</a></li>
      <li class="li-nav"><a href="#organizers-section" class="li-anchor">Organizers</a></li>
      <li class="li-nav last-link" id="lastLink"></li>
    </ul>

    <!-- Social Medias -->
    <ul class="social-media-list" id="socialMediaList">
      <li>
        <a href="https://www.instagram.com/physicianscientists/" class="social-link" target="_blank">
          <img src="assets/img/instagram.png" alt="instagram" class="social-img">
        </a>
      </li>
      <li>
        <a href="https://twitter.com/apsa_tweets" class="social-link" target="_blank">
          <img src="assets/img/twitter.png" alt="twitter" class="social-img">
        </a>
      </li>
      <li>
        <a href="https://www.facebook.com/physicianscientists/" class="social-link" target="_blank">
          <img src="assets/img/facebook.png" alt="facebook" class="social-img">
        </a>
      </li>
      <li>
        <a href="https://www.linkedin.com/company/american-physician-scientists-association/" class="social-link" target="_blank">
          <img src="assets/img/linkedin.png" alt="linkedin" class="social-img">
        </a>
      </li>
      <li>
        <a href="https://www.youtube.com/channel/UCc1BYq6Ow8q5NjLXNVPD9_Q" class="social-link" target="_blank">
          <img src="assets/img/youtube.png" alt="youtube" class="social-img">
        </a>
      </li>
      <li>
        <a href="https://discord.gg/apsa" class="social-link" target="_blank">
          <img src="assets/img/discord.png" alt="discord" class="social-img">
        </a>
      </li>
    </ul>

  </div>

  <!-- Background Section - Slideshow -->
  <div class="slideshow-background">

    <!-- Slideshow container -->
    <div class="slideshow-container">

      <!-- Full-width images with number and caption text -->
      {% for slide in site.data.conference.slideshow %}
      <div class="slideshow slideshow-fade">
        <img src="{{ slide.image | relative_url }}" class="slideshow-images" alt="{{ slide.alt }}">
      </div>
      {% endfor %}

      <!-- Next and previous buttons -->
      <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
      <a class="next" onclick="plusSlides(1)">&#10095;</a>

      <!-- The dots/circles -->
      <div class="slideshow-dot-div">
        {% for slide in site.data.conference.slideshow %}
        <span class="slideshow-dot" onclick="currentSlide({{ forloop.index }})"></span>
        {% endfor %}
      </div>
    </div>

    <!-- Page Banner -->
    <div class="page-title">
      <img src="assets/img/APSA_Logo_White_Crop.png" alt="APSA logo" class="APSA-logo">
      <h2 class="banner-title">{{ site.data.conference.subtitle }}</h2>
      <div class="registration-button-div">

        <!-- Button for MD/PhD registration -->
        <div class="registration-subutton-div">
          <img src="assets/img/mdphd-logo.png" alt="mdphd-logo" class="tile-logo">
          <h3 class="tile-title">MD/PhD Students</h3>
          <p class="tile-link">{{ site.data.conference.registration.status }}</p>
        </div>

        <!-- Button for Undergrad registration -->
        <div class="registration-subutton-div">
          <img src="assets/img/undergrad-logo.png" alt="undergrad-logo" class="tile-logo">
          <h3 class="tile-title">Undergraduates</h3>
          <p class="tile-link">{{ site.data.conference.registration.status }}</p>
        </div>
      </div>
      <h3 class="registration-dates">Registration & Abstract Deadline: {{ site.data.conference.registration.deadline }}</h3>
      <h3 class="registration-dates">Conference Date: {{ site.data.conference.event.date }} from {{ site.data.conference.event.time }}</h3>
      <h3 class="registration-dates">Venue: {{ site.data.conference.event.venue }}</h3>
    </div>
  </div>

</header>


<!-- Purpose Section -->
<span class="anchor" id="purpose-section"></span>  <!-- Anchor Tag -->
<div class="purpose-section">
  <h1 class="purpose-title">Purpose</h1>

  <!-- About -->
  <div class="purpose-div">
    <h3 class="purpose-subtitles">{{ site.data.sections.purpose.about.title }}</h3>
    {{ site.data.sections.purpose.about.content | markdownify }}
    <div class="apsa-map-div">
      <img src="assets/img/us_apsa_map.svg" alt="us-apsa-map" class="apsa-map">
    </div>
  </div>

  <!-- Who should attend -->
  <div class="purpose-div">
    <h3 class="purpose-subtitles">{{ site.data.sections.purpose.who_should_attend.title }}</h3>
    {{ site.data.sections.purpose.who_should_attend.content | markdownify }}
  </div>

  <!-- Purpose: Registration -->
  <div class="purpose-div">
    <h3 class="purpose-subtitles">{{ site.data.sections.purpose.registration.title }}</h3>
    {{ site.data.sections.purpose.registration.content | markdownify }}
  </div>

  <!-- Abstracts and posters -->
  <div class="purpose-div">
    <h3 class="purpose-subtitles">{{ site.data.sections.purpose.abstracts.title }}</h3>
    {{ site.data.sections.purpose.abstracts.content | markdownify }}
  </div>

  <!-- Posters -->
  <div class="purpose-div">
    <h3 class="purpose-subtitles">{{ site.data.sections.purpose.posters.title }}</h3>
    {{ site.data.sections.purpose.posters.content | markdownify }}
  </div>

  <!-- Travel Awards -->
  <div class="purpose-div">
    <h3 class="purpose-subtitles">{{ site.data.sections.purpose.travel_awards.title }}</h3>
    {{ site.data.sections.purpose.travel_awards.content | markdownify }}
  </div>

</div>



<!-- Schedule Section -->
<span class="anchor" id="schedule-section"></span>  <!-- Anchor Tag -->
<div class="schedule-section">

  <h1 class="schedule-title">Schedule</h1>

  <div class="schedule-container">

    {% for event in site.data.schedule %}
    <!-- {{ event.title }} -->
    <div class="schedule-event-container">
      <p class="schedule-desc schedule-time">{{ event.time }}</p>
      <div class="schedule-speaker-container">
        {% if event.image %}
        <img src="{{ event.image | relative_url }}" alt="speaker" class="schedule-speaker-img">
        {% endif %}
        <div class="schedule-speaker-div">
          <p class="schedule-desc schedule-talk">{{ event.title }}</p>
          <p class="schedule-desc schedule-speaker-desc">{{ event.presenter }}</p>
        </div>
      </div>
    </div>
    {% endfor %}

  </div>

</div>



<!-- Speakers Section -->
<span class="anchor" id="speakers-section"></span>  <!-- Anchor Tag -->
<div class="speakers-section">
  <h1 class="speakers-title">Speakers</h1>

  {% for speaker in site.data.speakers %}
  <!-- {{ speaker.name }} -->
  <div class="speaker-container">
    <h2 class="speakers-subtitles left-speaker">{{ speaker.title }}</h2>
    <div class="speakers-div-left">
      <div class="speaker-picture-left-div">
        <img src="{{ speaker.image | relative_url }}" alt="speaker" class="speaker-picture">
        <p class="speaker-info speaker-name">{{ speaker.name }}</p>
        <p class="speaker-info speaker-affiliation">{{ speaker.affiliation }}</p>
      </div>
      <div class="speaker-description-div">
        {{ speaker.bio | markdownify }}
      </div>
    </div>
  </div>
  {% endfor %}

</div>



<!-- Travel Info Section -->
<span class="anchor" id="travel-section"></span>  <!-- Anchor Tag -->
<div class="travel-section">
  <h1 class="travel-titles">Travel Information</h1>

  <div class="travel-info-div">
    <h3 class="travel-subtitles">{{ site.data.travel.travel_instructions.title }}</h3>
    {{ site.data.travel.travel_instructions.content | markdownify }}
  </div>

  <div class="travel-info-div">
    <h3 class="travel-subtitles">{{ site.data.travel.hotel_accommodations.title }}</h3>
    {{ site.data.travel.hotel_accommodations.content | markdownify }}
  </div>

  <div class="travel-info-div">
    <h3 class="travel-subtitles">{{ site.data.travel.conference_center.title }}</h3>
    {{ site.data.travel.conference_center.content | markdownify }}
    {% if site.data.travel.conference_center.image %}
    <div class="travel-image-div">
      <img src="{{ site.data.travel.conference_center.image | relative_url }}" alt="NRI-instructions" class="travel-image">
    </div>
    {% endif %}
  </div>

  <div class="travel-info-div">
    <h3 class="travel-subtitles">{{ site.data.travel.meals.title }}</h3>
    {{ site.data.travel.meals.content | markdownify }}
  </div>

</div>


<!-- Organizers Section -->
<span class="anchor" id="organizers-section"></span>  <!-- Anchor Tag -->
<div class="organizers-section">

  <h1 class="organizers-title">Organizers</h1>
  <br>

  <!-- Board of Directors -->
  <div class="board-div">
    <h2 class="organizers-subtitles">BCM MSTP Leadership</h2>
    <div class="organizers-flexbox" id="organizersFlexbox1">
      <!-- Organizer cards will be populated by JavaScript -->
    </div>
  </div>

  <div class="board-div">
    <h2 class="organizers-subtitles">Local Organizing Committee</h2>
    <div class="organizers-flexbox" id="organizersFlexbox2">
      <!-- Organizer cards will be populated by JavaScript -->
    </div>
  </div>

</div>


<!-- Footer -->
<footer class="footer-section">

  <div class="footer-flexbox">

    <!-- APSA -->
    <div class="footer-subsection">
      <h4 class="footer-title">APSA</h4>
      <ul class="footer-list" id="footerList">
      </ul>
    </div>

    <!-- Additional Resources -->
    <div class="footer-subsection">
      <h4 class="footer-title">Additional Resources</h4>
      <ul class="footer-list">
        <li class="footer-desc">
          <a href="https://www.asci-jci.org/" target="_blank" class="footer-link">ASCI-JCI</a>
        </li>
        <li class="footer-desc">
          <a href="https://www.aap-online.org/" target="_blank" class="footer-link">AAP</a>
        </li>
        <li class="footer-desc">
          <a href="https://www.physicianscientists.org/page/career-navigation" target="_blank" class="footer-link">Career Navigation</a>
        </li>
      </ul>
    </div>

    <!-- Host -->
    <div class="footer-subsection">
      <h4 class="footer-title">Host</h4>
      <ul class="footer-list">
        <li class="footer-desc">
          <a href="https://www.bcm.edu/education/school-of-medicine/md-phd-medical-scientist-training-program" target="_blank" class="footer-link">BCM MSTP</a>
        </li>
        <li class="footer-desc">
          <a href="https://www.bcm.edu/" target="_blank" class="footer-link">Baylor College of Medicine</a>
        </li>
      </ul>
    </div>

    <!-- Sponsors -->
    <div class="footer-subsection">
      <h4 class="footer-title">Sponsors</h4>
      <div class="footer-sponsor-logos">
        <div class="footer-sponsor-logos-subdiv">
          <a href="https://www.bwfund.org/" target="_blank"><img src="assets/img/bwf-logo.png" alt="BWF-Logo" class="footer-logo"></a>
        </div>
        <div class="footer-sponsor-logos-subdiv">
          <a href="https://www.asci-jci.org/" target="_blank"><img src="assets/img/ASCI-logo.jpg" alt="ASCI-Logo" class="footer-logo"></a>
        </div>
      </div>
    </div>

  </div>

</footer>