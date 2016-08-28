Using Jodot
=============

Use a process control system
-----------------------------

Use a process control system like Supervisor to manage the livelihood of the
Jodot process. The Jodot process should be running at all times.

Jodot logs failing duties (crashed, exited or somehow failed to execute) to
stdout. It is important that you monitor where stdout is directed to on the
basis of how critical your Jodot duties are.

There are Jodot duties available to help with monitoring generally.
jodot-monitor is a duty that tails a specified log and send an alert to a
designated e-mail whenever a specified text string is detected. jodot-summary
sends a summary of all duties that a jodot instance is currently running via
e-mail.

Running multiple instances of Jodot
-----------------------------------

Jodot is fundamentally a process, you can thus run as many instances of Jodot on
a single environment or multiple environements.

There are several scenarios where multiple instances will be better. For
example, you may want to separate your Jodot processes by functional categories
and run Jodot on an environment that closer serves the category (system
administration duties on a system administration environment, financial duties
on the environment for financial systems, etc.).

Organizations and enterprises may want to separate Jodot processes for different
functional units. Each Jodot process can be isolated from one another and be
accessible by different people. Different Jodot processes may also need
different :ref:`security` setups, different duty package update settings (see :ref:`updating_duty_packages`) and duty
sources (see :ref:`sources_of_duties`).

Of course, you can also run all duties with one Jodot process. This is suitable
for casual, personal use.
