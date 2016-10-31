Alpine-test-PHP
===================


This image aims to run PHP5 tests.



Building the base image
-----------------------

To create the base image `ahgora/alpine-php5-build`, execute the following command on the tutum-docker-php folder:

      docker build -t ahgora/alpine-test-php  .


Running your Apache+PHP docker image
------------------------------------

Start your image, build its link to whichever other container you need to connect to:

      docker run -t -d --link cassandra:cassandra  ahgora/alpine-test-php


Loading your PHP application into the container to test
--------------------------------------------------------


Once you have this container running you will need to copy your project to its container.


     docker cp <project_folder> <containerid>:/


Acess its container by:


     docker exec -it <containerid> /bin/sh


If you are using makefile to organize code compilation as this project, you can execute the command below:


make test

You will get the results of your tests as soon as its test complete.


That's it!

