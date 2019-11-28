
#### 下载和安装

依赖的系统软件：

    yum install cmake
    yum install autoconf
    gcc-c++
    ncurses-devel.
    cmake版本要大于3.1，源代码重装了一下。

安装过程

    wget https://binaries.cockroachdb.com/cockroach-v19.2.0.src.tgz
    tar xzf cockroach-v19.2.0.src.tgz
    cd cockroach-v19.2.0
    make build
    make install

启动，参考 https://www.cockroachlabs.com/docs/stable/cockroach-start-single-node.html

安全模式的启动步骤

    cd cockroach-v19.2.0
    mkdir certs my-safe-directory
    cockroach cert create-ca --certs-dir=certs --ca-key=my-safe-directory/ca.key
    cockroach cert create-node localhost $(hostname) --certs-dir=certs --ca-key=my-safe-directory/ca.key
    cockroach cert create-client root --certs-dir=certs --ca-key=my-safe-directory/ca.key
    cockroach start \
    --certs-dir=certs \
    --store=node1 \
    --listen-addr=localhost:26257 \
    --http-addr=localhost:8080 \
    --join=localhost:26257,localhost:26258,localhost:26259 \
    --background

启动第二个cockroachdb

    cockroach start --certs-dir=certs --store=node2 --listen-addr=localhost:26258 --http-addr=localhost:8081 --join=localhost:26257,localhost:26258,localhost:26259 --background
    第三个
    cockroach start --certs-dir=certs --store=node3 --listen-addr=localhost:26259 --http-addr=localhost:8082 --join=localhost:26257,localhost:26258,localhost:26259 --background

初始化cluster

    cockroach init --certs-dir=certs --host=localhost:26257

### 使用内嵌的sql client

    cockroach sql --certs-dir=certs --host=localhost:26257
    详情参考 https://www.cockroachlabs.com/docs/stable/secure-a-cluster.html  step 3


​    
​    
官方文档

https://www.cockroachlabs.com/docs/stable/

github

https://github.com/cockroachdb/cockroach
