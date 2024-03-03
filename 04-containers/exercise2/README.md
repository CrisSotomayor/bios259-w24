# Docker hands-on exercise 2

## Introduction
This exercise will guide you through the process of using an existing image, the one you created in excercise 1, to create a new image. 

**Note:** Please complete [**exercise 1**](/04-containers/exercise1/) first before you work on this.

### Instructions

1. **Work on the forked/cloned repository**:You already have the GitHub repo https://github.com/asntech/bios259-w24 locally. Next change the directory to  `04-containers/exercise2`  where you will find Dockerfile and the Python application `app2.py`.

    ```bash
    cd bios259-w24/04-containers/exercise2
    ```

2. **Modify the Dockerfile**: Open the `Dockerfile` in a text editor. Now you need to use the docker image from your docker hub account that you pushed in excercise 1 as the starting point. You will see in the app2.py that it now also requires `seaborn` package to run `app2.py` and we already have `python` and `click` pre-installed.


3. **Build the Docker image**: Once you have modified the Dockerfile, build the Docker image using the `docker build` command. Replace `<image_name>` with a suitable name for your Docker image.

    ```bash
    docker build -t <image_name> .
    ```

4. **Run the Docker container**: After the image is built successfully, you can run a container from the image to ensure that it works as expected.

    ```bash
    docker run <image_name>
    ```

    Make sure that your first name is displayed as expected in the output of the application.

5. **Push the Docker image to Docker Hub**: Now, it's time to push your modified Docker image to Docker Hub. First, log in to Docker Hub using the `docker login` command.

    ```bash
    docker login
    ```

    Enter your Docker Hub credentials when prompted.

6. Tag your Docker image using your Docker Hub username and the desired repository name.

    ```bash
    docker tag <image_name> <username>/<repository_name>
    ```

7. Finally, push the tagged Docker image to Docker Hub.

    ```bash
    docker push <username>/<repository_name>
    ```

8. Verify on Docker Hub: Visit your Docker Hub profile on the web and confirm that your Docker image has been pushed successfully.

9. You may want to commit and push it GitHub to brush-up your Git skills from day 2 :-)

10. **Bonus task**: Create a `Singularity` image using the Docker image you just pushed to Docker Hun and try to run it as a Singularity container.

## Conclusion

Congratulations! You have successfully modified a Dockerfile, built a Docker image with your changes, and pushed it to Docker Hub. This exercise demonstrates a basic workflow for Docker image modification and distribution.