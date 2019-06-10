---
环信服务端python SDK
---

#### 目前仅开发获取聊天记录文件下载并入库，后续功能敬请期待
程序开始执行后，第一次会获取直到程序运行前的2小时的聊天记录

#### 使用方法
1. 复制config.example.conf文件重命名为config.conf
2. 修改配置文件
```
[huanxin]
app_key =
client_id =
client_secret =
default_rest = http://a1.easemob.com
token =
last_get_time = 00000000
last_message_time = 2017082802

[db]
db_host = 127.0.0.1
db_user = root
db_password = root
db_database = root
db_table = root

```
其中last_get_time（上次获取时间）和token（管理员token）可保持为空，last_message_time（消息记录获取到的时间）格式为10位时间戳，设置为你想从哪个时间点开始获取，程序会自动获取那个时间点到程序运行前的2小时的聊天记录

3. 安装好必要的库，执行start.py

#### 建议把脚本配置到定时任务中，每小时执行一次，即可持久获取聊天记录
#### 注意：环信聊天的聊天记录只保持3天，所以last_message_time请设置当前的时间3天以内， 不然程序会报错
