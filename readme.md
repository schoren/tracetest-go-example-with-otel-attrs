# how to run

```sh
export TAG=v0.12.2
docker compose build
docker compose up -d
sleep 10
docker compose restart otel-collector
docker run --rm -it -v$(pwd):$(pwd) -w $(pwd) --network host --entrypoint tracetest kubeshop/tracetest:${TAG} -s http://localhost:11633 test run -d ./test-api.yaml -w
```