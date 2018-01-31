+++
date = "2014-07-11T10:54:24+02:00"
title = "Talks"
image = ""
slug = "talks"
draft = false
menu = ""
comments = false
share = false
noauthor = false
aligncenter = true

+++

Some talks I have given in the past.

#### From Media Types to MicroTypes and Introspected REST
_APIDays Paris conference, January 2018._

<iframe src="//slides.com/vasilakisfil/from-media-types-to-microtypes/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

A talk again specifically for MicroTypes was hosted in APIDays in Paris,
that was targeted to more advanced audience and covered the whole
MicroTypes concept with rigid definition of each property along with its implementation in HTTP.
Towards the end we discussed new paradigms that such architecture could lead (i.e. introspecting capabilities of HTTP APIs for configurability, discovery of capabilities etc).

Unfortunately no video or recorded audio of this talk is available although it was very interesting talk because I could finally explain the whole concept
without fearing that I will lose the audience. Lesson learned: next time I give a talk and I don't see cameras I will record the audio of my talk with my phone..


#### MicroTypes: Composability in HTTP APIs
_Nordic APIs conference, October 2017._

<iframe src="//slides.com/vasilakisfil/microtypes-composability-for-http-apis/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

Microtypes in combination with reactive negotiation, a forgotten but still valid negotiation mechanism in HTTP,
can give us enormous possibilities when designing a new API by allowing the API designers to tailor the API
capabilities to their needs while at the same time it enables clients to negotiate parts of the API functionality
that are only interested or understand and not the Media Type as a whole. Choosing between REST or GraphQL won’t
be necessary as APIs can support both styles progressively, simultaneously, or asymmetrically for different
classes of clients, using multiple sets of MicroTypes.

There is a video version available as well from the talk.
<iframe width="560" height="315" src="https://www.youtube.com/embed/pc8ZyFjJY4A" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>


#### Sliding away from Roy Fielding's REST model
_Nordic APIs conference, October 2016._

<iframe src="//slides.com/vasilakisfil/sliding-away-from-roy-fielding-rest-model/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

We go through what a modern REST API is, see what are the least features we should provide to the clients,
how we can test it super fast (because testing APIs can be very time consuming!) and how we can optimize it's performance.
The talk is not bound to any specific API spec (JSONAPI, Serien, HAL etc) but goes though all the principles of a modern REST API.

However it challenges Roy Fieldings's thesis on REST APIs (is it still valid, 17 years later?) along with current specs which are
based on Roy's thesis (like JSONAPI spec) especially when high performance is part of the API design.

There is a video version available as well from that talk.
<iframe width="560" height="315" src="https://www.youtube.com/embed/RY_kMXEJZfk" frameborder="0" allowfullscreen></iframe>

#### Building real world apps in EmberJS
_Stockholm EmberJS Meetup, May 2016._

<iframe src="//slides.com/vasilakisfil/emberjs26-tutorial/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

Shows how you can build a real app on Ember and not yet another ToDo list.
Highlights latest Ember features and common practices.


#### APIs on Ruby (and possible Rails)
_Athens Ruby Meetup, January 2016._

<iframe src="//slides.com/vasilakisfil/apis-on-ruby-and-rails/embed" width="560" height="315" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

Discusses best practices for building, testing and optimizing modern APIs.
Ruby and Rails is used in the slides but the practices should be the same regadless the language.

It reflects Videofy's backend we built in the end of 2015.
