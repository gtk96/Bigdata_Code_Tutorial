## Q1: Flink standalone 集群报错 进而导致集群非正常宕机
2022-01-15 10:06:53,481 ERROR org.apache.flink.runtime.blob.BlobServerConnection           [] - GET operation failed for BLOB 150aa5a2e247e759f21ff93c424edd3e/p-e8b09031cd0
e01ba83667bef8a0b956dcfe18006-8d149618809ae4df5d911e989054527d from /10.176.xx.xx.
java.nio.file.NoSuchFileException: /tmp/blobStore-39487a05-032e-4605-81f8-d1e9c7d2e1ff/incoming/temp-00000134

原因： 群友：之前遇到过 我的是被运维清理工具给清理了； 你看看 可有这个文件了；一些配置 有三四个 默认都是 /tmp 下，都是 
可以自定义路径的。

临时目录被清空，导致文件无法找到。

我的解决方案：将 io 目录从临时目录改为其他目录即可。

## Q2: Flink 官方什么时候支持 oracle sql 连接器？

根据Flink 1.15 的最新快照文档，Flink JDBC 将在 1.15 支持 Flink 

https://nightlies.apache.org/flink/flink-docs-master/docs/connectors/table/jdbc/

![image](https://user-images.githubusercontent.com/34996528/149879850-b7c1164f-5505-4905-a162-b6105f945866.png)