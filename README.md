# EasyOps Zookeeper 监控插件包

## 适用环境

~

## 工作原理

1. Zookeeper 监控插件包使用了第三方的 Zookeeper Exporter 进行指标采集，该 Exporter 的 GitHub 链接为 https://github.com/dabealu/zookeeper-exporter 。

## 使用方法

### 导入监控插件包

1. 下载该项目的压缩包 ( https://github.com/easy-monitor/zookeeper-collector-plugin/archive/master.zip )。

2. 建议解压到 EasyOps 平台服务器上的 `/data/exporter` 目录下。

3. 使用 EasyOps 平台提供的自动化工具一键导入该插件包，具体命令如下，请替换其中的 `8888` 为当前 EasyOps 平台具体的 `org`。

```sh
$ cd /usr/local/easyops/collector_plugin_service/tools
$ sh plugin_op.sh install 8888 /data/exporter/zookeeper-collector-plugin
```

4. 导入成功后访问 EasyOps 平台的「采集插件」列表页面 ( http://your-easyops-server/next/collector-plugin )，就能看到导入的 "Zookeeper_collector_plugin" 采集插件。

### 启动插件包

1. 根据现场的情况修改`supervisor/exporter-supervisor.py`的`ORG`和`CMDB_HOST`配置

2. 启动插件包
有两种方案：

    a. 手动执行：
    ```shell
    cd script
    sh deploy/start_script.sh
    ```

    b. 通过优维的部署平台执行：
    在上述导入那个步，其实就已经将插件包上传到平台的制品包，你可以在程序包管理看到该制品包，程序包的包名为：`collector_plugin-xxx`，按标准的主机部署的方式执行即可，这边不再详细描述。
