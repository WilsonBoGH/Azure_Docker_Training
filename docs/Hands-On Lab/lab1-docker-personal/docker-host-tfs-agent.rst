在Docker Host上使用Azure Storage部署Docker Registry
--------------------------------------------------------------

.. attention::
    
    文档内容将与Docker v1.12.1保持同步，请确保你所使用的Docker版本与本文档的适用范围一致，再参照本文档进行Docker的安装和配置，以防出现联系过程中系统不对称导致的问题。

在Azure docker host上安装并启动TFS Agent
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

运行如下命令登录到docker host上：

.. code-block:: text

    docker-machine ls
    docker-machine ssh {azure docker host name}
    sudo -i
    mkdir /tfsagent
    cd /tfsagent
    wget http://tfs.devopshub.cn:8080/tfs/vsts-agent-ubuntu.16.04-x64-2.105.6.tar.gz --user user1 --password P2ssw0rd
    tar zxvf vsts-agent-ubuntu.16.04-x64-2.105.6.tar.gz
    rm vsts-agent-ubuntu.16.04-x64-2.105.6.tar.gz
    ./config.sh
    ./run.sh

配置过程中输入的参数分别为：
1. 


在Azure docker host上安装并启动TFS Agent
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

运行如下命令登录到docker host上：

.. code-block:: text

    docker-machine ls
    docker-machine ssh {azure docker host name}
    sudo -i
    mkdir /tfsagent
    cd /tfsagent
    wget http://tfs.devopshub.cn:8080/tfs/vsts-agent-ubuntu.16.04-x64-2.105.6.tar.gz --user user1 --password P2ssw0rd
    tar zxvf vsts-agent-ubuntu.16.04-x64-2.105.6.tar.gz
    rm vsts-agent-ubuntu.16.04-x64-2.105.6.tar.gz
    ./config.sh
    ./run.sh

配置过程中输入的参数分别为：

    - 输入 **Y**,  同意Licens
    - server URL: http://tfs.devopshub.cn:8080/tfs
    - authentication type, 使用默认
    - 输入用户名，密码
    - agent pool: default
    - agent name: {user name}+agent, 例如 user1agent

