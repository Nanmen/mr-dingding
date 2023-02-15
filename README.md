# mr-dingding
mr-dingding
## 注意: 默认为企业机器人（只需填入openapi_key），如果想使用自定义机器人必须填写webhook和secret，开启了自定义机器人那么就不在支持企业机器人，企业机器人在钉钉后台设置了几个就支持几个，自定义机器人只支持一个
### 首先讲两点，如果你无企业、或者无法新建一个人的群，如下：
* 新建企业：[手机端钉钉] -[通讯录] -[创建加入企业/组织/团队] -[创建团队] -[选择要创建的类型并输入企业信息] - [创建] 即可。
* 新建只有一个人+机器人的群，只能在手机上新建，目前测试，电脑上不能新增一个人的群
### 支持两种机器人对接
* 自定义机器人（单发送信息到钉钉） + OUTGOING 模式（接收消息响应内容发送到钉钉） 
> * 只用在群聊里新增自定义机器人，复制webhook 以及对应的加密需要配置 webhook, secret, outgoing开启，并配置MR的路径 https://xxxxxx.com/api/plugins/dingbot/robots ,outgoing对应的token可以随便填写。
> * 然后在MR中配置webhook, secret, 以及open_api的key
> * 然后在群里问chatgpt吧
* 企业机器人
  访问钉钉开发者后台 https://open-dev.dingtalk.com/?spm=ding_open_doc.header.unLogin.openDevBtn#/ ，在顶端选择`应用开发` ——> `企业内部开发` ——> 在左侧选择`机器人`
  ![66a5b9d11d3e162ecb108f7b9992811f_](https://user-images.githubusercontent.com/15227063/218070006-62fd5cb4-5709-4c91-ac22-166bd0063d37.png)
  ![3ac5996ec9cdadbc7dfa1d9d35bb2e00_](https://user-images.githubusercontent.com/15227063/218070064-43f18caa-2d5f-4556-8d0b-1988cce93b99.png)
  选择新建机器人，在开发管理中![e056b0f8fd4f9a3baa5cdb9edd511aee_](https://user-images.githubusercontent.com/15227063/218070378-c1ba18be-3d82-4d33-a327-3d0383339d4e.png)
  配置好消息接收地址,填写`https://xxxxx.com/api/plugins/dingbot/robots`，注意替换自己的域名
  然后选择左侧的`管理与发布`，点击发布机器人
  ![image](https://user-images.githubusercontent.com/15227063/218070841-ded69522-0fb7-413b-9985-25a094964662.png)
  最后在MR里只需要配置open_api的key, 其他参数留白，其他参数填了就是自定义机器人了！！！！
  最后的最后，在群聊里添加企业机器人吧，开启对话吧

### 新增
1. 增加钉钉chatgpt 上下文关联，如要清空上下文关联，输入`#清除记忆`
2. 增加钉钉chatgpt 画图模式，要画图，请用 `画+描述` 使用
3. 目前上下文关联设置的1000字符，如有需要可以自己改代码- -，或者后续开放配置
