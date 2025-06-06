!> 注意：本文信息可能会过时，仅供参考，请以服务商最新官方文档为准。本文发布日期：2020 年 5 月 2 日。

?> 官方文档：https://cloud.tencent.com/product/tmt/getting-started

?> 由于图片翻译 API 也会进行文字识别，所以可以用作文字识别接口

## 0. 收费模式

[查看详情](https://cloud.tencent.com/product/tmt/pricing)

| 服务 | 免费额度 | 超出免费额度 | 并发请求数 |
| :-- | :-- | :-- | :-- |
| 图片翻译（开通免费试用） | 每月10000次 👍 | 直接禁止使用，不会扣费 | 1次/秒 |
| 图片翻译（开通付费版） | 每月10000次 👍 | 0.045元/次 | 1次/秒 |

## 1. 注册登录

[点击此处跳转网页](https://cloud.tencent.com/)

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_login.png" alt="tencent_translate_login" width=1000 />

## 2. 个人认证

!> 腾讯云免费服务使用之前需要认证，普通用户申请「个人认证」即可，如果已经认证，请直接跳过此步骤

 进入 [「账号信息-查看或修改认证」](https://console.cloud.tencent.com/developer/auth)，点击「开始个人认证」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_auth_1.png" alt="tencent_translate_auth_1" width=1000 />

以下信息如实填写，然后点击「下一步」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_auth_2.png" alt="tencent_translate_auth_2" width=1000 />

如下提示即代表认证成功

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_auth_3.png" alt="tencent_translate_auth_3" width=1000 />

## 3. 开通机器翻译

?> 如果进入机器翻译页面能直接看到运营数据，证明已开通，请直接跳过此步骤

进入 [「机器翻译」](https://console.cloud.tencent.com/tmt) 页面

如果只是想使用免费额度，直接点击「免费试用」（每月免费额度使用完之后将直接无法使用，不会扣费）

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_open_1.png" alt="tencent_translate_open_1" width=1000 />

如下提示即代表开通成功

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_open_2.png" alt="tencent_translate_open_2" width=1000 />

## 4. 获取秘钥

!> 请妥善保管自己的秘钥，秘钥泄露可能会给你带来损失！

获取秘钥有两个方法，方法1更快捷，方法2更安全，**任选一个跟着操作就可以了**。

!> 注意，无论使用哪个方式获取秘钥，前面的步骤（个人认证、开通机器翻译）都是需要操作的。如果不操作，即便获取到了秘钥也无法正常使用！

### 方法1（更快捷）

如果想更快捷地获取秘钥，可以直接获取「主账号」的秘钥，**该秘钥可以直接访问你账户下的所有腾讯云资源**。

进入 [「访问管理-访问秘钥-API秘钥管理」](https://console.cloud.tencent.com/cam/capi)，点击「新建秘钥」

?> 如果已有秘钥，可直接使用，无需再新建

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_secret_1_1.png" alt="tencent_translate_secret_1_1" width=1000 />

如下图所示即所需的秘钥

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_secret_1_2.png" alt="tencent_translate_secret_1_2" width=1000 />

### 方法2（更安全）

如果想要更安全一些，可以创建一个「子用户」，然后只给这个「子用户」开启访问「机器翻译」API的权限

!> 如果之前为腾讯的其他服务创建过「子用户」，**也请创建一个新的「子用户」**，每个服务对应的权限可能不同，只有权限对应上了才能正常使用。

进入 [「访问管理-用户-用户列表」](https://console.cloud.tencent.com/cam)，点击「新建用户」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_user_1.png" alt="tencent_translate_user_1" width=1000 />

点击「自定义创建」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_user_2.png" alt="tencent_translate_user_2" width=1000 />

选择「可访问资源并接受消息」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_user_3.png" alt="tencent_translate_user_3" width=1000 />

用户名随意设置，勾选上「编程访问」，其他的不用勾选，然后点击「下一步」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_user_4.png" alt="tencent_translate_user_4" width=1000 />

在搜索框输入「tmt」即可快速找到「机器翻译」相关服务，然后勾选上「**QcloudTMTFullAccess**」，点击「下一步」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_user_5.png" alt="tencent_translate_user_5" width=1000 />

点击「完成」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_user_6.png" alt="tencent_translate_user_6" width=1000 />

如下图所示即为所需秘钥

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_user_7.png" alt="tencent_translate_user_7" width=1000 />

如果已经创建完「子用户」，想重新查看秘钥，则进入 [「访问管理-用户-用户列表」](https://console.cloud.tencent.com/cam)，展开对应子用户，然后点击「查看用户详情」

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_secret_2_1.png" alt="tencent_translate_secret_2_1" width=1000 />

点击「API 秘钥」，下图所示即可所需秘钥

<img src="https://cdn.jsdelivr.net/gh/ripperhe/oss@master/2020/0501/tencent_translate_secret_2_2.png" alt="tencent_translate_secret_2_2" width=1000 />

## 5. 填写秘钥

在 Bob 的 偏好设置 > 服务 中，选中「文本识别」，点击 `+` 号，选中「腾讯云图片翻译」，然后将刚才获取到的秘钥填写到对应位置即可。

详细使用方法可查看 [服务](general/quickstart/service) 页面。