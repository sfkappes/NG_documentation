Many researchers on Nightingale will have access to their own node or
nodes, often called "interactive" nodes. Those specially-dedicated nodes
are for that group's use. If that's the case for you, then you will have
specific instructions on how to log into your own interactive node in
the Nightingale cluster, and you don't have to worry about the
instructions on this page. If instead of (or in addition to) access to
your own interactive node, you have access to the shared pool of
computational ("compute") nodes that are part of the Nightingale
cluster, this page tells you how to access them.

The computational cluster part of Nightingale is a shared pool of
individual computers within Nightingale called nodes that are available
for running your software. Because there are more than one compute node
on Nightingale, if your application can run on more than one computer at
a time, it can potentially run faster. Also, the batch system can run
your application as part of a "job", which is a block of instructions
that it will execute when there are compute nodes available to do the
work. That is, when you've submitted a job to be done, the instructions
in the job without you having to be logged into Nightingale at all. You
can queue up a bunch of jobs, each running a useful calculation, and
they will run sometime while you're away. This makes the cluster very
efficient at running software that can be broken down into chunks that
can each be done by a job. Jobs are typically configured to write their
results to a location on disk, and so you can retrieve the results and
read them when you log into Nightingale the next time.

This page is meant to teach you how to put together a job on
Nightingale, submit it to the Nightingale job system, monitor the job
before it runs, during its run, after it's finished, and then how to
retrieve the results.

Here is a list of the types of computational nodes available on
Nightingale and what hardware is available on them.

============= ============= ============== =====
resource name GPUs per node job time limit nodes
a100          (1) A100      7 days         5
a100x2        (2) A100                     1
a40           (1) A40                      3
cpu           (none)                       16
============= ============= ============== =====

Nightingale's Job Control System: Slurm
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Nightingale uses the `Slurm job control
software <https://slurm.schedmd.com/documentation.html>`__ to run jobs.
Slurm was developed at California-based DoE labs, and is now perhaps the
most-used job control system on HPC systems in the world. If you want to
do something that this page doesn't cover with your jobs, feel free to
submit a ticket, but you could also google "how X with slurm" and that
should get you close, as long as you keep in mind the configuration of
the nodes on Nightingale.

Managing your jobs with Slurm

| 
