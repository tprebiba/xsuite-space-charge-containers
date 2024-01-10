# xsuite-space-charge-containers

Dockerfiles for containers related to space charge xsuite codes.
Thanks to Kostas. 
Based on [ecloud-scrubbing-containers](https://github.com/ecloud-cern/ecloud-scrubbing-containers/blob/main/)

### To create your own container 

1. Install docker with sudo privileges:
    ```
    $ sudo apt-get install docker
    ```

2. Create a new project at [registry.cern.ch](https://registry.cern.ch/):

3. Build docker from container file
    ```
    $ sudo docker build -f xsuite_2024.1 -t registry.cern.ch/tprebiba/xsuite:2024.1 .
    ```

4. Push image to registry (find CLI secret at user profile):
    ```
    $ sudo docker login registry.cern.ch
    $ sudo docker push registry.cern.ch/tprebiba/xsuite:2024.1
    ```
    Check images by:
    ```
    $ sudo docker images
    ```
    Connect to docker:
    ```
    $ sudo docker run -it b1e2a3013cc0
    ```
    Delete docker:
    ```
    $ sudo docker rmi b1e2a3013cc0 --force
    ```

5. Add registry path to [recipe.yaml](https://gitlab.cern.ch/unpacked/sync/-/blob/master/recipe.yaml?ref_type=heads) (fork and merge).