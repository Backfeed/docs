Organizational and development practices
-----------------------------

# What's the problem

The basic problem is that:

    Software is not delivered on time 

# What causes it

* Bad communication. Every single person I talked to mentioned this.
* There is/was basically have no management
* No effective usage of best practices (I am thinking of devops/agile stuff)

Just to be clear, the problem is **not** that specs are changing. This is normal, and if the specs get better, it is even positive.

# Joel's Test Score

This is this 12 point scale of best practices for companies that develop software. It is the one you see in the job adverts on stackoverflow

http://www.joelonsoftware.com/articles/fog0000000043.html

I think we rate perhaps a 3. 

That is embarassing.

We want 12, and need at least 10.

# What we can do to resolve this.

Communication. We need some documentation (not too much, just enough): for the API (which is the point of contact between backend and frontend dev), a white paper or at least some written specs for the protocol and its various versions (which is the point of contact between protocol thinkers and developers). 

Agile/Devops: We can try some those Agile/Devops practices that are now not in place, and see what works. The goal is to have short development iterations, have a development process that is incremental (we don't break old stuff when adding new things).  

# Concrete steps

## Testing of the frontend

We want a test suite with functional tests for the frontend (tests of the type "if you click here, than you should get result X"). We start with identifying what test framework to use.

Automatic testing of all functionality is essential for garanteeing that our software will continue to work as intended, and are a great way of codifying knowledge about the intended functionality of the software.

## One-click deployment

Any changes in frontend or backend should be put online with the least possible effort. This makes it possible to show changes or prototypes immediately to "the client" (in this case, "the client" = Matan and Primavera), and wil make resolving bugs or adding functionality much less painful

## Write good API documentation for the service

The API documentation serves as a "contract" between frontend and backend developers - it is like a domain specific language that both can understand, and frontend-developers can be very precise about their wishes by expressing them as proposed changes to the API.

## Create a written specifiction of the protocol

This not only to explain and communicate our ideas to a larger public, but also as a way of communicating between those that theorize the protocol, and those that implement it. 

## Implement continuous integration

Tests should be run automatically (on a remote server) daily, or even on each push to the repositories.

## Use agile practices

We can try out things like planning games or daily standup meetings, and see which works best for us. More importantly, it would be good if the team members who don't know what this is about started googling for "devops" and "agile" to get an idea.

## Rewrite the protocol-service

See [Protocol Service Roadmap](protocol_roadmap.md) 

## Keep staging and production environments that are always up-to-date

[we have this now]

Create a (semi-public) staging instance for both frontend and backend that shows the latest working version of the software. This will give everybody involved a way of measuring progress, catching problems with UX or functionality in all stages of development, and in general serves as an object point of discussion. 

## Have more systematic bug tracking

Trello is fine for defining priorities and signalling problems in an informal way.  The github issue tracker has a more defined workflow, for assigning responsibilities, closing issues, and integration with github itself. We can consider using github issues for bugs and precise requests for software functionality.

## ?

Please add anything else that may be useful 
    