# Seatunnel-Spark Setup With Helm


## Configuration

By default, Seatunnel will use the configuration file in the cluster's `/mnt/data` directory. For minikube;

- Create a file named `flink-streaming-conf`

    ```shell
    touch flink-streaming-conf
    ```
    For testing you can use the content of [this file](https://github.com/apache/incubator-seatunnel/blob/dev/config/spark.streaming.conf.template).

- Create `/mnt/data` directory in minikube;

    ```shell
    minikube ssh

    sudo mkdir /mnt/data

    exit 
    ```

- Run following command to copy the configuration file into minikube cluster;

    ```shell
    minikube cp spark-streaming-conf /mnt/data/flink-streaming-conf
    ```

---
## Install

- First, install the certificate manager;

    ```shell
    kubectl create -f https://github.com/jetstack/cert-manager/releases/download/v1.7.1/cert-manager.yaml 
    ```

- While you are in the `seatunnel_helm/seatunnel_flink` directory, run the following command:

    ```shell
    helm install seatunnel-flink .
    ```

- To uninstall it:

    ```shell
    helm uninstall seatunnel-flink
    ```

---