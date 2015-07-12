We have a team of bright Column University professionals, and as a team, you are tasked 
with building a boat. You have boat building expertise and knowledge, you have done
it before, but this is a different kind of boat.

It is a disruptive technology and innovation in the boat business that will the business
an edge in the boat industry.

This boat is going to allow you ship products around the world faster than any other boat
boat from any other company. What are some of the considerations that you would want to take
into account in the building out of this boat?

Now let’s translate this into the world of software. Historically, this is the process which
has been practiced in building software. Build the prototype, take it out of the pond and onto
the lake, and from the lake, take it out onto the ocean.

The problem is that life on the pond, you cannot always anticipate what is happening on the
ocean.

So a developer has a base set of tools that he/she can build a great product in their environment,
but the environment does not match the production environment that the software is supposed to
operate. Or requirements change. Or the base software gets updated. Or the server software gets 
switched out. There’s any number of moving parts that can cause a fail.

You have the NYSE this past week as Exhibit A. Somebody is in hot water right now.

But this reality has been shifting enormously in the last 15 years or so, getting really, really close to building
on the ocean from the outset.

So, instead of a taking a year or two to roll out a new product, a la Microsoft Word
2000, Word 2002, Word 2007, Word 2010, Word 2013, now you are seeing incremental changes and new features
that get added every day or every week.

So all the steps are there, dev, testing, deployment, but they are rearranged and compacted significantly.

##Why does Docker matter? What problems does it answer?
The problem that Docker answers is that it brings together the moving parts of the development-to-production
process in a standardized, portable package. Dev is done on the ocean. QA is done on the ocean. Production is the
ocean, and the enviroment is consistently pegged to production.

So a lot of people think that Docker is a virtualization thing, which it is, but the real win happens in its packaging power,
which will we talk about in a bit more detail.

So the primary win- Consistent, portable, packaged, controlled environment to put your code in

##Overview of Containers
### Key Terms
There’s a couple of terms that you need to understand moving forward before diving into containers
specifically.

`Docker`  
Is a company which offers a Platform as a Service. They happen to be the open-source leaders of the containerization
    movement.

Docker != Container, they just have push the container standarization envelope

`Container`  
Is a filesystem wrapper. A package. Code, and stuff that tells Linux how execute the code. The raw materials and the instruction manual,
so that when you hit enter, Linux fires away and puts the thing together.

