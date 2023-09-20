# ReplicaSet

Có 2 loại Replica là: Replication Controller và ReplicaSet với **ReplicaSet là phiên bản thay thế cho Replication Controller**. 

## 1. Replication Controller

![Replication Controller](/1-introduction-to-k8s.md/images/4-1-replication-controller.png)

**Chú ý** rằng với ReplicationController thì appVersion phải là v1. Khác với ReplicaSet là app/v1

## 2. ReplicaSet
![ReplicaSet](/1-introduction-to-k8s.md/images/4-2-replicaset.png)
Với ReplicaSet thì bắt buộc phải có trường **replicas** và **selector**.

## 3. Scale
![Scale](/1-introduction-to-k8s.md/images/5-scale.png)