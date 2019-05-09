# compose-nginx-example
Example project to show fronting multiple containers with nginx

## Overview
This project uses docker-compose to create a nginx containers that serves as a fontend proxy to 2 separate apache:php containers and one tomcat container.


## Usage 

Clone or download the project, change directory into the project and type: 

```
docker-compose up -d
```

Once it is up and running, try these different urls in your browers (the all resolved to 127.0.0.1)

```
http://classic.martinipunk.com  http://vesper.martinipunk.com  http://dirty.martinipunk.com

```
For the the first two, you should get a phpinfo results page.  Search on those pages for the keyword variable:  CONTNAME.  The 
results will prove that you are contacting two separate containers.

For dirty.martinipunk.com you should receive a tomcat default page.  

To stop the stack, type

```
docker-compose down
```

If you make changes to the Dockerfiles, or the underlying configs, be sure and rebuild before bringing the stack up with:

```
docker-compose build
docker-compase up -d
```

## Author

  * Barry Johnson (<cyclist@clemson.edu>)
