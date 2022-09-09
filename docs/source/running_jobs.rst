Running and Managing Jobs
===================================

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
work. That is, when you've submitted a job to be done, it will execute
the instructions in the job without you having to be logged into
Nightingale at all. You can queue up a bunch of jobs, each running a
useful calculation, and they will run sometime while you're away. This
makes the cluster very efficient at running software that can be broken
down into chunks that can each be done by a job. Jobs are typically
configured to write their results to a location on disk, and so you can
retrieve the results and read them when you log into Nightingale the
next time.

This page is meant to teach you how to put together a job on
Nightingale, submit it to the Nightingale job system, monitor the job
before it runs, during its run, after it's finished, and then how to
retrieve the results. Please see the example scripts page for scripts
that work on Nightingale that you can use and build from

Here is a list of the types of computational nodes available on
Nightingale and what hardware is available on them.

============= ============= ============== =====
resource name GPUs per node job time limit nodes
a100          (1) A100      7 days         5
a100x2        (2) A100                     1
a40           (1) A40                      3
cpu           (none)                       16
============= ============= ============== =====

This page and the example scripts page assume that you have a working
knowledge of how to write and test a script, and you know at least
generally how jobs work. If you don't, but you want to run software on
compute nodes, the safest place to start is probably interactive jobs
(below). Please send us a ticket if you need help with this.

Nightingale's Job Control System: Slurm
---------------------------------------

Nightingale uses the `Slurm job control
software <https://slurm.schedmd.com/documentation.html>`__ to run jobs.
Slurm was developed at California-based DoE labs, and is now perhaps the
most-used job control system on HPC systems in the world. If you want to
do something that this page doesn't cover with your jobs, feel free to
submit a ticket, but you could also google "how X with slurm" and that
should get you close, as long as you keep in mind the configuration of
the nodes on Nightingale.

Managing your jobs with Slurm
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Generally you'll use these commands to run **batch** jobs. Each batch
job is controlled by a script that you hand off and the compute nodes
run when there's enough nodes available to run. That is, the job will
generally run **asynchronously** , so you can log back in and see the
output when it's finished.

sbatch <my_job_script>
^^^^^^^^^^^^^^^^^^^^^^

submits that script to the job system. It will handle the job according
to the #SBATCH directives in the top of the script (see example
scripts).

squeue
^^^^^^

This command lists the jobs that are currently running on the system. If
there are lots of jobs, you can run

::

   squeue --user=${USER}
   
to only see **your** jobs.

scancel <jobid>
^^^^^^^^^^^^^^^

This kills a job that is in progress and ends it immediately, without
waiting for any applications to finish.

Interactive Jobs
~~~~~~~~~~~~~~~~

Unlike batch jobs above, you can also ask the scheduler for a compute
node **now** , and to log you onto it. To launch an interactive job, run
the following command:

::

   srun -A usrsvc --pty bash 

(You'll need change "usrsvc" in that command to the name of your
allocation account.)

Warning: be sure to end the interactive job as soon as you're done. If
you leave the job running, even if you're not running any processes, you
allocation account is being charged for the time.

| 
