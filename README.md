Hydra Camp Box
==============

Scripts to build a Vagrant based VM for running Hydra Camp tutorials.

The current versions provisioned by this build script are:

* Ubuntu server 16.04 LTS (bento/ubuntu-16.04)
* rvm >= 1.29.3
* ruby 2.4.2
* rubygems >= 2.7.6 
* Rails 5.1.6
* java version 1.8 (openJDK)
* Redis server >=2.8.4
* ImageMagick 7.0.7
* FITS 1.0.5
* ffmpeg 3.4

The build scripts also installs the gems necessary to run a Hyrax 2.1 (Beta) application:

* Solr Install files
    * version 6.6.2
* Fedora Install files
	* 4.7.5
* Hyrax demo application
	* Includes `gem "hyrax"` and dependencies (version 2.1.0.beta2)

How to use this repo
--------------------

#### Pre-requisites ####
* Virtual Box - https://www.virtualbox.org
* Vagrant - https://www.vagrantup.com

### Option #1 ###
Just use Vagrant to load the fully configured boxfile for the release version in this repo. Both Vagrant and VirtualBox need to be installed on your local system.  

    vagrant init camper http://camp.curationexperts.com/vagrant-boxes/dce-boxes.json
    vagrant up


### Option #2 ###
Clone this repo to your local system and run the setup scripts yourself.  Both Vagrant and VirtualBox need to be installed on your local system.  

    git clone --recurse https://github.com/curationexperts/camper.git
    cd camper
    vagrant up

Now you have a fully configured VM running Ubuntu server along with all of the necessary softward to support a complete Hydra development environment.

#### Notes ####
Option #2 depends on a much smaller base box, but needs to run a significant number of additional configuration scripts and downloads.  This option may be quicker to run for single installs, but downloading the file for option #1 will be quicker for classroom and demo installations where you need the system installed on multiple machines - download the file to one machine and then copy it locally via network shares or usb drives.

The fully configured VM used by options #1 is approximately 1.25GB, so either of these options may take a considerable amount of time to download depending on your connection speed. 

The Vagrantfile is configured to allocate 4gb RAM to the VM.  If your host machine has more or less than 8gb physical memory installed, you may want to increase or decrease the amount of memory allocated to the VM.


Running Vagrant & Learning Hydra
--------------------------------

* To start the VM: `vagrant up`
* To access the VM: `vagrant ssh`
* To stop the VM: `vagrant halt`
* To halt and restart the VM: `vagrant reload`
* To erase the VM and start over: `vagrant destroy`


Learn more about Samvera here: https://samvera.github.io
And here: https://wiki.duraspace.org/display/samvera/Samvera 
Learn more about Vagrant here: https://docs.vagrantup.com  
