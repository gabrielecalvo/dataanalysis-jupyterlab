# Data Analysis - Jupyter Lab
Jupyterlab (with Miniconda) server installation on Alpine Linux container.

The image size is a bit hefty (1.63 GB) so it will take a few minutes to download.

**BEWARE**:
This is supposed to be a **DEMO** image, quickly showing the capabilites and flexibility of Jupyter Lab as a server so as default the instance will run as a server (listening to all IPs) and no password. This means that anyone in the same network can connect to it by knowing the IP and port of the machine running it.

For production you will **definitely** want to add security measures. Starting with the information [here](https://jupyter-notebook.readthedocs.io/en/stable/public_server.html).

# Basic Usage
You can run a throw-away container with this command (add the path of where you want your notebook to be saved):
```
docker run -it -d --rm \
    -p 9999:9999 \
    -v <path-to-where-your-notebooks-live>:/Notebooks \
    gabedotpy/dataanalysis-jupyterlab 
```
**Note**: the first time you run the command will trigger the download of the image which will take a few minutes. Once you have the image it will be much faster.

The instance will be available on https://localhost:9999, leave the password empty.


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

This image is a modified version of https://github.com/datarevenue-berlin/alpine-miniconda.