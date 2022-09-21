# strimzi-kafka-demo
This repository holds the manifests for the deployment for strimzi kafka operator and kafka resources.
All the app specific manifests are held inside apps folder and is fluxcd is configured to use that dir.


## Console consumer

```
kubectl run kafka-producer -n kafka -ti --image=quay.io/strimzi/kafka:0.19.0-kafka-2.4.1 --rm=true --restart=Never -- bin/kafk
a-console-producer.sh --broker-list kafka-cluster-kafka-bootstrap:9092 --topic test-topic
```

## Console producer

```
 kubectl run kafka-consumer -n kafka -ti --image=quay.io/strimzi/kafka:0.19.0-kafka-2.4.1 --rm=true --restart=Never -- bin/kafka-console-consumer.sh --bootstrap-server kafka-cluster-kafka-bootstrap:9092 --topic test-topic --from-beginning
 ```