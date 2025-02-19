
## Prerequisites

Before you begin, ensure you have the following installed:

- [Kubernetes](https://kubernetes.io/docs/setup/)
- [Helm](https://helm.sh/docs/intro/install/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Installation

1. **Clone the repository**:

    ```sh
    git clone https://github.com/BroGrammer89/helm-otel-monitoring-system.git
    cd helm-otel-monitoring-system
    ```

2. **Navigate to the Helm chart directory**:

    ```sh
    cd helm/nginx
    ```

3. **Deploy Nginx**:

    ```sh
    helm install nginx .
    ```

4. **Navigate to the OpenTelemetry Collector directory**:

    ```sh
    cd ../opentelemetry-collector
    ```

5. **Deploy OpenTelemetry Collector**:

    ```sh
    helm install opentelemetry-collector .
    ```

6. **Navigate to the Splunk directory**:

    ```sh
    cd ../splunk
    ```

7. **Deploy Splunk**:

    ```sh
    helm install splunk .
    ```

8. **Navigate to the ELK directory**:

    ```sh
    cd ../elk
    ```

9. **Deploy ELK Stack**:

    ```sh
    helm install elk .
    ```

## Usage

Once the Helm charts are deployed, you can access the services as follows:

- **Nginx**: Access the Nginx service using the Kubernetes service URL.
- **OpenTelemetry Collector**: The OpenTelemetry Collector will start collecting and exporting logs.
- **Splunk**: Access the Splunk web interface using the Kubernetes service URL.
- **ELK Stack**: Access Kibana using the Kubernetes service URL to visualize logs collected by Elasticsearch and Logstash.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
