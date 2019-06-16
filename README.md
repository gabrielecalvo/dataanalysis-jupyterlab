# Data Analysis - Jupyter Lab
Jupyterlab (with Miniconda) installation on Alpine Linux container.

Inspired by https://github.com/datarevenue-berlin/alpine-miniconda

# Basic Usage
You can run a throw-away container with this commands:
```
docker run -it --rm gabedotpy/dataanalysis-jupyterlab
```
The instance will be available on https://localhost:9999

# Docker-compose Usage
In alternative, edit and use the docker-compose file to create an instance with bound folders, this way the data is not thrown away.

The lines you need to edit are:
```
  - <path-to-where-your-notebooks-live>:/Notebooks
  - <path-to-where-your-data-lives>:/DataDrive
```

To run it, navigate to the folder where you edited file is and run:
```
docker-compose up
```
