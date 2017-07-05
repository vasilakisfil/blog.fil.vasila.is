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
