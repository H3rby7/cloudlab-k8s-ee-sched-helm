# Cloudlab Kubernetes Energy-Efficient Scheduler Benchmark

- [Cloudlab Kubernetes Energy-Efficient Scheduler Benchmark](#cloudlab-kubernetes-energy-efficient-scheduler-benchmark)
  - [Usage](#usage)
- [Developing](#developing)

## Usage

Helm chart to run with [this cloudlab profile](https://github.com/H3rby7/cloudlab-k8s-ee-sched)

      helm repo add ee-sched https://h3rby7.github.io/cloudlab-k8s-ee-sched-helm
      helm repo update
      helm install my-release ee-sched/cloud-ee-bench

Automates the following process:

1. [Create a workmodel](https://github.com/H3rby7/muBench-workmodel-gen) in 
   1. From a dataset ([example](https://github.com/H3rby7/cloudlab-k8s-ee-sched-data))
2. [Template](https://github.com/H3rby7/muBench-k8s-templater) [service cells](https://github.com/H3rby7/muBench-svc-cell)
3. [Run Trace CSV](https://github.com/H3rby7/muBench-csv-runner)
   1. Calls the service cells using microservice call graphs
   2. Each service cell consumes resources ([example](https://github.com/H3rby7/cloudlab-k8s-ee-sched-functions))

# Developing

Local test setup using docker-compose:

    docker-compose up -d

    docker-compose exec helm bash

    helm template /chart -f /example/my-values.yaml --output-dir /generated
