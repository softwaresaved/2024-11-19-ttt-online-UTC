---
layout: workshop      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "Software Sustainability Institute"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "online"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "gb"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the workshop
latitude: "45"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-1"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "9-12 July 2024"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "090:00 - 13:00"    # human-readable times for the workshop e.g., "9:00 am - 4:30 pm CEST (7:00 am - 2:30 pm UTC)"
startdate: 2024-07-09      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2024-07-12        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Steve Crouch", "Aleksandra Nenadic"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: []     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["a.nenadic@software.ac.uk"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:  # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

<!-- See instructions in the comments below for how to edit specific sections of this workshop template. -->

<!--
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'tools/check' *before* committing to make sure that changes are good.
-->

<!--
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
-->
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->

<p>
<a href="{{ site.carpentries_site }}">The Carpentries</a> is a community of practice centered around teaching foundational
  coding and data science skills to researchers worldwide. This Instructor Training
  event is designed to prepare trainees to certify and participate as Carpentries
  Instructors. However, much of our curriculum focuses on educational principles that
  apply across a wide variety of contexts. We also welcome participants who do not plan
  to certify but simply wish to become a better teacher.
</p>

<p>Carpentries Instructor Training has the following goals:</p>

* Introduce you to evidence-based teaching practices.
* Teach you how to create a positive environment for learners at your workshops.
* Provide opportunities for you to practice and build your teaching skills.
* Help you become integrated into the Carpentries community.
* Prepare you to use these teaching skills in teaching Carpentries workshops.

<p> Because we have only limited time, some things are beyond the scope of this training. We will
not be learning:</p>

* How to program in R or Python, use Git or SQL, or any of the other topics taught in  <a href="{{ site.dc_site }}">Data Carpentry</a>,
  <a href="{{ site.lc_site }}">Library Carpentry</a>, or
  <a href="{{ site.swc_site }}">Software Carpentry</a> workshops.
* How to create your own lessons from scratch. However, this Instructor Training serves as a good precursor to [The Carpentries Lesson Developer Training]({{ site.lessondev_training_site }}).


<p>
Instructor Training events are hands-on throughout: short lessons alternate
with individual and group practical exercises, including practice teaching sessions.
This Instructor Training event is the first step towards certification as a
Carpentries Instructor. For more details on the other 3 steps, see the <a href="{{ site.training_site }}/checkout.html">Checkout Instructions</a> page.
For more information, see our <a href="{{ site.training_site }}">Instructor Training Curriculum</a>.
</p>

<h3>Code of Conduct</h3>

All participants are required to abide by The Carpentries <a href="{{
site.swc_site }}/conduct/">Code of Conduct</a>.



