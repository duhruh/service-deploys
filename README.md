# service-deploys
Definitions of services for various environments

## What is this?

It's the repository containing definitions and manifests for services/containers/stacks/etc for various environments. [Bosun](https://github.com/docker-infra/universe/tree/master/bosun) consumes this repository.

## Organization

Each top-level directory is an environment, and within each of those directories are several other directories, pertaining to the orchestrator that the manifest pertains to. For example, the production environment looks like this:
```
us-east-1
  |- kubernetes
    |- _dns.yaml
    |- airboss.yaml
  |- swarm
    |- infra-haproxy-test-routing.yaml
```

The `us-east-1/kubernetes` are kubernetes manifests that will be deployed via `kubectl apply -f -r us-east-1/kubernetes`. The `us-east-1/swarm` directory are for Swarm stacks which are deployed via `docker stack deploy -f <stack_name>.yaml <stack_name>`. 


More information can be found in the [Bosun README.md](https://github.com/docker-infra/universe/tree/master/bosun).
