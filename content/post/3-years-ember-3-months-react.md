+++
comments = true
image = ""
title = "3 years in Ember, 5 months in React"
author = ""
share = true
menu = ""
date = "2017-04-02"
draft = true

+++


I still remember my first days in Ember: it was exactly 3 years ago and Ember was in version 1.5.7.
After going through the whole documentation of "the framework for creating ambitious web applictions" I sat down and
and started creating my first routes and templates, following the client's specifications.
At that time, Ember was both magical and awful.
Magical because I had never seen anything like that, it was my first experience with **reactive programming** and
to be honest, it took me a while to figure out that classic software engineering
patterns don't always work for reactive programming.
On the other side, working on what was called at that time handlebars was awful and I still remember the uglyness of `bind-attr`
if you wanted to.. bind a property of a component or controller (yes at that time controllers where a thing!) to an html tag.
Working on handlebars was really awful, but that was in 2014 when React hadn't even announced and the only real alternative,
full-stack front-end framework, was AngularJS.

Why we chose Ember? Not sure, probably as a Rails shop, we felt right to go for a framework that follows
Rails philosophy of convention over configuration.
At that time I had just seen ember-cli (an alternative of Ember kit), that was supposed to help
you with setting up your Ember app and had some Rails-inspired generators like `ember generate route Index`.
I never really liked generators in Rails, I never used them anyway but ember-cli was good to have mostly because
it could package your app easily: it was a tool where you could work with and without it you would have to set up
the scripts etc yourself, something that reminded me front-end development of the past decade.
I clearly remember wondering myself if I did the right choice to setup the Ember project using ember-cli.

3 years fast forward, in Kollegorna we have taken more Ember projects and I have personally done a lot of Ember on the side
from small apps to huge ones.
All that time I loved Ember because it makes me super performant: if you asked me to create a prototype for a client
in Ember + Rails or in plain Rails, I would definitely go with Ember: I don't even need an API, I will just setup the localstsorage adapter,
structure the models the way I want, add some factories for test data and start coding.
And when you have actually worked with frameworks that allow you to update the dom that easily, it's not fun
going back to the conventional way of setting up a web page, like Rails views.
It wouldn't be an overstatement that Ember has changed my way of thinking, especially in complex DOM elements, like forms.
And if handlebars felt like primitive, latest HTMLBars are very powerful, or at least powerful enough that you don't need
something more. ++ about addons

5 months ago, I was announced that I will work closely with a client that wants to create a new front-end app on React.
To be honest I was super happy about it. **Finally**, I would have some hands-on experience with the thing called React
and its ecosystem. Everyone have been talking about React, the data-down-actions-up pattern was so revolutionary,
that even Ember adopted it (= added better support for it) and I won't be lying if I say Ember community
has been influenced by React patterns, taking probably the things that make sense.
I was super happy about it.


First day I started working with React I sat down and read the official docs.
After 3 years of experience with Ember, I could not only gasp React in a few hours but also understood pretty well
why things are like that along with common patterns when using it.
In essence, I would say that a [React component]() isn't much different than an [Ember component]().
Everything seemed great and I was super excited.
Funny thing is that the client's lead front-end developer, when he was showing me the current, a week's, code
he mentioned that it took them 3 days to setup webpack.
OK I had heard that webpack configuration is a bit tough, nothing surprising here, at least it was working ;)

From the very beginning we figured out that we won't manage going far with React only.
The code-base already had React-Router, for routing but we needed something that can manage things on the side,
like Ember services, because you can't inject properties all the way down to all components.
React-Redux was an obvious choice: Redux has been so popular about managing the state in a React project,
we have been hearing it everywhere, actually when working with Ember I was hearing so much about react-redux
that it revolutionizes the state management somehow.

Unfortunately as the time passed I was start realizing that React and its ecosystem misses some crucial
things that otherwise you find them in a regular fron-end framework like EmberJS, AngularJS, VueJS etc.


