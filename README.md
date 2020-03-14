# Kubernetes Apache Spark
 Deploy Apache Spark in Kubernetes

## Install

Change configuration in `helm-values.yml` and :

```
helm install spark -f helm-values.yaml bitnami/spark
```

Read more about helm values [here](https://github.com/bitnami/charts/tree/master/bitnami/spark)

## WebUI

* You should enable `ingress` to access Spark from a web browser
* Set hostname in `ingres` section. Default is https://spark.local

## Scaling

In `worker` section you can set scaling policy and limits. That will enable replica autoscaling depending on CPU

```yaml
resources:
    limits: 
       cpu: 100m
       memory: 150Mi

autoscaling:
    enabled: true
    CpuTargetPercentage: 50
    replicasMax: 10
```
