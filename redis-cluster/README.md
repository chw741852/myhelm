# redis cluster helm
仅支持redis 5

### 启动
```shell
helm install redis-cluster \
 --name myredis \ 
 --set replicaCount=6 \
 --set persistence.storage=500Mi \
 --set password=password
```

### 创建cluster
```shell
# 进入其中一个redis容器
kubectl exec -it myredis-redis-cluster-0 /bin/bash
redis-cli --cluster create \ 
`dig redis-redis-cluster-0.redis-redis-cluster.default.svc.cluster.local`:6379 \
`dig redis-redis-cluster-1.redis-redis-cluster.default.svc.cluster.local`:6379 \
`dig redis-redis-cluster-2.redis-redis-cluster.default.svc.cluster.local`:6379 \
`dig redis-redis-cluster-3.redis-redis-cluster.default.svc.cluster.local`:6379 \
`dig redis-redis-cluster-4.redis-redis-cluster.default.svc.cluster.local`:6379 \
`dig redis-redis-cluster-5.redis-redis-cluster.default.svc.cluster.local`:6379 \
--cluster-replicas 1 -a password
```
