# Running

## Run the node on your local machine

Install the dependencies

```text
yarn install
```

Build the node

```text
yarn build
```

Run it

```text
yarn start
```

## Run the node using Docker \(recommended\)

Build the Dockerfile

```text
docker build -t kyve-node:latest .
```

Run the container

```text
docker run --name kyve-node kyve-node:latest
```

