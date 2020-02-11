首先我们一个service用作消息中转以及线程开启使用

本次中，应用activity发起的默认请求消息机制代码为 1000 系列

thread完成工作后返回机制代码为91000系列

即 多一位数 9 为标志 数值为整型

后三位通
### 线程开始时就向service发送消息请求通知，随后等待service给予工作通知
请求码为1

    shareFile 发起设备请求码为 1001
    
    service 通知thread 工作码为 91001
    serivce 通知请求者shareFile弹出等待提示 码为1001
    
    随后 thread工作，完成之后返回service
    码为91001
    
    service将结果通知给请求者shareFile
    码为91001
    shareFile展示当前设备已连接数据

Android service中码分为两种



# new 不行

第一种为消息通讯码 messenger 通信码

第二种为请求通讯码 用于messenger内部的通讯识别

即采用与上不同方法，这个采用区分请求activity类的方法，上一次思路我使用的是按请求类型分类

(上一种方法可能导致我需要多种方法存储通讯实例)

shareFile 发起请求，通知service 编码为 100
    随后封装内部请求码 1001 表名本次为 获取已连接设备数据
    
    
# 文件转存

按日期建立文件夹
    按类型建立文件夹



