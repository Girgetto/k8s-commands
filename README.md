# Helpful Kubernetes Commands

This document lists some of the most commonly used `kubectl` commands along with a brief description of their purpose in managing Kubernetes resources.

## Cluster Management

- `kubectl get nodes`: List all nodes in the cluster.  
  _Shows the status of each node._

- `kubectl cluster-info`: Display cluster info.  
  _Provides high-level information about the cluster._

## Working with Namespaces

- `kubectl get namespaces`: List all namespaces in the cluster.  
  _Helps with organizing resources._

- `kubectl create namespace <name>`: Create a new namespace.  
  _Useful for separating environments._

## Deploying Applications

- `kubectl create -f <filename>`: Create a resource from a YAML or JSON file.  
  _For deploying applications or other resources._

- `kubectl apply -f <filename>`: Apply a configuration to a resource from a file.  
  _Ideal for updating applications or configurations._

## Monitoring and Troubleshooting

- `kubectl get pods`: List all pods in the current namespace.  
  _Shows the status of each pod._

- `kubectl logs <pod-name>`: Print the logs for a container in a pod.  
  _Useful for troubleshooting applications._

- `kubectl describe pod <pod-name>`: Show detailed information about a pod.  
  _Provides insights into pod status, events, and more._

## Managing Resources

- `kubectl get all`: List all resources in the current namespace.  
  _Gives an overview of what's running._

- `kubectl delete -f <filename>`: Delete resources specified in a YAML or JSON file.  
  _For cleaning up applications or resources._

## Interacting with Running Pods

- `kubectl exec -it <pod-name> -- /bin/bash`: Execute an interactive bash shell in the specified pod.  
  _Allows for direct interaction with a running container._

- `kubectl port-forward <pod-name> <local-port>:<pod-port>`: Forward one or more local ports to a pod.  
  _Useful for debugging or directly accessing pod services._

## Configuration and Secrets

- `kubectl create secret generic <secret-name> --from-literal=key=value`: Create a new secret.  
  _For storing and managing sensitive information._

- `kubectl get configmap`: List all configmaps in the current namespace.  
  _For configuration management._

## Role-Based Access Control (RBAC)

- `kubectl create role <role-name> --verb=get,list,watch --resource=pods`: Create a role with specific permissions.  
  _For defining access control._

- `kubectl create rolebinding <name> --role=<role-name> --user=<user-name>`: Bind a role to a user.  
  _Applies the access control defined in a role to a user or set of users._

This guide offers a starting point for managing Kubernetes resources and applications. For more detailed information, refer to the official Kubernetes documentation.
