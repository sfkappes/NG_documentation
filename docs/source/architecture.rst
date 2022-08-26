=====================
System Architecture
=====================

**Introduction**

The NCSA Nightingale cluster is a HIPAA-capable RedHat Linux OS High-Performance Computing (HPC) environment
created to support UIUC researchers and collaborators who engage in
analysis of regulated sensitive data, like electronic Protected Health Information
(ePHI) or CUI. The cluster resides within a secure environment and follows
NCSA and University of Illinois security policies and procedures to
ensure conformance and protection of ePHI, CUI, and other such data types.

| 

**ACHE Environment**

The Nightingale cluster provides a high-performance environment within
the\ `Advanced Computational Health Enclave
(ACHE) <https://wiki.ncsa.illinois.edu/display/ACHE/ACHE%3A+NCSA+Internal+Use+Space>`__.
The ACHE is a special environment with restricted physical and
electronic access within NCSA’s National Petascale Computing Facility.
It is a physically isolated 1000-square-foot data center that is
strictly managed to support electronic Protected Health Information. It
follows HIPAA standards and University of Illinois policies and
procedures to ensure conformance and protection of ePHI. The ACHE
undergoes annual security assessments as well as\ `SOC2
Type2 <https://wiki.ncsa.illinois.edu/display/ACHE/SOC+2+Compliance+Testing+Procedures>`__\ certification.
ACHE’s controls supporting the security and confidentiality criteria are
summarized in the table below.

Many of the restrictions that make the ACHE environment possible mean
that many tasks that users want to do are more complicated than they
would be on other HPC systems. Installing software, particularly,
requires interaction with Nightingale staff. The Nightingale
documentation that you're reading now generally explains this process.
Please see the User Software documentation page for details. If you have
further questions that page doesn't answer, please submit a ticket and
chat with Nightingale support staff.

| 

**Technical Specification**

Nightingale provides standard batch computing options and interactive
compute nodes. The compute nodes are a mix of CPU nodes and nodes with 
GPUs set up for double precision work (A100) or single precision work (A40).
These are made available to users as dedicated servers or shared
environments based on the needs of each research project. Nightingale
offers database services to support long-term data storage and
management with the ability to share and access relational databases on
the system. With 880 TB of high-speed parallel LUSTRE-based storage, the
system adequately supports the researchers’ needs for sharing data as
well as generating and storing results.

Batch Computing

-  16 dual 64-core AMD systems with 1 TB of RAM
-  2 dual-A100 compute nodes with 32-core AMDs and 512 GB of RAM

Interactive Compute Nodes

-  4 interactive compute/login nodes with dual 64-core AMDs and 512 GB
   of RAM

-  6 interactive nodes with 1 A100, dual 32-core AMDs with 256GB RAM

-  5 interactive nodes with 1 A40 with dual 32-core AMDs and 512GB RAM

| 

**Nightingale Nodes**

Some users will have an assigned "interactive" node. If your project has
one of these, you will be told about this. The hostname will be
something like ng-rollingstones01.ngale.internal.ncsa.edu.

If your group doesn't have an assigned node, then you will log into one
of the general login nodes:

-  `ng-login01.ngale.internal.ncsa.edu <http://ng-login01.ngale.internal.ncsa.edu>`__
-  `ng-login02.ngale.internal.ncsa.edu <http://ng-login02.ngale.internal.ncsa.edu>`__

If you need to run batch jobs on Nightingale compute nodes (see the
batch job documentation page for details) then you'll likely set up and
queue the jobs from the general login nodes.
