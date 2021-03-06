# OMERO.server and OMERO.web (docker-compose) with figure export

Example of running OMERO.server and OMERO.web in Docker.

This configuration will enable the export figure option based on: 
https://github.com/ome/omero-figure#enabling-figure-export **(Option 2)**


OMERO.server is listening on the standard OMERO ports `4063` and `4064`.
OMERO.web is listening on port `4080` (http://localhost:4080/).

Log in as user `root` password `omero`.
The initial password can be changed in [`docker-compose.yml`](docker-compose.yml).

## Run

    docker-compose up -d
    docker-compose logs -f


To make sure OMERO stores all the data on a different storage volume instead of writing to the server storage itself:

    chmod ug=rwx path_to_external_storage
    
This will give the owner or the user read/write/executable permissions to the this folder.
Change the docker-compose.yml file at this line:

        volumes:
            - "omero:/OMERO"
            
(https://github.com/pr4deepr/docker-example-omero/blob/bd71124a6b3d5ddb932a2e6b7d37e821d642e6ba/docker-compose.yml#L29)

to:

    volumes:
    - "path_to_external_storage:/OMERO"
        

See here for more details on enabling figure export and changing location of storage
https://github.com/ome/docker-example-omero/issues/6


For more configuration options see:
- https://github.com/ome/omero-server-docker/blob/master/README.md
- https://github.com/ome/omero-web-docker/blob/master/README.md
- https://github.com/ome/omero-figure#enabling-figure-export
- https://github.com/ome/docker-example-omero/issues/6

