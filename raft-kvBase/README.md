# KVstorageBaseRaft-cpp

## 使用方法

### 1.库准备
- muduo
- boost
- protoc
- clang-format（可选）

**安装说明**

- clang-format，如果你不设计提交pr，那么不用安装，这里也给出安装命令:`sudo apt-get install clang-format`
- protoc，本地版本为3.12.4，ubuntu22使用`sudo apt-get install protobuf-compiler libprotobuf-dev`安装默认就是这个版本
- boost，`sudo apt-get install libboost-dev libboost-test-dev libboost-all-dev`
- muduo,https://blog.csdn.net/QIANGWEIYUAN/article/details/89023980
> 如果库安装编译本仓库的时候有错误或者需要确认版本信息，可以在issue页面查看其他人遇到的问题和分享： [链接](https://github.com/youngyangyang04/KVstorageBaseRaft-cpp/issues)

### 2.编译启动
#### 使用rpc
```
mkdir cmake-build-debug
cd cmake-build-debug
cmake ..
make
```
之后在目录bin就有对应的可执行文件生成：
- consumer
- provider
运行即可，注意先运行provider，再运行consumer，原因很简单：需要先提供rpc服务，才能去调用。

#### 使用raft集群
```
mkdir cmake-build-debug
cd cmake-build-debug
cmake..
make
```
之后在目录bin就有对应的可执行文件生成，
```
// make sure you in bin directory ,and this has a test.conf file
raftCoreRun -n 3 -f test.conf
```


#### 使用kv
在启动raft集群之后启动`callerMain`即可。



