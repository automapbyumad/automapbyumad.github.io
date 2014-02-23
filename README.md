# Automapbyumad website

The website is hosted on GitHub Pages at this location: [http://automap.ixartz.com](http://automap.ixartz.com) and the content is generated from PHP files.

## How to generate the static content

### Installation

We will host the dynamic website on a local Virtual Machine. So, you need to install:
* VirtualBox
* Vagrant

### File location

First, clone Automap website repository

### Run the Virtual Machine

You can now launch your Virtual Machine (VM):

    cd ${folder}/site && vagrant up

Then, you can ssh to the VM:

    vagrant ssh

### Set up MySQL database

You need to configure MySQL database and load the data into MySQL:

    mysql -u root -p
    # the default password is root

    mysql> create database test;
    mysql> use test;
    mysql> source /vagrant_data/umad.sql

### Test

Open your browser at *http://192.168.33.10* and you shoud see Automapbyumad website

### Generate a static version

Finally, you can generate the static version of the website:

    wget -k -E -r -l 10 -p -N -nH http://192.168.33.10
