---
layout: post
date: 2017-03-18 12:01:55 -0400
title: what it takes to make open source software
---

i was glad to see
[a blog post](https://nolanlawson.com/2017/03/05/what-it-feels-like-to-be-an-open-source-maintainer/)
recently, detailing one of the unglamorous aspects of being an open source
developer: the seemingly never-ending stream of bug reports, help requests, and
other (mostly negative) messages coming from the community trying to use your
software.  it was written from the perspective of someone doing bug triage, and
i was particularly happy to see that role highlighted, because it's absolutely
essential to the health of a project to pay attention to issues that get filed,
both because it's a good way of identifying problems with your code, testing,
and documentation, but also because it's an opportunity to encourage your users
(and maybe occasionally recruit them to help with the project).

the one thing about that blog post that is very different from my experience is
that it's written from the perpective of a lone-wolf developer maintaining a
project personally, presumably in their spare time.  in contrast, all the
projects i work on have several developers working on them as part of their
full-time jobs, and a broader range of people contributing in a lot of different
roles, again, mostly as a part of their full-time jobs, and in some cases as
their exclusive job.  i want to talk about this broader range of roles, because
i think they aren't well-understood (or valued), and the lone-wolf model
obscures them.

**code reviewer** is the first new role that i noticed when i started working on
open source projects.  instead of just pushing my changes when i thought they
were good enough, i open pull requests, and another developer (or sometimes 
someone in a "tech lead" role) will review them, ask for changes, make comments,
ask questions, and merge them when they are happy.  sometimes that's a very
cursory check (there are a bunch of automated tools that run tests, check for
known code quality problems, etc. to make this task easier), and sometimes it's
a very exacting process, which can get tied up in architectural concerns, 
release management, and drag on for months.

a **team leader** helps manage the work a group of people are doing on a
project.  this involves doing bug triage, writing and organizing workable
tickets (making sure they're in scope, clearly-written, not blocked by external
requirements, etc.), leading team meetings, making sure everyone on the team has
work to do and isn't waiting for someone else before they can work.  depending
on the team, this might be a "tech lead" position, whose full-time job is being
a team-leader for a project.  it might be a technical manager who supervises
developers.  or it might be a volunteer, stepping in to that role for a week or
two.  if you have a small group of developers working on an established project,
you might share this role among the developers, or have one developer take this
role in addition to being a developer.  but even in that case, projects will
start to drift after a few weeks and somebody has to do the most important job
of a team leader: coordinating with stakeholders to make sure the software is
actually useful to someone.

**testers** make sure that the software does what its supposed to do.  this can
range from very a informal process where someone sets up the software and tries
to use it, to a very formal process with a dedicated environment and a
pre-written script of tasks to complete.  testers then submit bug reports for
things that don't work, or maybe check off items from a todo list to indicate
what works and what doesn't.  in many cases, testers are the only ones who have
real data, production-scale hardware, or end-users to work with.

**documenters** write documentation to help people use the software effectively.
this can range from a README file in the source code to help people build and
run the software, to exhaustive catalags of commands or options, to guides that
walk through how to perform a particular task, to general information about the
project, to screencasts demonstrating the current state of the software.  there
are a lot of different audiences for documentation, and they need very different
kinds of information, and have very different concerns.  a system administrator
may want to know about installation and configuration options.  an IT manager
may want to know how what other software it works with.  a developer may want
to know where the source code is and what the process for contributing is.  an
administrator may want to know about the health of the project and how it fits
into a broader landscape.  writing for these different audiences is challenging,
and keeping the documentation current (particulary for a fast-moving project)
is a lot of work.

**stakeholders** articulate what the software needs to do, what's a hard
requirement.  what's nice to have but not essential.  what needs to be done
first, and what can wait for later.  they are sometimes the end users themselves
(which is ideal), but more often they are a proxy for them, such as a project
manager.  they are often involved at the beginning of a project (when initial
requirements gathering takes place), and then periodically when milestones are
reached (to provide feedback and refine the requirements).

and there are a lot of other roles beyond these, depending on the software.
most of the projects i work on involve metadata, so **metadata analysts** who
know the ins-and-outs of metadata standards and can find good sample data to
work with are invaluable.  for anything with a web front-end (which is almost
everything i work on), a **web designer** who knows about responsive design and
accessibility is key.  as software approaches production use, a **devops
engineer** can make deployment much easier, and repeatable.

of course, these roles aren't exclusive.  in a big project, you might have one
or more people doing each of these.  but it's also common for one person to
have many roles between projects, or on the same project.  and in the lone-wolf
scenario, one person may be filling every role.  i think being mindful about
the different work that needs to be done is more important than having a
dedicated person for each role.  in my experience, it's better to let people
contribute in different ways and not limit them to their narrowly-defined job
responsibilities.

but having separate people in some or all of these roles has a lot of
advantages:

* perspective is the most important.  either from having a different role all
  the time, or from just having a little distance in this specific instance,
  a different perspective makes a lot of roles more effective.  for example,
  it's easier to find problems in someone else's code, because you have
  different assumptions, do things in different order, etc.  for documentation,
  where empathy with different types of users is so important, having 
  different perspectives is particularly important.

* different skills — more than once i've gone into a discussion with a metadata
  analyst thinking i knew something well, only to realize my understanding was
  very limited (protip for arrogant developers: people with advanced degrees
  and/or years of experience in a field know more than you do — listen to them).
  many of the roles have to be filled one way or the other, but it is a joy to
  work with people who are skilled at the task, whether it's a professional
  technical writer, or a dedicated coordinator representing stakeholders, or a
  project manager who runs a meeting well and always knows the way forward when
  you hit a roadblock.

* resources — testing with real data on real hardware is critical, particularly
  for things like testing performance and scalability.  some stakeholders can
  commit the staff they manage to work on a project, and this can unsurprisingly
  hinge on whether they expect the software to meet their needs.  everyone has
  a network of people they can ask questions of, try to persuade to help, etc.

i touched on this in my [last post](/2017/03/10/not-a-developer), but i think
it's important say that a lot of these roles are dismissed or devalued.  they
are usually seen as secondary to the developer role.  in particular, some of
these roles are usually filled by women, who don't get the same respect,
support, and compensation as the (mostly male) developers do.

but i've worked on projects with tons of stakeholder input, and we made better
software than the projects where we've had to guess what users really needed.
we also wasted less effort on functionality no one really wanted.

i've worked on projects where documentation was an afterthought, or
non-existent, and it was harder for people to use our software than when we had
dedicated documenters working with our team.

i've worked on projects with dedicated testers, and we caught and fixed 
showstopper bugs instead of shipping them.

if you care about making quality software — ultimately, if you care about making
something that actually helps users — you should care about all of these roles.
you should respect, celebrate, and compensate these roles like the essential
contributions they are.
