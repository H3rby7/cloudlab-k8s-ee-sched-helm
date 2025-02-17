[See github pages](https://h3rby7.github.io/cloudlab-k8s-ee-sched-helm/)

- [Usage](#usage)
- [Developing](#developing)

# Usage

Helm chart to run with [this cloudlab profile](https://github.com/H3rby7/cloudlab-k8s-ee-sched)

      helm repo add ee-sched https://h3rby7.github.io/cloudlab-k8s-ee-sched-helm
      helm repo update
      helm install my-release ee-sched/cloud-ee-bench

Automates the following process:

1. Create a [mubench](https://github.com/mSvcBench/muBench) workmodel
   1. From a dataset ([example](https://github.com/H3rby7/cloudlab-k8s-ee-sched-data))
2. Template k8s files for [mubench](https://github.com/mSvcBench/muBench) service cells
3. Run Trace CSV
   1. Calls the service cells using microservice call graphs
   2. Each service cell consumes resources ([example](https://github.com/H3rby7/cloudlab-k8s-ee-sched-functions))

# Developing

Local test setup using docker-compose:

    docker-compose up -d

    docker-compose exec helm bash

    helm template /chart -f /example/my-values.yaml --output-dir /generated
