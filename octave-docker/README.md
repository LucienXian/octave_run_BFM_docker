# Octave

Lightweight development environment for testing Octave scripts.

## Usage

```
$ docker run --rm -it bfm/octave                   # Octave shell
$ docker run --rm -it --entrypoint bash bfm/octave # Bash shell
$ docker run --rm openmicroscopy/octave -h                    # Get octave help
$ docker run --rm openmicroscopy/octave example1.m arg1       # Run the example file
$ docker run --rm -v $(pwd):/source bfm/octave /source/myfile.m
```

Mount your local source folder to the container and run it inside the container.

## Modified from [link](https://github.com/openmicroscopy/octave-docker)