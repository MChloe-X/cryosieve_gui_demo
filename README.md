# cryosieve_gui_demo
Java Swing

#### 1. 项目工具

apache-maven-3.9.4

#### 2. 项目介绍

  本项目利用Java Swing进行页面编写，实现利用纯命令或slurm脚本调用cryoSieve。

#### 4. 项目类描述

+ **CryoSieveGUIApplication.java**

  <u>CryoSieveGUIApplication</u>: 启动类，应用入口

+ **ConfigurationManager.java**

  <u>ConfigurationManager</u>: 此类用于每次启动时提前读取配置文件；根据界面获取的用户设置补全slurm脚本配置；通过此类可以调用SSHConnection中的方法进行SSH连接、命令行/slurm脚本的运行。

+ **DemoJFrame.java**

  <u>DemoJFrame</u>: 界面，包括组件和监听器

  <u>MyDialog</u>: 继承JDialog的个人弹窗组件，输入msg弹窗弹出对应消息

  <u>myJTextField</u>: 继承JTextField的个人文本框组件，目的是存入文本框名称，并添加监听器

  <u>myJComboBox</u>: 继承JComboBox的个人文本框组件，目的是存入下拉框名称

  <u>myKeyListener</u>: 继承KeyAdapter的个人监听器，实现文本框的ctrl+c/v功能

+ **SSHConnection.java**

  <u>SSHConnection</u>: 利用host port userName password进行ssh连接，项目中通过ConfigurationManager调用其功能实现，用户在配置文件中配置好ssh相关信息即可；实现命令行/slurm脚本运行。

+ **cmdGeneration.java**

  <u>cmdGeneration</u>: 接收界面传递参数生成cryoSieve对应命令行

+ **配置文件**

  <u>run.slurm</u>: 项目运行中根据界面传递的参数替换脚本中"{{NUM_GPUS}}"、"{{CMD}}"部分产生的slurm脚本（初次使用没有）

  <u>slurm_template.sh</u>: slurm脚本模板，用户运行前进行设置

  <u>ssh_config.properties</u>: 配置ssh连接信息
