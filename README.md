# Cloudlab Kubernetes Energy-Efficient Scheduler Benchmark

Helm chart to run with [this cloudlab profile](https://github.com/H3rby7/cloudlab-k8s-ee-sched)

Automates the following process:

1. [Create a workmodel](https://github.com/H3rby7/muBench-workmodel-gen) in 
   1. From a dataset ([example](https://github.com/H3rby7/cloudlab-k8s-ee-sched-data))
2. [Template](https://github.com/H3rby7/muBench-k8s-templater) [service cells](https://github.com/H3rby7/muBench-svc-cell)
3. [Run Trace CSV](https://github.com/H3rby7/muBench-csv-runner)
   1. Calls the service cells using microservice call graphs
   2. Each service cell consumes resources ([example](https://github.com/H3rby7/cloudlab-k8s-ee-sched-functions))

- [Cloudlab Kubernetes Energy-Efficient Scheduler Benchmark](#cloudlab-kubernetes-energy-efficient-scheduler-benchmark)
- [Developing](#developing)

# Developing

Local test setup using docker-compose:

    docker-compose up -d

    docker-compose exec helm bash

    helm template /chart -f /example/my-values.yaml --output-dir /generated
