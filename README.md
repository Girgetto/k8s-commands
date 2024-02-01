# Advanced Kubernetes Commands for CKAD Exam

Expand your `kubectl` toolkit with these commands, tailored for tasks and challenges you might face during the CKAD exam.

## Working with Specific Namespaces

- `kubectl get pods --namespace <name>`: List all pods in a specific namespace.  
  _Targets operations in a given namespace._

- `kubectl config set-context --current --namespace=<name>`: Set the default namespace for subsequent commands in the current context.  
  _Streamlines command execution in a specific namespace._

## Resource Inspection and Troubleshooting

- `kubectl describe nodes <node-name>`: Show details of a specific node, including allocated resources, labels, and status conditions.  
  _Essential for node-level troubleshooting._

- `kubectl get pod <pod-name> -o yaml`: Output the configuration of the specified pod in YAML format.  
  _Useful for debugging and understanding pod configurations._

- `kubectl top pod <pod-name>`: Display CPU and memory usage for a specific pod.  
  _Helps identify resource bottlenecks._

## Resource Management and Scaling

- `kubectl scale deployment <deployment-name> --replicas=<num>`: Scale a deployment to a specific number of replicas.  
  _Quickly adjust the scale of applications._

- `kubectl autoscale deployment <deployment-name> --min=<min> --max=<max> --cpu-percent=<target>`: Automatically scale a deployment based on CPU usage.  
  _Implements automatic scaling based on load._

## Updating and Rolling Back Deployments

- `kubectl set image deployment/<deployment-name> <container-name>=<image>:<tag>`: Update the image of a deployment.  
  _Triggers a rolling update of pods._

- `kubectl rollout status deployment/<deployment-name>`: Watch the progress of a rolling update.  
  _Ensures updates proceed as expected._

- `kubectl rollout undo deployment/<deployment-name>`: Rollback to the previous deployment.  
  _Quick recovery from faulty deployments._

## ConfigMaps and Secrets

- `kubectl create configmap <map-name> --from-literal=key=value`: Create a ConfigMap from literal values.  
  _For externalizing configuration._

- `kubectl create secret generic <secret-name> --from-file=path/to/bar`: Create a secret from a file.  
  _Securely manages sensitive information._

## Working with Persistent Data

- `kubectl get pv`: List all PersistentVolumes in the cluster.  
  _Overview of storage resources._

- `kubectl get pvc`: List all PersistentVolumeClaims in the current namespace.  
  _Tracks storage claims by pods._

## Advanced Resource Queries

- `kubectl get pods --selector=app=cassandra`: List all pods that match a specific label selector.  
  _Filters resources based on labels._

- `kubectl explain pods`: Get the documentation of the Pod resource.  
  _Deepens understanding of resource specifications._

## Using Labels and Annotations

- `kubectl label pods <pod-name> key=value`: Add a new label to a pod.  
  _For organizing and selecting subsets of resources._

- `kubectl annotate pods <pod-name> key=value`: Add an annotation to a pod.  
  _Stores additional, non-identifying information on resources._

This expanded set of commands is designed to cover a wide range of tasks and challenges you may encounter during the CKAD exam, from basic resource management to more complex operations and troubleshooting.
