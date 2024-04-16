## Fly.io redis server

This is a companion repo to host a local redis instance for the [Irish transport tracker](https://github.com/david-abell/transit-tracker).

## How to use

- `docker build --tag 'image_name' .`
- `docker run --detach 'image_name'`

## How to deploy

- flyctl cli `fly secrets set REDIS_PASSWORD=<your password>`
- flyctl `fly launch`

## Connecting on fly.io

To connect from another app on the same region. In the connecting app repository set env:

- flyctl cli `fly secrets set REDIS_PASSWORD=<your password>`
- flyctl cli `fly secrets set REDIS_HOST=<your fly app name>.internal`
