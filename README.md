# apptainer_tsp

An apptainer container image to run task-spooler (tsp)

## Usage

Download the sif file as follows

``` sh
wget https://github.com/oogasawa/apptainer_fio/raw/main/apptainer_tsp.sif
```

Execute `tsp` with apptainer as follows.

``` sh
apptainer exec apptainer_tsp.sif tsp -h
```


## How to build

1, First, build a docker container image.

```
git clone https://github.com/oogasawa/apptainer_tsp
cd apptainer_tsp
docker build -t apptainer_tsp:latest .
```

2, Create a tar file of the docker container image on your local hard disk.

``` sh
docker save -o apptainer_tsp.docker.tar apptainer_tsp:latest
```

3, Build a apptainer image file (`*.sif` file) from the docker image file.

``` sh
sudo apptainer build apptainer_tsp.sif docker-archive://apptainer_tsp.docker.tar
```

