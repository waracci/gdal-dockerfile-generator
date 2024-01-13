## Build Instructions:

### About
Often I struggle coming up with a docker image containing a specific version of GDAL.

I built this simple UI that lets you select the:
1. Ubuntu container version
2. GDAL version
3. Python Version

Once the variables are selected, the generated Dockerfile will build a docker image. The instructions below outline what to do with the generated Dockerfile content.

### Generate your preferred Dockerfile

On the UI, select your preferred versions, Click on the `Generate Dockerfile` button to generate the result.

Click on the `copy` button to copy the generated content, you may also highlight your preferred sections and paste on a Dockerfile file on your machine.

follow instructions below on how to build the image, run it and verify that GDAL has been installed.

### Build the Docker Image:

```bash
docker build -t my_container:latest -f path/Dockerfile .
```

The command above builds a Docker image tagged as `my_container:latest` using the Dockerfile located in the provided path. Ensure you have selected the preferred Python and GDAL versions in your Dockerfile.

### Run the Container:

```bash
docker run -it --rm my_container:latest /bin/bash
```
The command above runs the Docker container interactively, removing it (`--rm`) after exiting. The /bin/bash ensures you have a shell inside the container for further interaction. Exit the container shell when done inspecting the container.

### Check GDAL Version:

```bash
docker run -it --rm my_container:latest gdalinfo --version
```
Use the command above to verify the installed GDAL version within the container.
