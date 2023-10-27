# -Qt-ARM-
基于 Qt和ARM主控开发板的 具有C/S架构的应用程序
该程序有两个主要程序客户端和服务器端
客户端可以运行在ARM开发板上；
运行环境为：Qt Creator 4.8.0
野火i.MX6ULL S1 eMMCPro开发板
野火5寸电容RGB液晶屏800x480；
LED灯为三色可编程LED灯
温湿度传感器为DHT11
ARM芯片为：MCIMX6Y2CVM08ABCortex A7 800MHz（实际为 792MHZ）
项目结构如下
![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/b38615b3-123c-499b-a34d-19f3de04b5a8)
项目设计：
基于QT开发板的家庭控制系统由三大部分组成，包括上位机、下位机和数据库。这个系统旨在提供家庭自动化控制和数据管理。下面对这三部分进行详细说明：

1. 下位机：
- 下位机包含六个不同的应用界面，分别是登录界面、注册界面、主界面（应用界面）、家电控制界面、音乐播放器界面和温湿度显示界面。
- 登录界面用于用户身份验证，注册界面允许新用户创建账户，其中包含检查用户名是否已存在和验证密码是否匹配的功能。
- 主界面是整个系统的核心，其中包括导航按钮，允许用户访问其他应用界面。
- 家电控制界面允许用户远程控制三个LED灯的状态，并将状态信息发送到服务器进行保存。
- 音乐播放器界面允许用户播放和暂停音乐。
- 温湿度显示界面可采集温度和湿度数据，并将其发送到服务器端进行存储。

2. 上位机：
- 上位机是PC端的用户界面，用于接收、处理和显示从下位机通过网络传输的数据信息。
- 它还负责将反馈信息发送回下位机，以提供用户友好的界面来与家庭设备进行互动。

3. 数据库：
- 使用本地数据库管理数据，主要包括三个表：用户信息表、家电状态记录表和温湿度记录表。
- 用户信息表用于存储用户的注册信息，包括用户名和密码。
- 家电状态记录表用于记录家电设备的状态，例如LED灯的开关状态。
- 温湿度记录表用于存储采集到的温度和湿度数据，以供后续分析和查看。

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/66a44b77-2df7-47ae-b5b6-a8c995e589a7)

  
客户端工程中的build-QtKeyboard-ebf_lubancat-Debug文件中有ARM芯片可用的程序可执行文件

以下图片为功能展示
程序运行初始界面也是登录界面

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/176ed4d6-0efc-45a0-87dc-7b570de02ee4)

注册界面

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/28ca4657-194d-4438-8fea-ebb2cf4d28c5)

登录成功跳转到主界面

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/7717fba8-56bf-4b9d-b0a6-fc9b743a5237)

LED界面功能

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/95c148cc-eaa9-4c88-8de7-ef6d8b706fbf)

音乐播放器界面

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/31d8b6e5-ad18-4672-9291-f454f63ccbcb)

温湿度检测界面

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/73978a92-182d-4407-ac4e-1f087017bdfd)

虚拟键盘输入界面

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/0eca3df7-7714-47f0-9d4c-18b55abd5eda)

用户表

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/5635702b-9cc1-4e1a-bfbf-9ffb7c4c206e)

家电状态模拟表

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/31682ba2-1f51-4f35-ae95-f9418127ce5f)

温湿度表

![image](https://github.com/MCC12345/-Qt-ARM-/assets/104244230/04504f50-6e77-408e-b000-969457874b55)


实际使用时如果客户端和服务器端都运行在本地的PC端上请修改为正确的ip和端口确认通信没有问题 如果客户端运行在ARM开发板上服务器端运行在PC端上 请确保两个设备处于同意网段 修改ip地址为实际地址 确认服务器端是否正确连接数据库。
