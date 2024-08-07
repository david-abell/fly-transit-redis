## Fly.io redis server

This is a companion repo to host a local redis instance for the [Irish transport tracker](https://github.com/david-abell/transit-tracker).

## How to use

- `docker build --tag 'image_name' .`
- `docker run --detach --expose 6379 -p 6379:6379 'image_name'`

## How to deploy

- flyctl cli `fly secrets set REDIS_PASSWORD=<your password>`
- flyctl `fly launch`

## Connecting on fly.io

To connect from another app on the same region. In the connecting app repository set env:

- flyctl cli `fly secrets set REDIS_PASSWORD=<your password>`
- flyctl cli `fly secrets set REDIS_HOST=<your fly app name>.internal`

If the docker container fails to find `start-redis-server.sh` check that the file line endings are set to LF and not CRLF. 
