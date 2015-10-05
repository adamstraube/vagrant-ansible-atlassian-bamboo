# Easy Atlassian Bamboo VM with Vagrant and Ansible

This repo has all that you need to get an Atlassian Bamboo server up quickly (with license key or trial key from Atlassian of course). Useful if you want to test if continuous integration works in your environment, it is also easy to migrate the database later as PostgreSQL is also installed.

## Prerequisites

To make use of these files, you'll need to have the following prerequisites installed on your workstation:

* [VirtualBox](https://www.virtualbox.org/)
* [Vagrant](http://www.vagrantup.com/)
* [Ansible](http://www.ansibleworks.com)

A second VM with a GUI and browser in Virtualbox connected to the internal network labelled `int-bamboo`. Changing the interface to `Bridged` in `Vagrantfile` will allow you to access the machine on any machine in the local network if desired.

## Getting Started

To begin, create an empty directory and clone the files in this repository into it.

Then just run the command `vagrant up` and your VM should bootstrap itself into existence.

Once the bootstrap is complete, open up a browser and go to [http://192.168.23.3:8085/](http://192.168.23.3:8085/). 

Go get a trial key (or purchase a paid on) from Atlassian (click on the Atlassian link on the page) and put it in the `License key` field.

Make sure you click `Custom Installation` as we are going install to the database.

* General configuration - Change the name of the instance here
* Database configuration - Click `External` and select `PostgreSQL`
* Choose how you wish Bamboo to connect to your database - Connection type `Direct JDBC connection`, username `bamboouser`, password `bamboouser`
* Select starting data for Bamboo - Select `Create a new Bamboo home`
* Set up administrator user - Create you admin user here


All done! This site can get you started creating a CI workflow for [Java](https://confluence.atlassian.com/bamboo/getting-started-with-java-and-bamboo-289277286.html) or [.NET](https://confluence.atlassian.com/bamboo/getting-started-with-net-and-bamboo-289277288.html)


## License

Thanks to:

ANXS for the
 - [PostgreSQL Ansible role](https://galaxy.ansible.com/list#/roles/512)  [Github Link](https://github.com/ANXS/postgresql)

kbrebanov for
 - [Java Ansible role](https://galaxy.ansible.com/list#/roles/3309) 
 - [Bamboo Ansible role](https://galaxy.ansible.com/list#/roles/3383)

Copyright (c) 2015 Adam Straube

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program.  If not, see <http://www.gnu.org/licenses/>. 

