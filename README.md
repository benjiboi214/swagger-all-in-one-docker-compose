# Open API / Swagger Usage

## References
- [Installing the Docker Image](https://swagger.io/docs/open-source-tools/swagger-ui/usage/installation/)
- [Run Swagger using Docker Compose](https://github.com/elevennines-inc/swagger-all-in-one-docker-compose)

## Installation
Get the Docker Images
```bash
$ docker pull swaggerapi/swagger-ui
$ docker pull swaggerapi/swagger-editor
$ docker pull danielgtaylor/apisprout
$ docker pull nginx:mainline-alpine
```

Set the Workspace Env Var
```bash
# Add to ~/.bashrc
export WSCODE_BASE_DIR="/Users/belliot/Develop/workspace"
alias wscode="code $WSCODE_BASE_DIR"
```

## Run it with Docker
```bash
# Defaults
docker run -p 80:8080 swaggerapi/swagger-ui
```

```bash
# Provide a swagger.json
docker run -p 80:8080 -e SWAGGER_JSON=/foo/swagger.json -v /bar:/foo swaggerapi/swagger-ui
```

## Run it with Docker Compose
Cleaner approach, as docker compose will clean up after us when we're done. Docker images will remain, especially when we forgot to clean up after ourselves.
```bash
# Run the example
docker-compose -f $WSCODE_BASE_DIR/open_api/docker-compose.yml up 
```

On the other hand, you may have your own swagger API that you want to view or edit.
- Copy docker-composer.yml to your directory
- Update the non-defaults based on your new location
- Run the above command, changing the `-f` flag to your new `docker-compose.yml` file's location.