According to the [docs](https://www.docker.com/whatisdocker):
    “Docker containers wrap up a piece of software in a complete filesystem that contains everything it needs to run:
    code, runtime, system tools, system libraries – anything you can install on a server.”

`DevOps`
This is a buzz word that you hear flying around that nobody knows what it means, or that you use it one way to mean something
and I use it another way to mean something else.

Some say it is a philosophy or attitude, some say it is a process. Some say it is just a shiny new term for something that has been
around forever.

What people are getting at when they say DevOps-  
    software development and IT operations working together on the same team

The people who are making sure the your site is working when you get 10,000 calls per second are on the same team and
actively involved with the folks building a new feature which is going to be inserted into this fast-moving train.

So whether you like the term or are not interested in using it, the concept is important. The software needs to keep improving while not
stopping everything every time there is a change, and doing it through teamwork.
This is a key insight of the container movement, which I will come back to in a minute. But one more term.

`Version Control`  
Last non-Docker term that you will need to know for the test- version control. Version control is your Time Machine.
In Microsoft Word, when you save something, it overwrites whatever you have. This is not version control. 

With version control, every time you save, you get a new copy. 
So if you make a mistake, or you overwrite something accidentally, you don’t have to start from scratch.

Version control can save your life. The movie Toy Story 2 was 90% deleted by a stray recursive delete command. Their backups
had insufficient data, so they nearly lost years of man-hours. Fortunately, the Supervising Technical Director was working 
remotely as she had recently had a baby, and had a local copy. Otherwise, the movie was dead in the water.

### How it works
So we know that Docker is a platform that provides portable packages called containers,
aspects. We know that DevOps is a team of development folks and operational folks that make sure new features get
on-boarded seamlessly, and that Version Control makes multiple copies. Let’s take a look at the Docker container 
and how it works and pull it together.

It is helpful to compare it to a Virtual Machine. How is this different than VM? Let's look at these slides.

With a traditional VM, you are virtualizing hardware. You choose the number of cores that you want the VM to have,
the amount of memory that you allocate, etc. You dropping a separate computer inside your computer.

So this is amazing. Right now, the container technology is specific to Linux awesome sauce.
A container is not a new technology. Linux has this technology for over a decade.

So Linux as an operating system already has the ability to create isolated workspaces by using namespaces.

[Here](http://docs.docker.com/introduction/understanding-docker/) are some of these namespaces that Docker
implements from Linux [Source](http://docs.docker.com/introduction/understanding-docker/)-

    The pid namespace: Used for process isolation (PID: Process ID).
    The net namespace: Used for managing network interfaces (NET: Networking).
    The ipc namespace: Used for managing access to IPC resources (IPC: InterProcess Communication).
    The mnt namespace: Used for managing mount-points (MNT: Mount).
    The uts namespace: Used for isolating kernel and version identifiers. (UTS: Unix Timesharing System).

If you are already running Linux, you don't need another operating system to tell your hardware which processor to fire.
You start a container, and it shares the operating
system, so that all you need is the code and the instruction on how to run the code.
There's only one computer in there, which makes it make significantly more lightweight.

So instead of a traditional VM, you are using an instance of Linux. This cause some confusion for me, so you want
to note it. As of July 2015, Docker only runs on Linux! You can figure out Boot2Docker later once you get this.

If you are comparing it to a VM, you can spin up 10 containers with better performance on your machine than a couple VMs.

Here's where I want to circle back to the key insight as it relates to `DevOps` and teamwork. Ready for it?
Containerization recognizes that development and operations are not the same. You catch that?
Dev and ops need to work together, but they do have separate concerns, and this is a key insight.

When I am putting together a web app in Ruby on Rails, I can spin up an instance of a Postgres DB on my
local machine and get a working app-to-db back-and-forth. But it is not real. If even I populate it with some seed
data, it still is a sandbox environment.

Now, with a Docker container, I get an instance of my Rails app. Then I spin up a Docker instance of a database. Then
I spin up a Redis cache database, then I spin up a email service worker server, etc. Now I can simulate that the code
I just wrote is not going to work because it hits the cache once and the Postgres database 2x for this custom query. Drop
a fair number of seed records in there and you have a real performance issue.

Shoot some automated scripts at the thing and you are getting real feedback.

Without getting into the details of the tools, Ops can write some Chef server recipes to configure the server exactly like it is
in production. So the dev is not configuring it. The dev is just brought out to the ocean to build the ship.

Docker can take this and pull it into the local development or testing environment.

##Constraints
* Replicating a production environment on a laptop can lead to weird errors due to insufficient hardware.
* Security is always a concern for immature tech
    * From a security standpoint, “containers do not contain” [source](https://opensource.com/business/14/9/security-for-docker).
      Just like any software that you install on your computer, you need to trust the author.
    * Key strength also its weakness: you have easier access to the kernel. If somebody writes up malicious source code
    on the Docker image, you may be giving them the keys to the kingdom. Just the same as you download a virus
    from somewhere.
    * Docker recently released [Docker Trusted Registry](https://blog.docker.com/2015/06/docker-ready-for-production/)

## Opportunity for Business
And here is the grand finale- `version control`

The cloud was a massive game changer in the world of software, but a lot of companies probably will never move to the cloud. Now, with containerization, and
Docker version control specifically, you can bring small, incremental change to the enterprise.

You can configure an enterprise server to check version control every week, let's say. The way it works is that when you
pull down something from a remote version, it only updates what has been changed. It doesn't redo the whole software package,
just the files that have been modified.

You can use Docker to automate and update enterprise software on an on-premise machine as often as you want,
and it gives the team confidence that the update has passed the testing suite that has been configured to match the production environment exactly, 
because it is built from the same server configuration recipes. It takes the risk factor down,
because you are only changing one feature at a time.

So Docker- Consistent, portable, packaged, controlled environment to put your code in.
