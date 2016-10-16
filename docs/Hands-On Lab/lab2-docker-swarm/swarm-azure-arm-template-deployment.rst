使用Azure资源管理器部署Docker Swarm集群
------------------------------------

什么Azure资源管理器
====================

应用程序的体系结构通常由许多组件构成 – 其中可能包括虚拟机、存储帐户、虚拟网络、Web 应用、数据库、数据库服务器和第三方服务。这些组件不会以独立的实体出现，而是以单个实体的相关部件和依赖部件出现。如果你希望以组的方式部署、管理和监视这些这些组件，那么，你可以使用 Azure 资源管理器以组的方式处理解决方案中的资源。你可以通过一个协调的操作为解决方案部署、更新或删除所有资源。你可以使用一个模板来完成部署，该模板适用于不同的环境，例如测试、过渡和生产。资源管理器提供安全、审核和标记功能，以帮助你在部署后管理资源。

更多信息请参考： `Azure资源管理器概述 <https://www.azure.cn/documentation/articles/resource-group-overview/>`_

Docker Swarm 集群架构
=======================

Docker Swarm Azure 资源管理器模板
================================

借助Azure资源管理器模板，我们可以很容易的在Azure中部署Docker Swarm集群环境。请从以下地址访问我们的模板

`Docker Swarm Azure资源管理器模板github地址 <https://github.com/ups216/DockerSwarm>`_

.. figure:: images/lab02-swarm-arm-github-page.png

部署步骤：

1. 点击此页面中的 Deploy To Azure 按钮，

.. figure:: images/lab02-swarm-deploy-to-azure-button.png

即可启动部署模版。

2. 配置模版参数

点击以上 Deploy to Azure 按钮并使用你的Azure账号登陆系统后，可以看到一下模版配置页面

.. figure:: images/lab02-Configure-Arm-template.png

这里，需要我们输入或者配置一下几个参数

================    ===========
    参数              值
================    ===========
SSHPUBLICKEY         用来管理Swarm集群的ssh公钥
MASTERCOUNT          Swarm集群中管理节点的数量，默认为 1
NODECOUNT            Swarm集群中工作节点的数量，默认为 2
================    ===========

.. attention::
    
    以上我们限制使用了1个管理节点和2个工作节点，这样做时是为了配合试验环境所使用的Azure试用账号的一些限制。实际生产环境中请根据需要配置。
    一般来说，管理节点应为单数并至少是3个，工作节点则可以根据需要配置。

ssh密钥可以使用ssh-keygen这个工具来生成，如果你之前已经在使用ssh密钥来管理服务器请跳过一下生成密钥的步骤。

打开命令行工具，并输入

ssh-keygen -C {emailAddress}











