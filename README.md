# SigNoz Monitoring Playground

### Step 1 (Stack Installation)
#### Installation
```sh
docker compose -f deploy/docker/clickhouse-setup/docker-compose.yaml up -d
```
Open http://localhost:3301 in your favourite browser. To check if works the SigNoz UI.

> Note: You have to create a SigNoz account to access into the UI. You'll find the instructions during the process.
### Step 2 (Sample PHP App)
#### Generating traces
To generate distributed traces, run:

```bash
# navigate to the distributed-tracing
cd sample-php-app/distributed-tracing

docker compose run --rm service-one composer install
docker compose up

# in a separate terminal
$ curl localhost:8000/users/otel
```
Open http://localhost:3301 in your favourite browser. And check if you can see the traces generated from the sample app.

### Step 3 (Sample ReactJS App)

#### Generating traces
To generate distributed traces, run:

```bash
# navigate to the sample-reactjs-app
cd sample-reactjs-app

docker compose run --rm front yarn install
docker compose up
```
Open http://localhost:3000 and generate traces to SigNoz

#### Hit the app a couple of times before actually seeing the tracing/logs on the SigNoz dashboard

### Step 4 (Sample Golang App)
#### Generating traces
To generate distributed traces, run:

```bash
# navigate to the sample-golang-app
cd sample-golang-app

docker compose run --rm golang go mod tidy
docker compose up
```
Open http://localhost:8090/books and generate traces to SigNoz
