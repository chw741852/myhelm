## 启动
```shell
helm install nexus --name nexus
```

> 默认context path为"nexus" \
> 修改 \
> --set env[0].NEXUS_CONTEXT="nexus"
> --set contextPath=/ \
