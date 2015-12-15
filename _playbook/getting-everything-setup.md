---
layout: page
title: 'Getting Everything Set Up'
parent: the-microwizard
previous: the-microwizard
next: microservices-in-action
---
The Microwizard base system runs inside of a VirtualBox VM. We provision the VM using Vagrant and then use a combination of shell scripts, Ansible playbooks, and custom code to smooth over the experience. Developers must be running a modern Linux distribution or Mac OS X (we’ve tested on Fedora 22 and OS 10.10 Yosemite) and should have the following software installed before trying to use Datawire Microwizard:

| ----------- | ---------- | ------------ |
| Software    | Version    | Instructions |
| Ansible     | &gt;=1.9.4 | `pip ansible install` <br>or see the official [install](http://docs.ansible.com/ansible/intro_installation.html) instructions |
| Vagrant     | &gt;=1.7.4 | [Install](https://docs.vagrantup.com/v2/installation/index.html) |
| Virtual Box | &gt;= 5.0  |[Install](https://www.virtualbox.org/wiki/Downloads) |

### To get started, do the following:

1. Clone the MicroWizard project on GitHub, as well as some of the Git submodules linked into this repository:
  `git clone --recursive git@github.com:datawire/microwizard.git1`
  _Note: Using the --recursive flag is equivalent to running git submodule init &amp;&amp; git submodule update after a normal git clone command._
2. Start vagrant by running vagrant up. This will take some time as the Microwizard bootstraps inside the VM, possibly as long as 15-20 minutes depending on your system - be patient, this step is automating a lot of configuration so you don't have to do it manually.
3. Once the initial provisioning has completed run ./scripts/lobsters-up to bring up the demonstration monolith application. Note that it usually takes from 3 to 5 minutes for Lobsters to fully provision itself for use (and can take even longer at times).
4. Go to <a href="https://www.google.com/url?q=http://127.0.0.1:3000/&amp;sa=D&amp;usg=AFQjCNEcnz03GQK9Y22x5DxV3s9vuCGCYQ">http://127.0.0.1:3000/</a> to see the Lobster application running. You'll notice that this web page has a link at the top called "Most Popular Users" - this is not normally present in a standard Lobsters install; we added it to the monolith to provide access to data from the new microservice.