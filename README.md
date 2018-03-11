<p align="center"><img src="https://s17.postimg.org/kwyw37sxb/0_Hl-1_BN46_JLi_Th8_UM.png" width="300" height="350"></p>

# Docker Cluster

Helps to create, destroy, scale, remove and test a docker-swarm locally.

## Requirements

This assumed you have virtualbox installed.

## Installation

Run the following to add the script to your system path
```sh
cp ./bin/docker-cluster $HOME/bin
```

Then run:
```sh
docker-cluster --help
```

## Usage

To get started run:
```sh
docker-cluster create --workers 2
```

There are options you may apply. 
If you wish specificy the amount of memory for the workers:
```sh
docker-cluster create --workers 2 --memory 1016
```
This command will create 1 manager, 2 workers and each one will contain 1016 MB of RAM.

Everytime you need another worker run the following command:
```sh
docker-cluster scale --workers 2
```
This command will create additonally 2 workers and join them to the swarm.

To get details about the swarm run:
```sh
docker-cluster ls
```

To remove a worker run:
```sh
docker-cluster destroy worker-1
```
This command will shut down worker-1, remove it from the swarm and delete it.

To remove all of the machines run:
```
docker-cluster destroy all
```
This command will delete all existing docker machines

To check your cluster you can run:
```sh
docker-cluster create --clients 2
docker-cluster test 1000
```
This command will create 2 client machines and send 1000 requests to the manager machine on port 80 

## Notes

The idea behind this tool is to speed up the workflow locally before going to production.
It has been tested on windows 10 using bash, but might work on linux, mac as well.

## Bugs Reporting

Please feel free to report any bugs you find :)
