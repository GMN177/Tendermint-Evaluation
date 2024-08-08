# Tendermint-Evaluation

This repo investigates Tendermint's approach to Byzantine consensus and overlay management, aiming to evaluate its dependability from both functional and performance perspectives.

---

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)

---

## Installation

1. Install [Docker](https://docs.docker.com/get-docker/)
2. Install [Docker Compose](https://docs.docker.com/compose/install/)
3. Clone the [Tendermint Evaluation project repository](https://github.com/GMN177/Tendermint-Evaluation)
4. Go to the root directory of the project and run the following command to build the docker images:

```sh
docker compose build
```

---

## Usage

- After completing the [Installation](#installation) steps the infrastructure can be started with:

```sh
docker compose up
```

- To begin a load test run the following command:

```sh
docker exec -it tester sh -c "build/tm-load-test -c 1 -T 90 -r 100 -s 250 --broadcast-tx-method async --endpoints ws://node0:26657/websocket,ws://node3:26657/websocket"
```

- To reset the state of the chain, stop all running containers and run the following command:

```sh
docker compose -f reset-docker-compose.yaml up
```