# Running

### Using Docker \(recommended\)

**Build the Dockerfile**

```text
yarn node:build
```

or

```text
docker build -t kyve-node:latest .
```

**Run the node**

```text
yarn node:run
```

or

```text
docker run --name kyve-node kyve-node:latest
```

### Using NodeJS

To run the KYVE node using NodeJS simply, start the script:

```text
yarn start
```

