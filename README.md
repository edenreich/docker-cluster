# docker-cluster
Helps to create, destroy, scale, reduce a docker-swarm locally

# Installation

Run the following to add the script to your system path
```sh
cp ./bin/docker-cluster $HOME/bin
```

Then run:
```sh
docker-cluster --help
```

# Usage

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
