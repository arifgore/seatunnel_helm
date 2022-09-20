# Seatunnel-Spark Setup With Helm


## Configuration

By default, Seatunnel will use the configuration file in the cluster's `/mnt/data` directory. For minikube;

- Create a file named `spark-streaming-conf`

    ```shell
    touch spark-streaming-conf
    ```
    For testing you can use the content of [this file](https://github.com/apache/incubator-seatunnel/blob/dev/config/spark.streaming.conf.template).

- Create `/mnt/data` directory in minikube;

    ```shell
    minikube ssh

    sudo mkdir /mnt/data

    exit 
    ```

- Run following command to copy the conf file into minikube cluster;

    ```shell
    minikube cp spark-streaming-conf /mnt/data/spark-streaming-conf
    ```

---
## Install
- While you are in the `seatunnel_helm/seatunnel_spark` directory, run the following command:

    ```shell
    helm install seatunnel-spark .
    ```

- To uninstall it:

    ```shell
    helm uninstall seatunnel-spark
    ```

---