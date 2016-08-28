Duties
======

What is a duty?
---------------

It is simply a function that Jodot will perform continuously or periodically based
on a preset schedule (cron format).

A Jodot duty is thus either one that is repetitive or continuous.

One time tasks may not be suitable as Jodot duties (well, it can just be a script
on its own).

Local duties
------------

You can compose duties on your local environment too (not all duties have to be
shared). These can be private modules that you write for your own purposes.
Similarly, there's only one requirement when writing a local duty: implement the
process.on() function to encapsulate what the duty does.

To use your local duty, run jodot where your local duty reside and specify the
name of the duty module along with the localInstall flag set to true within
duties.hjson

For example:

1. You compose a duty module called my_local_duty

2. Run jodot where the my_local_duty source directory reside

3. Add duty with desired schedule to duties.hjson on the directory where jodot
   runs:

   [
     # Sample local duty
     {
       schedule: 1 * * * * *
       package: my_local_duty
       localInstall: true
     }
   ]

Crashing duty
-------------

If a duty child process had crashed resulting in it not being available for a
scheduled duty, Jodot will report it as well.

.. _updating_duty_packages:

Updating duty packages
----------------------

Jodot will update all duties with the latest available package whenever it is
restarted. If it is not restarted, Jodot will not update any duty with the
latest duty package that is available automatically. This is a defensive design.
Imagine the scenario where a duty package that had been tested to perform
properly being automatically updated with a later version that is malicious.
This is technically possible, although all npm packages are open source and can
be reviewed by anyone before using it.

If you're comfortable with having your duty packages update automatically (either
because you're using a secure duty package source or are running scenarios
that are OK with automatic public updates), you can use the jodot-update to
check and update your duties periodically.

In any case, if you have a need for enhanced assurance with your duty packages,
Jodot does support this technically via duty sources (see
:ref:`sources_of_duties`)

.. _sources_of_duties:

Sources of duties
-----------------

Writing your own duties
-----------------------

2. npm init

MUST have package.json
