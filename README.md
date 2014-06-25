######################

### pump.io http://pump.io Docker image - listens in port 80, 22

1) Install docker

2) clone  https://github.com/michielbdejong/docker-pump.io

3) Set up a data container with:
    /data/db (empty folder)
    /data/pump.io/pump.io.json (with your settings, like pump.io.json.sample in this repo)

4) Build the image:
    docker build -t pump.io docker-pump.io/

5) This can only run on port 2001 because of how pump.io self-points its hyperlinks. Suppose your data container is called 'michiel-data', run:

 docker run -p 2001:2001 -d --volumes-from michiel-data pump.io
