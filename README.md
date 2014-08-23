# docker-jenkins

Sets up a container with jenkins installed listening on port 8080.

## Usage

To run the container, do the following:

    export JENKINS_PORT=12345 #where 12345 is the port that you want jenkins to listen on.
    export JENKINS_DIR=~/$(whoami)-jenkins
    docker run -d -P ${PORT}:8080 -v ${JENKINS_DIR}:/jenkins russell/jenkins
    
Your jenkins instance is now available by going to http://localhost:12345 .

### Persistent Configuration

By default, JENKINS_HOME is set to /jenkins.  The best way to persist or import configuration is to have a separate data volume for /jenkins.  Below are a few references on data volumes.
By following the above, this will be mounted to ~/yourname-jenkins/

  * https://docs.docker.com/userguide/dockervolumes/
  * http://aespinosa.github.io/blog/2014-03-05-import-jenkins-configuration-to-docker.html
  * https://github.com/aespinosa/docker-jenkins/blob/master/test/jenkins_test.bats#L3

## Building

To build the image, simply invoke

    docker build github.com/Russell-IO/docker-jenkins

A prebuilt container is also available in the docker index

    docker pull russell/jenkins


## Author

  * Allan Espinosa (<allan.espinosa@outlook.com>)
  * Gwenn Etourneau (<g.etourneau@free.fr>)
  * Russell Clare (<Russell@Clare.io>)

## LICENSE

Copyright 2013 Allan Espinosa <br>
Copyright 2014 Russell Clare

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
