## 启动
```shell
helm install nexus --name nexus
```

## 创建PV
> 这里需要手动创建pv \
且PV的文件夹需要授权chown -R 200 /mypv

> 默认context path为"nexus" \
> 修改 \
> --set env[0].NEXUS_CONTEXT="nexus"
> --set contextPath=/ \
