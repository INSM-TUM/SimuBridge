# Simod Http with Cors

This folder helps with the integration of the [Simod](https://github.com/AutomatedProcessImprovement/Simod/tree/master) business process simulation model miner.
It includes:
- _An [adapted version](./main.py) of a specific version of the simod http api [main](https://github.com/AutomatedProcessImprovement/Simod/blob/2f3b7391f9e49e248927d61e07ec9e26d16d77e7/src/simod_http/main.py) file._<br>
This version adds CORS clearance to the original one. The original file was created by Ihar Suvorau under the Apache License 2.0.
- _A [Dockerfile](./Dockerfile) that plugs this adapted main file into the [simod-http/3.2.1-prerelease38](https://hub.docker.com/layers/nokal/simod-http/3.2.1-prerelease38/images/sha256-27cdef1308a9f796cbe805ef0ca9a043fae928d36c37de0471f8d13b59a0e0e6?context=explore) image._ <br>
We use this older version, as recently there have been major application structure changes for the simod htpp api. Note: This also means an older version of Simod is used, consequently, newer bug fixes and features might not be present.