# Welcome

You have landed at Victory CTO's Operatations Engineer practical evaluation. 

From here on, we are going to assume that you are either a canidate for an 
Operations position at one of Victory CTO's clients, or have applied to be 
part of the Victory Staff.

In either case, have a good time.  

# Overview

Your mission is to take a simple production web application and modify it to
scale on a laptop, then deploy it to the cloud provider of your choice.

You will be evaluated on your ability to communicate the work to be done, track
that work and communicate the work that is left to be done.

You are expected to spend between 4 and 6 hours on the project. You are welcome 
to spend more if you like. 


# Infrastructure

## Beginning

* Ubunutu 16.04
* Python 3
* Redis

## Target

Choose either the machine based topology or the container based topology as
directed during your interview.

Machine Based

* Ubuntu 16.04
* Haproxy
* Python 3
* Redis

Container Based

* CoreOS
* Docker
* Python 3
* Haproxy
* Redis

In addition to the above, set up some sort of build and artifact system. 
For example TravisCI and S3 to build an artifact and store it for deployement.

Deploy the production topology to the cloud provider of your choice.

# Basic Directions

1. Fork this project. Pull requests and pushes to this project will
_not_ be accepted unless they are specifically targeted at improving the
evaluation (not answering it).

2. Document the work you intend to do withing 4 to 6 hours of efforts over the 
course of a week. It is recommended you do this in the Issues section of your
Github project. (or similar)

3. Perform the work you have laid out for yourself and document the results
in your work tracking system.

4. Extra Credit for creating any documentation in the wiki that would help
the next person to encounter the system who has operations responsibilities. 

Important:

If a technology is not listed in the core infrastructure lists above you can
choose anything you like. If you change a core technology, then simply be 
ready to justify your change.

You will likely _not_ complete this. So keep in mind that your written 
communication about what comes next is critical to the evaluation. 

We realize you may have a current job and that forking this repo publically
could cause you trouble. Feel free to clone it and provide a tarball for 
us to evaluate if you feel the need to maintain your privacy.


## Tasks

You have been given a Vagrant development environment that is based on a very
simple python application that counts the number of times you have been seen.

The below list of tasks is not in order. Your prioritization of them will 
be a topic of discussion.  

Some tasks are relevant to one topology but not the other (vm vs. container).

### In the Development Environment

Assume the application is functionally complete and perform the following 
tasks:

* Implement HAproxy as a reverse proxy for the application in development
* Implement a self signed TLS cert and offload SSL at HAProxy
* Containerize the application and swap Ubuntu for CoreOS
* Secure the host:
  * Add Fail2ban 
  * Implement 2 to 4 firewall rules with the firewall of your choice
* Set up monitoring for each service in the stack
* Set up log aggregation for each service in the stack
* Set up a build system and artifact store

You are welcome to create your own task that you feel is more important than
any of these. Be ready to justify the addition and prioritization.

### In the Cloud Environment

Create a set of tickets to deploy your stack to a target environment in your 
favorite cloud provider. At a minimum there should be two diagrams and enough
detail for another person to implement without having 24/7 access to you.

* Diagram of target topology
* Diagram of deployment process
* Tickets for the configuration and deployment of each diagramed system.

If you need a diagramming tool, check out draw.io.

# Evaluation Criteria

It is impossible to capture the myriad breadth and depth of necessary 
experience required by today's operations engineers. The corollary to this 
fact is that as an Ops Engineer you cannot possibly know everything you need
to for any given position.

Please take note, that many places say, "Explain how to do this and document."
We prize the ability to communicate the work and the need driving it. Without
that ability, non-functional requirements languish in favor of application 
features. 

This evaluation is constructed to measure your ability to function a world of
constant learning and multi-mode communication. 

BBe sure to keep good notes during this time and ask good questions. 

You will have a week to work on the problems set for you here. After that time
another 30 to 90 minute time block will be set up to review the outcome of 
your work, your approach and your decision making.







# Making Improvements



