---
layout: workshop      # DON'T CHANGE THIS.
carpentry: ""    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "The Jackson Laboratory"
address: "Bioinformatics Training Room, 600 Main Street, Bar Harbor, Maine"
country: "us"
language: "en"
latlng: "44.365646, -68.197153"
humandate: "June 14-15, 2018"
humantime: "9:00 am - 4:30 pm"
startdate: 2018-06-14
enddate: 2018-06-15
instructor: ["Georgi Kolishovski", "Sue McClatchy"]
helper: ["Selcan Aydin", "Daniel Alfonsetti"]
email: ["susan.mcclatchy@jax.org"]
collaborative_notes:
eventbrite: 44045876402
---

<!-- See instructions in the comments below for how to edit specific sections of this workshop template. -->

<!--
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'bin/workshop_check.py' *before* committing to make sure that changes are good.
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
height="268px"
scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

<!--
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
-->
{% if page.carpentry == "swc" %}
{% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

<!--
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
-->
{% if page.carpentry == "swc" %}
{% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

<!--
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use http://itouchmap.com/latlong.html to find the lat/long of an
address.
-->
{% if page.latlng %}
<p id="where">
<strong>Where:</strong>
{{page.address}}.
Get directions with
<a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
or
<a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
JAX employees can locate the bioinformatics training room in building 1, unit 5 on
this <a href="https://myjax-p.jax.org/Facilities/engineering/GeneralMap/rl_locator_map.pdf">campus map</a>.
</p>
{% endif %}

<!--
DATE

This block displays the date and links to Google Calendar.
-->
{% if page.humandate %}
<p id="when">
<strong>When:</strong>
{{page.humandate}}.
{% include workshop_calendar.html %}
</p>
{% endif %}

<!--
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
-->
<p id="requirements">
<strong>Requirements:</strong> Participants must bring a laptop with a
Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
on. They should have a few specific software packages installed (listed
<a href="#setup">below</a>). They are also required to abide by the
{% if page.carpentry == "swc" %}
Software Carpentry's
{% elsif page.carpentry == "dc" %}
Data Carpentry's
{% elsif page.carpentry == "lc" %}
Library Carpentry's
{% endif %}
<a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

<!--
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
-->
<p id="accessibility">
<strong>Accessibility:</strong> We are committed to making this workshop
accessible to everybody.
The workshop organisers have checked that:
</p>
<ul>
<li>The room is wheelchair / scooter accessible.</li>
<li>Accessible restrooms are available.</li>
</ul>
<p>
Materials will be provided in advance of the workshop and
large-print handouts are available if needed by notifying the
organizers in advance.  If we can help making learning easier for
you (e.g. sign-language interpreters, lactation facilities) please
get in touch (using contact details below) and we will
attempt to provide them.
</p>

<!--
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
-->
<p id="contact">
<strong>Contact</strong>:
Please email
{% if page.email %}
{% for contact in page.email %}
{% if forloop.last and page.email.size > 1 %}
or
{% else %}
{% unless forloop.first %}
,
{% endunless %}
{% endif %}
<a href='mailto:{{page.email}}'>{{page.email}}</a>
{% endfor %}
{% else %}
to-be-announced
{% endif %}
for more information.
</p>

<hr/>

<!--
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
-->
<h2 id="schedule">Schedule</h2>

<div class="row">
<div class="col-md-6">
<h3>Thursday, June 14</h3>
<table class="table table-striped">
<tr> <td>09:00</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/">Workshop Overview</a></td> </tr>
<tr> <td>09:15</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/01-run-quit/">Running and Quitting</a></td> </tr>
<tr> <td>09:45</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/02-variables/">Variables and Assignment</a></td> </tr>
<tr> <td>10:15</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/03-types-conversion/">Data Types and Type Conversion</a></td> </tr>
<tr> <td>10:45</td>  <td>Coffee</td> </tr>
<tr> <td>11:00</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/04-built-in/">Built-in Functions and Help</a></td> </tr>
<tr> <td>11:30</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/06-libraries/">Libraries</a></td> </tr>
<tr> <td>12:00</td>  <td>Lunch break</td> </tr>
<tr> <td>13:00</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/07-reading-tabular/">Reading Tabular Data into DataFrames</a></td> </tr>
<tr> <td>13:45</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/08-data-frames/">Pandas DataFrames</a></td> </tr>
<tr> <td>14:30</td>  <td>Coffee</td> </tr>
<tr> <td>14:45</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/09-plotting/">Plotting</a></td> </tr>
<tr> <td>15:30</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/11-lists/">Lists</a></td> </tr>
<tr> <td>16:15</td>  <td>Wrap-up</td> </tr>
</table>
</div>
<div class="col-md-6">
<h3>Friday, June 15</h3>
<table class="table table-striped">
<tr> <td>09:00</td>  <td><a href="{{site.swc_pages}}/python-novice-gapminder/14-writing-functions/">Writing Functions</a></td> </tr>
<tr> <td>10:00</td>  <td><a href="https://github.com/narayananr/Python_SWC_Workshop/blob/master/Publication_Quality_Graphics.ipynb">Publication Quality Graphics</a> </td> </tr>
<tr> <td>10:00</td>  <td><a href="https://raw.githubusercontent.com/narayananr/Python_SWC_Workshop/master/Attie_Liver_CC_Founders_EMASE_10k_counts.tsv">Get the data here or run exp_data_url = 'http://bit.ly/2FUEwxW'</a> </td> </tr>
<tr> <td>10:45</td>  <td>Coffee</td> </tr>
<tr> <td>11:00</td>  <td><a href="https://github.com/narayananr/Python_SWC_Workshop/blob/master/Publication_Quality_Graphics.ipynb">Publication Quality Graphics</a> </td> </tr>
<tr> <td>11:30</td>  <td>End</td> </tr>
</table>
</div>
</div>



<!--
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.software-carpentry.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
-->
{% if page.collaborative_notes %}
<p id="collaborative_notes">
We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

<!--
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
-->
<table class="table table-striped">
<div class="col-md-6">
<h3 id="syllabus-python">Programming in Python</h3>
<ul>
<li>Using libraries</li>
<li>Working with arrays</li>
<li>Reading and plotting data</li>
<li>Creating and using functions</li>
<li>Loops and conditionals</li>
<li>Defensive programming</li>
<li>Using Python from the command line</li>
<li><a href="{{site.swc_pages}}/python-novice-inflammation/reference/">Reference...</a></li>
</ul>
</div>
</table>

<!--
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
-->

<h2 id="setup">Setup</h2>

<p>
To participate in a
{% if page.carpentry == "swc" %}
Software Carpentry
{% elsif page.carpentry == "dc" %}
Data Carpentry
{% elsif page.carpentry == "lc" %}
Library Carpentry
{% endif %}
workshop,
you will need access to the software described below.
In addition, you will need an up-to-date web browser.
</p>
<p>
We maintain a list of common issues that occur during installation as a reference for instructors
that may be useful on the
<a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>


<div id="python"> <!-- Start of 'Python' section. Remove the third paragraph if
the workshop will teach Python using something other than
the Jupyter notebook.
Details at https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility -->
<h3>Python</h3>

<p>
<a href="http://python.org">Python</a> is a popular language for
research computing, and great for general-purpose programming as
well.  Installing all of its research packages individually can be
a bit difficult, so we recommend
<a href="https://www.anaconda.com/distribution/">Anaconda</a>,
an all-in-one installer.
</p>

<p>
Regardless of how you choose to install it,
<strong>please make sure you install Python version 3.x</strong>
(e.g., 3.6 is fine).
</p>

<p>
We will teach Python using the <a href="https://jupyter.org/">Jupyter notebook</a>,
a programming environment that runs in a web browser. For this to work you will need a reasonably
up-to-date browser. The current versions of the Chrome, Safari and
Firefox browsers are all
<a href="https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility">supported</a>
(some older browsers, including Internet Explorer version 9
and below, are not).
</p>

<div class="row">
<div class="col-md-4">
<h4 id="python-windows">Windows</h4>
<a href="https://www.youtube.com/watch?v=xxQ0mzZ8UvA">Video Tutorial</a>
<ol>
<li>Open <a href="https://www.anaconda.com/download/#windows">https://www.anaconda.com/download/#windows</a> with your web browser.</li>
<li>Download the Python 3 installer for Windows.</li>
<li>Install Python 3 using all of the defaults for installation <em>except</em> make sure to check <strong>Make Anaconda the default Python</strong>.</li>
</ol>
</div>
<div class="col-md-4">
<h4 id="python-macosx">Mac OS X</h4>
<a href="https://www.youtube.com/watch?v=TcSAln46u9U">Video Tutorial</a>
<ol>
<li>Open <a href="https://www.anaconda.com/download/#macos">https://www.anaconda.com/download/#macos</a> with your web browser.</li>
<li>Download the Python 3 installer for OS X.</li>
<li>Install Python 3 using all of the defaults for installation.</li>
</ol>
</div>
<div class="col-md-4">
<h4 id="python-linux">Linux</h4>
<ol>
<li>Open <a href="https://www.anaconda.com/download/#linux">https://www.anaconda.com/download/#linux</a> with your web browser.</li>
<li>Download the Python 3 installer for Linux.<br>
(The installation requires using the shell. If you aren't
comfortable doing the installation yourself
stop here and request help at the workshop.)
</li>
<li>
Open a terminal window.
</li>
<li>
Type <pre>bash Anaconda3-</pre> and then press
tab. The name of the file you just downloaded should
appear. If it does not, navigate to the folder where you
downloaded the file, for example with:
<pre>cd Downloads</pre>
Then, try again.
</li>
<li>
Press enter. You will follow the text-only prompts. To move through
the text, press the space key. Type <code>yes</code> and
press enter to approve the license. Press enter to approve the
default location for the files. Type <code>yes</code> and
press enter to prepend Anaconda to your <code>PATH</code>
(this makes the Anaconda distribution the default Python).
</li>
<li>
Close the terminal window.
</li>
</ol>
</div>
</div>
<!--
<p>
Once you are done installing the software listed above,
please go to <a href="setup/index.html">this page</a>,
which has instructions on how to test that everything was installed correctly.
</p>
-->
</div> <!-- End of 'Python' section. -->

