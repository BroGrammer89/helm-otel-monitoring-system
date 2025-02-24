# Helm OpenTelemetry Monitoring System

This project sets up a monitoring system using OpenTelemetry to collect logs from an Nginx server and send them to Coralogix and Splunk. The configuration is managed using Helm charts.

## Prerequisites

Before you begin, ensure you have the following installed and configured:

1. **Kubernetes Cluster**: A running Kubernetes cluster. You can use Minikube for local development.
2. **Helm**: Helm must be installed to manage Kubernetes applications.
3. **Container Runtime**: Docker or another container runtime must be installed and running.

## Setup Instructions

### 1. Start Minikube

Start Minikube to create a local Kubernetes cluster:

```sh
minikube start
2. Navigate to the Project Directory
Navigate to the directory where your Helm charts are located:
cd /path/to/your/project
3. Deploy the Nginx Helm Chart
Deploy the Nginx Helm chart using the provided configuration:
install nginx helm/nginx
4. Add the OpenTelemetry Helm Repository and Update It
Add the OpenTelemetry Helm repository and update it to ensure you have the latest charts:
helm repo add open-telemetry https://open-telemetry.github.io/opentelemetry-helm-charts
helm repo update
5. Apply the OpenTelemetry Collector ConfigMap
Apply the ConfigMap for the OpenTelemetry Collector configuration:
helm install my-opentelemetry-collector open-telemetry/opentelemetry-collector --set mode=deployment --set image.repository="otel/opentelemetry-collector-k8s" --set command.name="otelcol-k8s"
7. Generate Traffic to the Nginx Server
To generate logs, you need to send some traffic to the Nginx server. You can use a script or a tool like curl to generate requests.

Example using curl:
# Get the Nginx service URL
NGINX_URL=$(minikube service nginx --url)

# Send some requests to the Nginx server
for i in {1..10}; do curl $NGINX_URL; done
