 BACKFEED PROTOCOL SERVICE
--------------------------

## What are we talking about

The Backfeed protocol service implements the Backfeed protocol and makes it available to the world.

It is the most central *material* product that Backfeed produces, around which the whole Backfeed eco-system revolves.

## What we want

In the short term Backfeed needs:

1. an elegant, sane, and documented REST API for the protocol service
1. an implementation of the protocol that is isolated from the deployment environment, and can be understood, and preferably tweaked and played with directly, by non-programmers (such as Elad)
1. a well-tested and beautiful code base that is a pleasure to work with, that we can be proud to have on github 
1. Devops that works (very short development cycles, deploying fixes and features should be painless)

In the medium/long term, we may need:

1. A structured way of running a large number of large (1000s of users, 100.000s of transactions) simulations of different usages of the protocol
1. A API service that can handle large amounts of traffic
1. Put our tokens, and eventually the protocol, on the blockchain


## What's the problem?

Development on the protocol service progresses very very slowly.

One reason is the present codebase is very difficult to maintain and extend. 

* The **quality of the code**: it is unstructured, largely untested, uses almost no abstraction.
* Due to usage of **AWS services** (Dynamodb, Lambda functions) and Serverless (which is in beta and buggy) the actual development process is frustrated by problems with operations (issues having to do with deploying the framework as opposed do writing the code)
* Backfeed does not want its central product to be essentially dependent on a private company such as Amazon


##  How we solve it

We will migrate the code to a new stack, and rewrite the core functions.

We will use established, "riskless", software stack, with a large community, and mature libraries.

### Software Stack

Our software stack can be divided three tiers

1. An HTTP/REST layer that serves the HTTP requests, and in which the API is defined
2. A logic layer where the data structures and the protocol is defined
3. A persistence layer where data is stored

We have now:

1. AWS API
2. Amazon lambda functions in nodejs
3. Dynamodb

The main choices we need to make is:

* which language will the principal language for development
* which database we will use for persistence

For the language part, we can use I'd propose Python. It is a natural choice with its easy to read syntax (which is important for the protocol implementation), and great statistics and math libraries, which we may need. It is also used in the scientific community, and therefore may make it easier to attract the type of programmers that we may need.

Regarding the database, the basic choice is between a relational database or a key-value or document-oriented database. Sql or Nosql.
Our data has a classical relational structure, which naturally fits the relational database model, and is difficult to work around in a Nosql db, so I would argue for a relational database. 

Specifically, I'd propose this:

1. Apache/Nginx and some server and framework such as Pyramid
2. Logic is written in Python
3. Postgresql


## Risks

1. Progress on the protocol stops while the migration is in progress
1. Because the present code is not completely tested, knowledge may be lost during the rewriting (i.e. we may forget to migrate things already implemented, or have to reinvent things twice) 

### Risk Mitigation

1. Given that we actually have no system in production that uses the service, and (as far as I know) no short term deadlines, this will not be a problem. Development on the frontend can continue against the existing service.
2. 
That way, development does not need to stop completely, and if there are doubts about the meaning of certain parts of the code, they can help.

## Estimated Time Line/Road map

see [dmag_roadmap](dmag_roadmap.md)



