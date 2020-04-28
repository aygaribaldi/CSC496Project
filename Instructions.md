In this project, what we are doing is setting up an Alpine Linux image, installing Docker onto that image, installing our testing programs through Docker, and then using them through Docker.

- Step 1: Prepare Alpine Linux Image. Follow Ngo's slides on how to do this.

- Step 2: Update and Prepare Alpine Linux
    - Make sure you have a non root user created (student)
    - Update system, run the following commands (as root):
      - su (if logged in as student, this will log you in as root)
      - apk update (updates list of programs from repos)
      - apk upgrade (upgrades your installed versions of these programs)
    - Install nano text editor (just like we use to code in Haskell)
      - apk add nano (installs nano text editor)
      - exit (logs you out as root)

- Step 3: Installing Docker to this image we have created
  - So we can install Docker, add community repo to /etc/apk/repositories file. Run the following commands:
	  - nano /etc/apk/repositories (opens up file to edit in nano)
	  - add line http://dl-cdn.alpinelinux.org/alpine/latest-stable/community (this is the repo we need)
  - Install and start Docker daemon at boot, allow non root user to use Docker (as root user)
	  - apk update (updates list of programs from repos)
	  - apk upgrade (upgrades your installed versions of these programs)
	  - apk add docker (installs docker, oh boy)
	  - service docker start (starts docker service)
	  - rc-update add docker boot (starts docker service at boot from now on)
	  - addgroup student docker (adds your non-root user to docker group, so you can use docker as non-root)
  - install testing tools under ubuntu docker image (should now work as non-root user)
	  - docker run -it ubuntu (starts up ubuntu in Docker)
	  - apt-get update (update list of programs from repo, just like apk update does in Alpine)
	  - apt-get install fio (installs fio testing program, this measures disk speed)
	  - apt-get install nuttcp (installs netccp testing program, this measures network bandwith)
  - save as new image (you can check his slides for this stuff if confused)
	  - exit (logs out of Docker) (take note of ID should be like bf7g89f7gd89s0 or some number like that)
	  - docker commit (ID) ubuntu-csc496 (this saves ubuntu image + testing programs)

- Step 4: Now, booting up Alpine from scratch, you should be able to:
  - login as student (non-root user)
  - type "docker run -it ubuntu-csc496" to start up your Docker image
  - now you're in your Docker image and can run the benchmarks!

- Step 5: Testing using fio
	- https://arstechnica.com/gadgets/2020/02/how-fast-are-your-disks-find-out-the-open-source-way-with-fio/
	- This program is used to test disk writing and reading speed. We can compare the values on our local machines, to the     values when this is running on CloudLab.

- Step 6: Testing using nuttcp
	- https://fasterdata.es.net/performance-testing/network-troubleshooting-tools/nuttcp/
	- This program can be used to test network bandwith. We can treat our 

- Step 7: Work in Progress: testing memory bandwith using Stream

- Step 8: Work in Progress: testing network latency using netperf

- Step 9: Upload all of this to CloudLab and run using OpenStack just like we did in class. Use his slides for this.
  - In doing this, we will be able to test the performance difference between when we run this stuff on our machines, versus when we run this "in the cloud" (on CloudLab through OpenStack).
