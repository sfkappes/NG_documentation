=====================
The Batch System
=====================

User access to the compute nodes for running jobs is available via a batch job. Nightingale uses the Slurm Workload Manager for running batch jobs. See the sbatch section Batch Commands for details on batch job submission.
Please be aware that the interactive (login/head) nodes are a shared resource for all users of the system and their use should be limited to editing, compiling and building your programs, and for short non-intensive runs.
An interactive batch job provides a way to get interactive access to a compute node via a batch job. See the srun or salloc section for information on how to run an interactive job on the compute nodes. Also, a very short time test queue provides quick turnaround time for debugging purposes.

Nightingale’s batch compute system is a shared pool of compute nodes where users run their jobs. A job is a set of instructions which includes all the resources needed to run an application. These instructions include the executable file, input data, environment variables, required computing resources, and output directives. 

There are two types of jobs – interactive and batch. An interactive job provides a way to directly communicate with the compute node from the command line. This is useful for testing and debugging purposes. For batch jobs, you must write a batch script that is run without user intervention. A batch script is a text file containing a sequence of commands that describe the requirements of your job. For example, a batch script indicates the number of nodes requested and expected wall clock time, identifies input files, the application program you want to run, and the location to write your output files.

You do not directly submit a batch script to the compute nodes, but rather you submit it to the batch scheduler where it is placed in a queue to be run later. The batch scheduler ensures optimal use of the cluster's resources by assigning your job to the compute nodes based on your site policies and node availability.  At any one time, there will be several jobs running with many more in the queue. The goal of the batch scheduler is to keep the compute nodes as full as possible while not leaving any jobs in the queue for too long. Nightingale uses the Simple Linux Utility for Resource Management (SLURM) scheduler to run jobs.
