# Kubernetes Commands

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

## Exposing Services

Exposing your application in Kubernetes can be done using various types of Services. Here are commands related to creating and managing Services to expose your applications.

### Creating a Service

- `kubectl expose pod <pod-name> --port=<port> --name=<service-name>`: Create a Service to expose a pod on a specific port.
  _Exposes a single pod._

- `kubectl expose deployment <deployment-name> --type=NodePort --port=<port>`: Expose a deployment as a Service accessible outside the cluster.
  _Creates a NodePort Service for broader access._

### Inspecting Services

- `kubectl get services`: List all Services in the current namespace.
  _Shows all services and their types._

- `kubectl describe service <service-name>`: Show detailed information about a Service.
  _Provides endpoint, selector, and port details._

## Managing Labels

Labels are key-value pairs attached to objects, such as Pods and Deployments, which are used for organizing and selecting subsets of objects.

### Adding Labels to Objects

- `kubectl label pods <pod-name> key=value`: Add a new label to a Pod.
  _Helps in categorizing and selecting pods for operations._

- `kubectl label deployment <deployment-name> key=value`: Add a label to a Deployment.
  _Useful for tracking versions or environments._

### Modifying Labels

- `kubectl label pods <pod-name> key=value --overwrite`: Update an existing label on a Pod.
  _Adjusts categorization or selection criteria._

### Filtering Resources by Labels

- `kubectl get pods --selector=key=value`: List all Pods that match the given label selector.
  _Enables targeted operations on a subset of resources._

- `kubectl get all --selector=app=frontend`: List all resources labeled as `app=frontend`.
  _Useful for comprehensive operations across resource types._

### Removing Labels

- `kubectl label pods <pod-name> key-`: Remove a label from a Pod.
  _Cleans up or adjusts resource categorization._

- `kubectl annotate pods <pod-name> key=value`: Add an annotation to a pod.  
  _Stores additional, non-identifying information on resources._

This expanded set of commands is designed to cover a wide range of tasks and challenges you may encounter during the CKAD exam, from basic resource management to more complex operations and troubleshooting.
