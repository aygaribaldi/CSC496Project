Team Members
============
- Alex Garibaldi
- Alex Kuhn
- Ryan Skipp
- David Matz

Project Performance Evaluation
==============================
Goal: 
Demonstrate the function of a few different benchmark programs through Docker/OpenStack/CloudLab, mainly: fio, nuttcp, netperf, and stream.

Project Subtasks:
Able to automatically Docker on a single CloudLab profile.
Able to install and configure the selected benchmarks and run the benchmarks. 

Paper Utilized for inspiration:
https://drive.google.com/file/d/1rnUlHRROm8RHGl46jj8QTjbRUsI_urli/view

Brief Installation Overview (covered in Technical Paper)
==================================================

1) Download and Install Alpine Linux VM in VirtualBox
2) Install Docker to the Alpine Linux VM
3) Install fio, nuttcp, and netperf in Ubuntu through Docker
4) Download and compile stream in Ubuntu through Docker
5) Upload completed VM image to OpenStack/CloudLab
6) Run benchmarks
