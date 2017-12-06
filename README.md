# Welcome

You have landed at Victory CTO's Operatations Engineer practical evaluation. 

From here on, we are going to assume that you are either a canidate for an 
Operations position at one of Victory CTO's clients, or have applied to be 
part of the Victory Staff.

In either case, have a good time.  

# Goal of the Evaluation

This evaluation is constructed to measure 
your ability to function a world of constant learning and multi-mode 
communication. 

You are being evaluated on the following criteria:

* ability to take a working system and harden it for a production environment
* ability to communicate about work in an effective, written fashion
* ability to prioritize the work to be done and provide sound reasoning for 
  the choices made
* ability to work with new/unfamiliar technologies and paradigms to quickly
  get effective results 

You are not being evaluated on 

* your deep knowledge of a particular technology.
* your ability to do everything in 4 to 6 hours without writing anything down
* your ability to guess our opinions and adhere to them.

On the last: You _will_ differ from us in your priorities and methodology just
as you would in a real job. That is expected, so relax and do _your_ best. 

# Privacy

Ideally you will fork this repository to your own Github account and use the 
Issues and Wiki functions. However, we realize this can be problematic for
candidates who are currently employed. 

Directions are written for the ideal. If you need to do something else, please
feel free. We have, over the years, accepted anything from a tarball to root
access to a cloud account. 

# Get Started!

Your mission is to take a simple web application and modify it to
scale on a laptop. If you like you could even deploy it to the cloud 
provider of your choice.

You have approximately one week, as agreed, during the introduction meeting to  
work on the problems set for you here. After that time another 
30 to 90 minute time block will be set up to review the outcome of your work, 
your approach and your decision making.

## Functioning Baseline

This evaluation starts on your personal workstation. You will need to be 
running a Vagrant or Docker set up locally. 

* You can follow directions for [installing Vagrant here](https://victorycto.com/post/vagrant-101-power-of-disposability).
* You can follow directions for [installing Docker here](https://docs.docker.com/docker-for-mac/install/).

1. Fork this repo
2. Type `vagrant up` in the root directory.
3. Open a browser and got to ["192.168.33.10"](http://192.168.33.10) 
4. Refresh the browser.

You are seeing Nginx reverse proxy calls to a simply Python 3 Flask application. 
That application keeps track of the number of times it sees you in a Redis 
key-value store. 

**It is critical that the application continue to function as seen in the 
baseline!** 

## Target

Choose either the machine based topology or the container based topology as
directed during your interview.

From a compliance standpoint, assume that the company currently does _not_ have
any compliance obligations, but will be assuming some (your choice) within
a year of your hire. 

From a budget perspective, don't allow funds to limit your thinking, 
simply be ready to justify the spend. 

### Machine Based

* Ubuntu 16.04
* Nginx/Haproxy
* Python 3
* Redis

The minimum expected application topology is a load balancer, two 
"Flask Servers" load balanced and a single Redis instance.  

The minimum deployment pipeline is something to "build" the code into some
sort of minimal artifact and store that somewhere. Ideally a trigger will
deploy the application when a new artifact arrives.

Do not limit your thinking to machines.  For example, if you are using AWS, 
you can use ELBs and Elastic Cache. Just be ready to justify your thinking 
and provide context. 

### Container Based

* CoreOS for host machines
* Docker
* Python 3
* Nginx/Haproxy
* Redis

The minimum expected application toplogy is a load balancer, two 
"Flask Containers" load balanced and a single Redis instance. 

The minimum deployment pipeline es something to package the application into 
a container and register it (Docker Registry, Quay or other). Ideally a 
deployment will be triggered when a new artifact arrives. 

## Tasks

The below list of tasks is not in order. Your prioritization of them will 
be a topic of discussion.  

Some tasks are relevant to one topology but not the other (vm vs. container).

Assume the application is functionally complete and perform the following 
tasks:

* Implement HAproxy or Nginx as a reverse proxy for the application 
* Implement a self signed TLS cert and offload SSL at HAProxy/Nginx
* Containerize the application and swap Ubuntu for CoreOS
* Secure the host:
  * Add Fail2ban 
  * Implement 2 to 4 firewall rules with the firewall of your choice
  * Manage users with SSH access to the host
* Set up monitoring for each service in the stack
* Set up log aggregation for each service in the stack
* Set up a build system and artifact store

You are encouraged to create your own task that you feel are more important than
any of these. Be ready to justify the addition and prioritization.

Do not be limited in your thinking. For example, with monitoring, get a trial
account with a service like Data Dog or New Relic and implement that if you 
feel it is the right way to go.

# Deliverables

Deliverables come it two flavors. Those that are tangible and those that will
be demonstrated and discussed. 

Tangible deliverables:

* A public URL in your favorite cloud provider to hit and see the application 
  function as expected.
* Access to your issue store and knowledge base to see what you did.
* A diagram of target topology 

Discussion Points: 

* A demonstration of how to change the application code and deploy to your 
  cloud environment
* A guided review of the code created to accomplish each task. 
* A discussion of the remaining identified tasks. 

If you need a diagramming tool, check out [draw.io](https://www.draw.io).

# Making Improvements to the Evaluation

If you think there is something that needs to be improved in the evaluation itself, 
please do the following

* Open a ticket in Issues
* Get a green light that the work you will do will be accepted
* Fork the repo and make the change.
* Submit the PR.

If that is not possible for the purposes of privacy, 
please fork, branch and tarball with a clear commit message. 

We will merge it if we believe it to be an improvment.