### Webpack is hard, but probably worth learning it
5 months in a React project, I never really touched webpack.
But I **did** try to understand it through its documentationa and tutorials but never
really grasp everything.
To me it seems like Webpack is becoming a de-facto standard in front-end development,
unfortunately, but I never had any problem with Ember.
I think the closest in Ember is Broccoli in combination with ember-cli, which
both are very easy to understand.

### No fixed structure on React
Another thing that striked me is the fact that React or Webpack doesn't come
with a system that removes the need to explicitly write down absolut paths (relative
to the project's root folder) when you import modules.
Having imports like

```
import '../../../MyComponent';
```

would be very classic in our React codebase.
Not a big problem, only when we moved components around we had to update the imports correctly.

In Ember you don't deal with
where you do the import. Instead, you care where the file you want to import
is, related to the project's root.
Actually components are automatically imported, but if you wanted to use  service
or something else.

```
import 'my-ember/services/session';
```

### JSX or HTMLBars, choice is yours but I slightly prefer HTMLBars
Having worked with Ember's HTMLbars, JSX templates looked a bit weird to me only the first month,
then it felt natural.

However, if you asked me now, HTMLBars or JSX, I would say to you I am fine with both, but if I had a choice, I would choose HTMLBars.
One reason is that HTMLBars allow you to copy/paste plain HTML and it's gonna just work.
Another thing is that I feel HTMLBars are easier to gasp what the component does because it's a new DSL designed  for that
where as JSX feels like a dirty hack, but maybe that's my own assumption.

Also with current JSX if you had multiple elements in the component, in the same level, you would need to wrap them
(probably in a div), but that restriction will be shifted in the latest React as far as I know, which is great
because working with tables could be problematic.

Another thing I liked in Ember is that of having the tagName where you can inject
it from parent of just override your component's tag.

My feeling is that JSX will always follow its own path, where it needs to re-invent
everything on its own.
For instance, I clearly remember I had an issue replacing a string with some
(safe) html and to do that I had to dig into the React's implementtion details.

### React is great but it's just the view layer
Initially we figured out that React is too small to setup a whole front-end app.
So you need at least, a routing library and probably redux.
There is also MobX and redux-sega.

You are dependend in ohter libraries..

### react-router is a joke
Maeh, I don't know how should better I advice people to **not** use react-router and invest their time (and money?)
in something else, like [react-spoon](https://github.com/iyobo/react-spoon).

#### Major breaking changes in every version
We used react-router V4 and guess what V4 means: on every version there has been a complete rewrite
and there have been major breaking changes.
Isn't that bad enough ?
Ember's routing hasn't changed since I started. Except a small change when you declare the
routes in router.js, that probably would take you half an hour to update. + deprecation

To be honest Ember's router hasn't changed almost at all in the past 3 years, and that's why
you need an RFC-driven way of doing things and, possibly but not necesserily, a framework.

#### No named routes
What is worse, you cannot have named routes, as it is considered an [anti-pattern](https://github.com/ReactTraining/react-router/issues/1514#issuecomment-122011215).
Feeling like an idiot to explain why having named routes but here it goes:
1. I understand that most sites are in english but it happens that people are developing
sites in other languages as well, and URLs is not an exception here.
Do I really have to type in chinese everytime I need to redirect/link to a route ?
2. Isn't it better if you have one place where you can declare all your routes ?
With react-router, I felt that routes were flowing all over the place, and if
you jump to a new React project you need to open many files before you understand
what's going on.
To be honest, when jumping in an Ember project, the first thing you take a look,
is the `router.js` file, where all the routes are declared. By looking only this file
you can instantly understand roughly how the UI looks like, and from there you can
move on to the right files to do any necessary changes.

#### Link-to in Ember excels
In ember, using link-to you can

#### No documentation

#### Routes !== components
One thing that I disliked about React ecosystem is the approach that everything
can be a component.
I don't think this logic really works and I really like Ember's approach to that.
You really want Routes (you can name them page components) to be distinctly different than regular component.
A route should have different hooks than a component,
handling url params, loading/error states, instant redirects, authorization of the route
and so many other things.+ember documentation
Each page has different issues/requirements
How is the lifecycle, what comes first, what comes last in components when they fire up. We need some help....

A react componnent cannot play the role of a Route.

#### Difficulties on things that otherwise should be easy
How can I redirect after an action ?
Wel an [answer](https://github.com/ReactTraining/react-router/issues/1514#issuecomment-122011215)
in stackoverflow reminds me the benefits of a framework.



### react-redux is just a pattern, but a good one
React-redux really helped us to offload the components (once we added it most components would become
functional) and I really liked working with it.
The pattern was the same everytime:  initialize the state correctly for the thing that you want,
add an action, add a reducer if needed, and use the action in the component.

Some things though were not super clear to me, mostly due to my inexperience, but all in all
I was happy with it.
The only problem I could see though is that, once you use react-redux, you get locked
in that pattern.
Having for isntance, half your app using react-redux and half mobx would be super complex,
and I think that's another difference from having a framework.

A framework must provide you the most boring APIs so that you can exploit it the way
you need it, without being attached to a specific pattern.

React+Redux feels more restrictive than Ember is.
What I like about Ember/Angular/VueJS is that it's a platform. A boring platform is all you want with good primitives and infrastructure so that you can build upon it.

### Initializer infrastructure

### funcional and OO patterns are kind-of mixed together

add spoon library


### Ember-data is missing

## Dude, are you saying that Ember is perfect ?
**No**. Ember is far from perfect and it has its own problems.
In fact Ember had a lot of problems when I got into it.

But there are some things that I think make difference in Ember.

### performance is not critical, results is all what you want

### A framework to share same beliefs on code
At the end of the day everything boils down how much to your productivity and happiness.
For some people React suits them better.
I am not one of them, I am happier when working with a good, stable yet powerful framework for the reasons stated above.


### Great documentation
In the beginning there was a fame that documentation is really bad and outdated.
I have never seen a better documentation in any other project than Ember's and I really mean it.
Documentation is just magic.

Then Ember was supposed to be slow. With Glimmer VM, Ember is super fast.
Maybe slower than React,  but still fast enough.

### Stability, listens to its users
But I what  like mostly about Ember, is that users drive  the framework and not a cowboy who felt that he/she should
rewrite the routing part and break everyone's code.
Ember has been super stable after version 2.0, we upgraded to HTMLbars with no issues,  we upgraded to
Glimmer VM with 3 deprecation warning we keep upgrading Ember and its deprecation system is awesome.


But I fimly believe, that Ember or any other framework is a much better choice than React's ecosystem.


## Conclusion
Just to be clear: **React is great**.
I would be happy to use React again in a project that needs only react, like replacing Phoenix/Rails views with React,
or adding React to an existing project as a complementary.
Or maybe I would like to checkout Ember's glimmer, which is ember's equivalent to react, but that's mostly because I
have experience with Ember already and I know what they deliver is always listen to their users.
Plus, it has templates, and soon it will be an official part of Ember (meaning that you can interopt glimmer components in Ember).

But using React (and its ecosystem) for a full-page app ? **Hell no**.



### Who am I ?
First how am I: I am not a front-end developer per-se, I don't consider my self that at least.
I mostly am a backend engineer, worked mostly around APIs and related stuff.
But I have worked a lot with front-end and I actually enjoy it a lot, as long as, I don't do CSS/design stuff because I am totally useless.
However there are a lot of stuff you can do in the frond-end and it's not only design.
How you setup the Redux, how you send the requests, creating adapters/serializers in Ember, setting up the models correctly,
optimizing the API requests these stuff, although they belong in the front-end sphere are fascinating me.
