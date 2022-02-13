
### ik插件

从github下载对应elasticsearch版本的ik插件，地址：https://github.com/medcl/elasticsearch-analysis-ik

### x-pack-core-6.2.2.jar

更新了LicenseVerifier和XPackBuild，用于破解证书认证。

由于6.2不公布x-pack源码，需要下载es源码并切换到6.3标签进行编译。

### license.json

更新证书前，使用`bin/x-pack/setup-passwords interactive`设置内置用户密码。

启动elasticsearch之后，使用如下命令更新证书。

```shell
curl -XPUT -u elastic 'http://localhost:9200/_xpack/license' -H "Content-Type: application/json" -d @license.json
```

