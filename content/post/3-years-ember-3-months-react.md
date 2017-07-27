+++
comments = true
image = ""
title = "3 years in Ember, 3 months in React"
author = ""
share = true
menu = ""
date = "2017-04-02"
draft = true

+++

In Kollegorna, where I work, we started using Ember long before React was published.
At that time there were very few options for full front-end frameworks: Angular, Backbone, Knockout and.. Ember.
After some initial research, Backbone and Knockout didn't seem full frameworks but more like libraries that helped you
to setup your application, Angular had the rumor of being Google-way (over-engineered and complex).
On the other hand Ember seemed the promising framework, being developed by well-known developers to someone familiar with
the Ruby community and having embraced Rails' convention over configuration seemed the right choice.
Btw, I don't have any recollection of picking Ember for its addon ecosystem, probably it had very few addons at that time.

I remember I was assigned to do a quick prototype demo for an incoming project.
Although documentation wasn't at its best it was quite good actually.
And I remember I had setup the main app pages in a couple of days, so that a designer could start working by adding
Lorem Ipsum text and inputs and have an actual prototype to the client.
Eventually we didn't use that codebase but a month later we got another project that required the app to work even offline
and Ember was the sole choice for that.
Since then I have worked on many Ember projects.

Fast forward, 3 years later we are still doing Ember when we feel it's the the right tool for the job.
The truth  is that working in Rails/Phoenix with complex forms that have a lot of dynamic elements it's not easy.
It's tough and a bit irritating and after having worked with Ember it doesn't feel natural to me as well (maybe that's where the irritating part comes from).
In Ember, such stuff is much more easier but then you have to deal with an API and if you don't have the right tools (1, 2, 3, 4)
then the time you gain by the Ember's ease of working with dynamic stuff, you lose it on setting up your API correctly.

But 3 months ago a client wanted us to implement the front-end on React.
Personally I was fine with Ember but super excited to work finally on React, something that I was looking forward a long time now.
React has become super popular among front-end tools.

### Who am I ?
First how am I: I am not a front-end developer per-se, I don't consider my self that at least.
I mostly am a backend engineer, worked mostly around APIs and related stuff.
But I have worked a lot with front-end and I actually enjoy it a lot, as long as, I don't do CSS/design stuff because I am totally useless.
However there are a lot of stuff you can do in the frond-end and it's not only design.
How you setup the Redux, how you send the requests, creating adapters/serializers in Ember, setting up the models correctly,
optimizing the API requests these stuff, although they belong in the front-end sphere are fascinating me.

### Working with React
I started studying the official React guides.
As I had already heard before many times, I instantly recognised that React is just a view component, an equivelent of Ember's components.
To be honest, I picked up React in almost a day and I pretty sure that it's not only because it's a simple view library but because
I had worked with Ember before so I already knew some patterns and ideas.
Ember has publicly admitted that it has "borrowed" many React elements and ideas, most importantly the DDAU pattern.

Even more excited we started working on the project. I joined the a week's codebase and the other developer told me that
it took them 3 days to setup webpack.
Ook, I had heard that webpack was complex but at least it was working when I joined :)

### Webpack is hard, but probably worth learning it

### No fixed structure on React

### JSX or HTMLBars, slightly prefer HTMLBars
Having worked with Ember's HTMLbars, JSX templates looked a bit weird to me.
But that was only the first month, then it felt natural.

But if you ask me HTMLBars or JSX I would say to you I am fine with both, but if I had a choice, I would choose HTMLBars.
One reason is that it allows you to just copy-paste plain HTML and it's gonna work.
Another thing is that I feel HTMLBars are easier to gasp what the component does because it's a new DSL designed  for that
where as JSX feels like a dirty hack.
Also with JSX you always need to wrap your code in a div or span because
Could cause problems in tables
I think Ember's way of having the tagName where you can inject it from parent of just override it is nice.


### React is great but it's just the view layer
Initially we figured out that React is too small to setup a whole front-end app.
So you need at least, a routing library and probably redux.
There is also MobX and redux-sega.

### react-router was far below my expectations


### funcional and OO patterns are kind-of mixed together

add spoon library

### performance is not critical

At the end of the day everything boils down how much to your productivity and happiness.
For some people React suits them better.
I am not one of them, I am happier when working with a good, stable yet powerful framework for the reasons stated above.

https://stackoverflow.com/questions/35706835/react-router-redirect-after-action-redux


replacing a string with some (safe) html is tough in React because it follows a different path with JSX

```
  get description() {
    const description = this.props.description;
    const geturl = new RegExp(
      "(^|[ \t\r\n])((ftp|http|https|gopher|mailto|news|nntp|telnet|wais|file|prospero|aim|webcal):(([A-Za-z0-9$_.+!*(),;/?:@&~=-])|%[A-Fa-f0-9]{2}){2,}(#([a-zA-Z0-9][a-zA-Z0-9$_.+!*(),;/?:@&~=%-]*))?([A-Za-z0-9$_+!*();/?:~-]))"
      ,"g"
    );
    const urls = description.match(geturl);

    if (urls) {
      return (
        <span>
          {description.split(urls[0])[0]}
          <a href={urls[0].replace(/\s/g, '')}>{urls[0].replace(/\s/g, '')}</a>
          {description.split(urls[0])[1]}
        </span>
      );
    }

    return description;
  }
```

??
