# Development Environment

The development environment for PomodoroAmigo is established using a private network of virtual machines, instantiated and configured with Vagrant.

## Setup a fresh development environment
These directions are for a fresh development environment in which to develop the backend API and Database.
Directions for developing on the front end are available in the repositories for the various clients:
TODO: List links to the clients here

1. Install Vagrant
2. Clone this repository
3. Within the cloned repo run `vagrant init`

## Setup PostgreSQL Database VM
Connect to this vm with `vagrant ssh postgres`

Running on Ubuntu 20.04 and PostgresSQL 12.5.
This machine is running on the host and can be pinged at 10.0.0.80.
Port 5431 on the host machine maps to port 5432 on the guest (the vm).
This is done so that the PostgreSQL server running on the VM can be accessed via port 5431 from either the host machine OR other vms.

TODO: Get a schema dump and put directions here on how to restore it.

## API VM
Connect to this vm with `vagrant ssh api`
### Install nodejs, npm, and express
```
sudo apt update
sudo apt install nodejs
sudo apt install npm
mkdir api
cd api
npm init (accept all defaults)
npm install express --save (saves express as a dependency in package.json)
```
