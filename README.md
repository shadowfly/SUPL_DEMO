# 基于bcos平台搭建供应链
## 项目背景介绍

在我们做的供应链系统中,有上游,核心企业,下游和工厂四种角色,核心企业向上游购买原料,然后把原料销售给下游,下游再将原料销售给工厂,工厂将原料进行加工,生产成产品,将产品销售给下游,下游再将产品销售给核心企业.

## 项目架构介绍

首先我们在云服务器上搭建bcos区块链环境,部署智能合约,然后在本地搭建java web后端环境,在web后端通过web3sdk接口来操作bcos区块链,后端再和前端界面交互.

## 功能展示

首先是注册环节,在这里机构可以选择机构类型,输入帐号密码,再次输入密码确认,点击注册就会在区块链和数据库中创建机构,密码属性经过sha256加密后保存在数据库而非区块链中,这样登录的时候只要在数据库中进行查询即可,一定程度上加快访问速度,提升用户体验.注册完之后就跳转到登录界面,用户使用帐号密码和对应的机构类型进行登录,登录成功后会跳转到主界面,在主界面我们可以看到我们提供了修改白条额度,录入交易信息,查看所有的白条列表,同时可以对白条进行回收,查看所有的交易列表,同时对与自己相关的交易进行修改状态,除此以外,我们还提供了合同下载功能和合同验伪功能.合同下载是指将在创建交易时上传到服务器上的合同下载下来,合同验伪是指上传一份本地的合同,将它与区块链中的指定的合同号的合同哈希进行比较,返回比较结果.

## 个人工作

我负责在本地使用虚拟机搭建bcos,然后部署到云服务器上,然后编译导出web3sdk.jar包,将web3sdk.jar包导入后端java web,将智能合约编译成Supl.java文件,在serviceImpl层调用Supl.java里的函数操作区块链.除此以外,我还负责后端service层和dao层代码的编写,mapper数据库语句的实现,数据库的建表,初始化数据
