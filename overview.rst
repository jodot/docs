Overview
========

``Jodot is your personal/team duty runner. Delegate software related duties to
Jodot!``

What is Jodot?
--------------

Jodot is a long-running process that executes duties that are delegated to it.
The current version of Jodot supports scheduled duties. It should support event
based duties as well as one-off duties.

Jodot is suitable for all kinds of duties/tasks/workflows that you may wish to
automate. Jodot duties are essentially npm packages or Node.js modules. The idea
is to tap onto the massive npm repository of functions and modules to easily 
assemble automation scripts (duties).

Run Jodot within your environment of choice. Since Jodot is open source and you
maintain complete control of how it is ran, duties delegated to it can be much
more personal/confidential than automation on hosted solutions.

Duty ideas
----------
Some ideas for duties:

- Turn e-mails where subject is prefixed with TODO into GitHub issues
- Send a Twitter DM whenever a website loads slower than a preset time
- Approve all leaves submitted by default as long as there are still days left for the year
- Gather additional info for a credit application from various sources before e-mailing complete set of information
- Send a message on next bus arrival for two nearest bus stops whenever I leave the house

Essentially, npm and Node.js is your limit! Duties can be for individuals or entire organisations.

Features
--------

Well, at this point. You may think, I could do this with Node.js, npm and cron or some other services? Well, you could, but in any case, Jodot provides you with an easy framework to structure your automation duties. It:

- Automatically installs any duty packages for you
- Provides a single file (duties.hjson) that organizes duties
- Handles running the duties as child processes
- Serves as the meeting point for all kinds of duty triggers (WIP)
- Easily share useful duties with others and use shared duties (hopefully)
