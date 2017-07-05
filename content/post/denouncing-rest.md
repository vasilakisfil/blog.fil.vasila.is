+++
comments = true
image = ""
title = "Denouncing REST"
author = ""
share = true
menu = ""
date = "2017-07-01"
draft = true
+++


There are 3 types of denouncers of REST model.

1. The ones who understand what REST is and feel that due to its complexity, they prefer loosing some features and deliver something
simpler, yet easier to implement and test and deliver a RESTy approach.
2. The ones who understand what REST brings on the table but given that they control the client as well,
why should they bother with the whole HATEOAS thing?
3. The ones who don't understand REST and just want a plain JSON because it's simple enough.

I have noticed that few developers belong to (1), meaning very few really understand what REST bring into the table.
But also notice how everything revolves around **simplicity**.

Building high performant web services is hard, but to justify the deprecation of Roy's REST model is multiple times harder.
Obviously the reason is that he had done pretty good damn job (almost perfect if you take into account when it was published).



### 9.1. Collections, Resources, endpoints, actions and methods
There is a small confusion of different terms used around API literature.
We would like to give a small description and definition of each one.

#### Collection
A collection is a set, an array, of resources.
The resources should be of the same type but rarely a collection could also contain
resources of different types, or polymorphic resources.

#### Resource
A resource is an entity that exposes a set of different actions that can be performed on it.
Typical actions are a subset of CRUD but it can go way beyond that and depends on the API designer decisions.

#### Endpoints
An endpoint is the interface of a specific action in a resource.
The term endpoint is usually used when referring to a non-REST URL that doesn't belong to any resource.

#### Actions
An action uses an HTTP method and along with the action's url forms an endpoint.
An action is always linked to a resource, meaning that the action will be applied to a resource.

#### Method
In the RPC world, a method is a remote method called by another remote object.
In HTTP and related protocols, when we talk about a method, we mean the actual protocol method used, for instance `REGISTER` in SIP,
or `DELETE` in HTTP.


##### 9.1.3.1. Capabilities
The term capabilities is used to describe what is possible an API to do using metadata.
This term us mostly used by


Roy's model is weird: it was rarely fully employed to have 100% evolvability and when it was all it's drawbacks appeared: complexity and performance issues.


Some people call such APIs AI-driven APIs, or autonomous APIs but it's all about **evolvability**.
If you can design an architecture style that is **evolvable** yest simple enough and applies/does not break
to our current Internet's protocols (like HTTP) then none can accuse you of using it.
RPC-based, hypermedia-based, whatever-driven, if it's evolvable and convinces us of using it (like it's very simple)
then none can accuse you about your API architecture.
Apparently people want want (from our experience with REST) first simplicity and then evolvability.
When we say evolvability, we mean without touching/breaking the clients.
At the moment we have only REST though which is evolvable but not simple. IT's complex.


We see that people fail to understand the full extend of Roy's initial `REST` model and what is happening is that
some elements of that REST are applied, some other not and eventually we have a model that has the downsides of both worlds.


No you don't need GraphQL



In this Manifesto we will try to kill Roy's model.
It gave us great insights but let's be pragmatic: it will never work out.

We need to **be brave enough and move on**: Roy's HATEOAS-based REST model can be declared as deprecated.

Introspected REST is an alternative backwards compatible API. No breaking changes are needed.

##############################################################
If you want to build the next Introspected-REST spec, you can follow the following reasoning.
Note that this reasoning is message-agnostic, meaning that we use here JSON just because we know it better
but your spec could use anything, yaml, xml etc.

* Start with some SANE defaults and the axion: The simpler your API (and the lesser it deviates from defaults), the simpler the introspection-meta-data should be
* Reach a concencus on a Introspection spec using already defined specs like JSON-Schemas.
* Reach a concencus on a querying language over url (filter + aggregation + pagination)
* Reach a concencus on an URL-API for attribute/association inclusion
* Reach a concencus on linking
* Reach a concencus on denoting linked/semantic data
* Reach a concencus on document structure (root element, meta attributes which should appear in the simple response as well etc)
Each of those could be a separate Media Type

So we keep 80% of the REST constraints and while we understand the benefits of other 20% we switch it with an on-demand alternative that makes the final thing
more flexible and powerful while keeping the final data simple.

Introspected REST model is flexible enough to cover all those user cases.
It's not a model that is black or white: your API is either Introspected-REST-compliant or it isn't, like REST.

It should be noted this model is not something we conceived in a lab. Some [people]()
have already tried to implement something similar, probably without really knowing
what they were doing.

You see, the shadow of Roy Fielding is above any API developer:
we are afraid to deprecate Roy's REST model and as a result what we are doing is that
we take some elements of Roy's model, apply them, and name our API or spec as RESTSful.
Eventually however, the final result is even worse. It doesn't have Roy's key elements for
a Markov-chain-like client (we still have offline contracts) yet we have added complexity
to our API for little result.


Probably Roy won't like that. He will either:
* declare that Introspected REST is a stupid manifesto that has nothing to do with his REST or
* he will declare the Introspected REST is just yet another REST as he defined it and we never
read his dissertation to actually see that we are defining yet another REST style.

In either case, given that very few has really implemented a Roy-compliant REST API means
that Roy himself failed to explain his model correctly.

Are we sliding a lot from Roy's initial model? No, we modernize it a little bit.


#### 5.3. An alternative architectural style maybe?
Most of those Media Types specifications would not be needed if the APIs were built
with introspection in mind.

Imagine that we have a Media Type that allows us to describe new media types, called `generic_media_type`.
Then the clients would only need to understand and parse this `generic_media_type` and derive the other
Media Types.
Of course, this scenario is more difficult than it sounds and the goal of this _manifesto_ is not
to provide a generic Media Type.
Nevertheless, API introspection, as we will see, can provide us with information on API's
capabilities along with hypermedia in a much flexible and cleaner way, _without having data and hypermedia (representation metadata) tangled together in 
the representation_.