{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
  -->
<h3 id="where">Where</h3>


{% if online == "false" %}
<p id="venue">
  {{page.address}}.
  {% if page.latitude and page.longitude %}
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
  {% endif %}
</p>
{% elsif online == "true_public" %}
<p id="venue">
  Online at <a href="{{page.address}}">{{page.address}}</a>.
  The training will be conducted using the Zoom video conferencing platform. No log-in is needed.
  However, if you have not used Zoom before, please click the link a few minutes early as it may prompt you to
  install the Zoom app or browser extension. You should have received a connection link in the same email that
  directed you to this website. If you found this page by another means and did not receive the connection link,
  please check your spam folder and email instructor.training@carpentries.org with your Trainers (contact details below) on cc.
</p>
{% elsif online == "true_private" %}
<p id="venue">
  This training will take place online.
  The instructors will provide you with the information you will need to connect to this meeting.
</p>
{% endif %}

<h4 id="accessibility">Accessibility</h4>

We are committed to making this training
accessible to everybody.
{% if online == "false" %}Organisers have checked that:

<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
{% endif %}

Materials will be provided in advance of the event.

We do not require participants to provide documentation of disabilities or disclose any unnecessary personal information. 
However, we do want to help create an inclusive, accessible experience for all participants.
We encourage you to share any information that would be helpful to make your Carpentries experience accessible.
To request an accommodation for this training, please fill out the
<a href="https://carpentries.typeform.com/to/B2OSYaD0">accommodation request form</a>.
If you have questions or need assistance with the accommodation form please <a href="mailto:team@carpentries.org">email us</a>.

<h3>How to Prepare for Instructor Training</h3>

Before your training, please visit our Preparing for Instructor Training page for complete instructions. A brief summary of these instructions is as follows
<ol>
  <li>Complete our Pre-training Survey. You will receive a custom link for your event when you receive your connection information.</li>
  <li>Select a lesson to use for teaching practice sessions and prepare a 3 minute segment, spending no more than 20-30 minutes to prepare.</li>
  <li>Please read the following:</li>
    <ul>
      <li><a href="https://carpentries.github.io/instructor-training/files/papers/science-of-learning-2015.pdf">The Science of Learning</a></li>
      <li><a href="https://carpentries.org/files/reports/2021%20Carpentries%20Annual%20Report_Final.pdf">The Carpentries Annual Report</a></li>
    </ul>
</ol>

<h3> Checkout: The Instructor Certification Process</h3>
After the training event, we ask you to complete three follow-up tasks to become a certified Instructor. These requirements are detailed on our
  <a href="{{ site.training_site }}/checkout.html">Checkout Instructions</a> page and will be discussed at our training.

{% if online == "false" %}
<h3>What to Bring to an In-Person Event</h3>

Participants should bring a laptop that is Internet connected and has a
functioning browser. If you have it, a device for recording audio and video
(mobile phones and laptops are OK) is useful as we
are going to record one another teaching in pairs or threes. It does not have
to be high-quality, but it should be good enough that you can understand what
someone is saying.
{% endif %}

<h3>Attendance and Cancellation</h3>
Trainees who miss more than 1 hour of the training may be marked absent.
Instructor certification cannot be completed without full attendance at
an Instructor Training event. If you unexpectedly need to miss more than
1 hour of your event, please contact your Trainers (contact info below).

For events in which registration occurs through The Carpentries via Eventbrite,
cancellation may be performed in Eventbrite up to the start of the event.
Canceled seats cannot be filled after the 1 week registration deadline for these events,
so we ask that you only cancel if absolutely necessary.

More information on our <a href="https://docs.carpentries.org/topic_folders/instructor_training/cancellations_and_makeups.html">cancellation and makeup policy</a> is available in The Carpentries Handbook.

<h3 id="contact">Contact</h3>
<p>
Please email
{% if page.contact %}
  {% for contact in page.contact %}
    {% if forloop.last and page.contact.size > 1 %}
      or
    {% else %}
      {% unless forloop.first %}
      ,
      {% endunless %}
    {% endif %}
    <a href='mailto:{{contact}}'>{{contact}}</a>
  {% endfor %}
{% else %}
  to-be-announced
{% endif %}
for more information.
</p>

<hr/>

<h2 id="preparation" name="preparation">Preparation</h2>

<p>
  Please read the following before the training begins:
</p>
<ol>
  <li><a href="{{ site.training_site }}/papers/science-of-learning-2015.pdf">The Science of Learning</a></li>
  <li><a href="https://carpentries.org/files/reports/2021%20Carpentries%20Annual%20Report_Final.pdf">The Carpentries 2021 Annual Report</a></li>
</ol>
<p>
  Please also read through <em>one</em> episode of one of The Carpentries lessons below
  carefully, so that you can do some exercises based on it on the
  first day of the class.  An episode is one page of a lesson.
</p>

  <ul>
  <li><a href="{{ site.dc_site }}/lessons">Data Carpentry Lessons</a></li>
  <li><a href="{{ site.lc_site }}/lessons">Library Carpentry Lessons</a></li>
  <li><a href="{{ site.swc_site }}/lessons">Software Carpentry Lessons</a></li>
  </ul>


<hr/>

<h2 id="materials" name="materials">Training Materials and Schedule</h2>

<p>
  Please see <a href="{{ site.training_site }}/instructor/index.html#schedule">the Instructor Training Curriculum</a> for course material and sample schedule for a 2-day event.
</p>


<hr/>

<!--
NOTE: This space can be customized to reflect the unique schedule of your training. If you would like it to display,
adjust the times and titles, then delete the characters above and below that serve to comment it out.
-->

<div class="row">
  <div class="col-md-6">
    <h3>Day 1, Tuesday 15 June 2021, 09:15-12:30</h3>
    <table class="table table-striped">
      <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/01-welcome/index.html">Welcome and Introduction</a></td> </tr>
      <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/02-practice-learning/index.html">Building Skill With Practice</a></td> </tr>
      <tr><td>Break</td> </tr>
      <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/03-expertise/index.html">Expertise and Teaching</a></td> </tr>
      <tr><td>Break</td> </tr>
      <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/05-memory/index.html">Memory and Cognitive Load</a></td> </tr>
      <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/06-feedback/index.html">Building Skill With Feedback</a></td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Day 2, Wednesday 16 June 2021, 09:15-12:30</h3>
    <table class="table table-striped">
      <tr><td>Recap of Day 1</td> </tr>
      <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/08-motivation/index.html">Motivation and Demotivation</a></td> </tr>
      <tr><td>Break</td> </tr>
      <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/11-practice-teaching/index.html">Teaching is a (Learned) Skill: Building Teaching Skill With Practice</a></td> </tr>      
      <tr><td>Break</td> </tr>
      <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/12-homework/index.html">Wrap-Up and Homework for Tomorrow</a></td> </tr>
   </table>
  </div>
</div>

<div class="row">
  <div class="col-md-6">
    <h3>Day 3, Thursday 17 June 2021, 09:15-12:30</h3>
        <table class="table table-striped">
          <tr><td>Recap of Day 2</td> </tr>
          <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/14-live/index.html">Live Coding is a Skill</a></td> </tr>
          <tr><td>Break</td> </tr>
          <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/17-performance/index.html">More Practice Live Coding</a></td> </tr>
          <tr><td>Break</td> </tr>
          <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/18-management/index.html">Managing a Diverse Classroom</a></td> </tr>
        </table>
  </div>
  <div class="col-md-6">
    <h3>Day 4, Friday 18 June 2021, 09:15-12:30</h3>
    <table class="table table-striped">
          <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/21-carpentries/index.html">The Carpentries: How We Operate</a></td> </tr>
          <tr><td>Break</td> </tr>
          <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/20-checkout/index.html">Checkout Process and Q & A session</a></td> </tr>
          <tr><td>Break</td> </tr>
          <tr><td><a target="_blank" href="https://carpentries.github.io/instructor-training/24-practices/index.html">Putting It Together</a></td> </tr>
          <tr><td>Wrap-up & <a target="_blank" href="{{ site.instructor_post_survey }}{{ site.github.project_title }}">Post-Workshop Survey</a></td> </tr>
    </table>
  </div>
</div>

<!--
  ETHERPAD

  At `_misc/etherpad.txt` you will find a template for the etherpad.

  Display the Etherpad for the workshop.  You can set this up in
  advance or on the first day; either way, make sure you push changes
  to GitHub after you have its URL.  To create an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
-->
{% if page.etherpad %}
<hr/>

<p id="etherpad">
  <strong>Etherpad:</strong> <a href="{{page.etherpad}}">{{page.etherpad}}</a>.
  <br/>
  We will use this Etherpad for chatting, taking notes, and sharing URLs and bits of code.
</p>

{% endif %}

<h2 id="pre_workshop_survey">Surveys</h2>

<p>
  Before attending the training, please fill out <a href="{{ site.instructor_pre_survey }}{{ site.github.project_title }}">our pre-training survey</a>.
</p>


<p>
  After the training, please fill out <a href="{{ site.instructor_post_survey }}{{ site.github.project_title }}">our post-training survey</a>.
</p>
