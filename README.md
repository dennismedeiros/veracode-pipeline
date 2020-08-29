![GitHub](https://img.shields.io/github/license/dennismedeiros/veracode-pipeline?style=plastic)

![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/dennismedeiros/veracode-pipeline)
![Docker Pulls](https://img.shields.io/docker/pulls/dennismedeiros/veracode-pipeline)

# veracode-pipeline

![Docker Image Version (tag latest semver)](https://img.shields.io/docker/v/dennismedeiros/veracode-pipeline/latest)

![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/dennismedeiros/veracode-pipeline)


## Description: 
This container image contains a version of the Veracode Pipeline Scanner. Configured to perform the actions available to the Veracode Pipeline Scanner in a secure way. All the actions available to the Veracode Pipeline Scanner can be perform by calling **Pipeline** and passing in the arguments as requied for the action. **Pipeline** is aliasing for java -jar /app/veracode-pipeline.jar command call.

The containter also now has environmental variable for **VERACODE_ANALYSISCENTER_ID** and **VERACODE_ANALYSISCENTER_KEY** to be passed instead of as arguments throug the command line.

## Docker Examples
### Example of retrieving the pipeline version
> `docker run --rm -e VERACODE_ANALYSISCENTER_ID=<veracode_id> 
    -e VERACODE_ANALYSISCENTER_KEY=<veracode_key>
    dennismedeiros/veracode-pipeline:latest Pipeline -version`

### Example of running a SAST application scan while passing environmental variables
> `docker run --rm -v $(pwd)/target:/target 
    -e VERACODE_ANALYSISCENTER_ID=<veracode_id> 
    -e VERACODE_ANALYSISCENTER_KEY=<veracode_key>
    dennismedeiros/veracode-pipeline:latest Pipeline -f /target/verademo.war`

## GitLab Examples: