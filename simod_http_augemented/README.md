# Simod Http with Cors

This folder helps with the integration of the [Simod](https://github.com/AutomatedProcessImprovement/Simod) business process simulation model miner.
It includes:
- _An [adapted version](./main.py) of a specific version of the simod http api [main](https://github.com/AutomatedProcessImprovement/Simod/blob/2f3b7391f9e49e248927d61e07ec9e26d16d77e7/src/simod_http/main.py) file._<br>
This version adds CORS clearance to the original one. The original file was created by Ihar Suvorau under the Apache License 2.0.
- _A [Dockerfile](./Dockerfile) that plugs this adapted main file into the [simod-http/3.2.1-prerelease38](https://hub.docker.com/layers/nokal/simod-http/3.2.1-prerelease38/images/sha256-27cdef1308a9f796cbe805ef0ca9a043fae928d36c37de0471f8d13b59a0e0e6?context=explore) image._ <br>
We use this older version, as recently there have been major application structure changes for the simod htpp api. Note: This also means an older version of Simod is used, consequently, newer bug fixes and features might not be present.

## How to run it

### As Part of Docker-Compose 
The easiest way to start the augmented Simod is as part of the docker-compose of the [SimuBridge root project](https://github.com/INSM-TUM/SimuBridge). For this, please refer to the instructions there.

### As Stand-alone Docker Container
To run it as stand-alone docker container, you need to first build the respective docker image by navigating to this folder and calling
``` console
 docker build -t simod-http-cors:1.0.0 .
```

Once the image ist built, you can start it with
``` console
docker run -it -p 8880:80 simod-http-cors:1.0.0
```

### For development purposes
To quickly test out changes to the `main.py` without having to rebuild the container, you can use the following command to start a container:
``` console
docker run -it -v $PWD/main.py:/usr/src/Simod/src/simod_http/main.py -p 8880:80 nokal/simod-http:3.2.1-prerelease38
``` 