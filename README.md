# SigNoz PHP Monitoring Playground

### Step 1 (Stack Installation)
### Installation
```sh
docker compose -f deploy/docker/clickhouse-setup/docker-compose.yaml up -d
```
Open http://localhost:3301 in your favourite browser. To check if works the SigNoz UI.

> Note: You have to create a SigNoz account to access into the UI. You'll find the instructions during the process.
### Step 2 (Sample App Installation)
### Generating traces
To generate distributed traces, run:

```bash
# navigate to the distributed-tracing
cd sample-php-app/distributed-tracing

docker compose run service-one composer install
docker compose up

# in a separate terminal
$ curl localhost:8000/users/otel
```
Open http://localhost:3301 in your favourite browser. And check if you can see the traces generated from the sample app.
