# Octave dockerfile for BFM model

The project is init Just because I don't want to install Matlab. I have modified the relevant files to fit the octave run.

## Prepare BFM data

[Link](https://github.com/LucienXian/octave_run_BFM_docker/blob/master/runBFM/readme.md)

## build

1. Enter the folder

```shell
cd octave-docker
```

2. build the docker file

```shell
docker build --build-arg UBUNTU_MIRROR="http://mirrors.163.com"  -t bfm/octave .
Or
docker build -t bfm/octave .
```

## run

1. run the docker 

```shell
docker run --rm -v $(pwd):/source bfm/octave /source/generate.m
```

## Thanks

[Octave-dockerfile](<https://github.com/openmicroscopy/octave-docker>)

[Face-3d](<https://github.com/YadiraF/face3d>)