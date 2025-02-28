This folder defines the conda package build for Linux and Windows. There are runners for both Linux and Windows on GitHub Actions, but it is faster to experiment with builds locally first.

To build, first go to the base repo directory and install the build environment:

```
conda env create -f environment_build.yml -n sleap_build && conda activate sleap_build
```

And finally, run the build command pointing to this directory:

```
conda build .conda --output-folder build -c conda-forge -c nvidia -c https://conda.anaconda.org/sleap/ -c anaconda
```

To install the local package:

```
conda create -n sleap_0 -c conda-forge -c nvidia -c ./build -c https://conda.anaconda.org/sleap/ -c anaconda sleap=x.x.x
```

replacing x.x.x with the version of SLEAP that you just built.
