# Autoclaw一键安装小龙虾🦞

> 手把手教你部署 Autoclaw（智谱一键安装版 OpenClaw），从下载安装到飞书机器人接入，全流程图文保姆级教程，小白也能轻松上手！
>
> **发布日期**：2026年3月13日 | **平台**：微信公众号 | **标签**：`AI` `工具` `教程`
>
> 🔗 [微信公众号](https://mp.weixin.qq.com/s/zZdIA6cWa02YWTO71a6t2w?scene=1) 

龙虾千千万，虾脑最关键！🦞

![ai-generated-image.png](images/ai-generated-image.png)

最近测试了多种 OpenClaw 的部署方式，从原汁原味的 OpenClaw 到国内各大厂家的适配版本，不得不说，**国内厂家推出的一键安装包**才是真正让普通用户也能轻松上手的关键。

今天就以 **Autoclaw（智谱版）** 为例，带大家从零开始完成部署，并打通飞书机器人。没办法～一开就是 Coding Plan Max 一年的套餐 😎

另外顺便推荐一下智谱的 [AutoTyper 语音输入法](https://autoglm.zhipuai.cn/autotyper)，日常搭配使用非常方便，语音输入效率拉满！

---

## 一、下载安装

前往 Autoclaw 官网下载安装包：[https://autoglm.zhipuai.cn/autoclaw/](https://autoglm.zhipuai.cn/autoclaw/)

[AutoClaw（澳龙）- OpenClaw一键安装 | 飞书集成 | AI助手下载](https://autoglm.zhipuai.cn/autoclaw/)

![image.png](images/image.png)

![image.png](images/image-1.png)

> 💡 **Mac 用户安装提示**：如果提示无法打开，需要先允许"任何来源"的应用程序。

**操作步骤：**

1. 打开 **系统设置** → **隐私与安全性** → 下滑找到「安全性」→ 选择 **任何来源**

![image.png](images/image-2.png)

1. 如果没有「任何来源」选项，按 `Command + 空格` 搜索并打开 **终端**

![image.png](images/image-3.png)

输入以下命令（输入密码时不会显示），回车后重新打开隐私设置即可看到「任何来源」

```bash
sudo spctl --master-disable
```

---

## 二、登录账号

点击 Autoclaw 应用图标，首次启动会弹出登录界面。

![image.png](images/image-4.png)

![image.png](images/image-5.png)

> 📦 如果之前部署过 OpenClaw，会自动进入迁移流程，数据无缝衔接。

![image.png](images/image-6.png)

登录成功后的主界面：

![image.png](images/image-7.png)

---

## 三、基础设置

主界面可以分为 **五个功能分区**，拿到手后先别急着用，花几分钟了解一下各区域功能。

![image.png](images/image-8.png)

### 🔧 用户信息与设置

点击用户设置按钮进入设置面板：

![image.png](images/image-9.png)

![image.png](images/image-10.png)

这里重点介绍两个关键设置：

### 📌 1. 模型与 API

如果你额外购买了 Coding Plan 套餐，可以在这里 **添加自定义模型**。一般购买的套餐都有对应的接口文档，按文档接入即可。

![image.png](images/image-11.png)

![image.png](images/image-12.png)

### 📌 2. IM 频道（重点！）

这是 Autoclaw 的核心功能之一——可以接入 **飞书** 等社交平台（目前智谱版仅支持飞书，后续会开放更多平台）。

![image.png](images/image-13.png)

> 📖 想深入了解更多功能？可以参考 OpenClaw 官方文档：[https://docs.openclaw.ai/zh-CN](https://docs.openclaw.ai/zh-CN)

[OpenClaw - OpenClaw](https://docs.openclaw.ai/zh-CN)

![image.png](images/image-14.png)

---

## 四、打通飞书机器人

接下来是重头戏——将 Autoclaw 接入飞书，实现在飞书内直接与 AI 对话。

### Step 1：创建飞书应用

打开飞书开放平台：[https://open.feishu.cn/app](https://open.feishu.cn/app)

[Developer Console - Feishu Open Platform](https://open.feishu.cn/app)

1. 点击 **创建企业自建应用**
2. 填写应用名称、描述，选择图标

![image.png](images/image-15.png)

![image.png](images/image-16.png)

创建完成后进入应用管理界面：

![image.png](images/image-17.png)

### Step 2：获取应用凭证

在 **凭证与基础信息** 页面，复制以下两项：

- **App ID**（格式如 `cli_xxx`）
- **App Secret**

> ⚠️ **重要**：请妥善保管 App Secret，切勿分享给他人！

![image.png](images/image-18.png)

回到 Autoclaw → **设置** → **IM 频道** → 点击「添加频道」→ 选择「飞书」→ 填入 App ID 和 App Secret → 点击添加

![image.png](images/image-19.png)

![image.png](images/image-20.png)

![image.png](images/image-21.png)

![image.png](images/image-22.png)

### Step 3：添加机器人能力

回到飞书开放平台：[https://open.feishu.cn/app](https://open.feishu.cn/app)

[Developer Console - Feishu Open Platform](https://open.feishu.cn/app)

选择 **添加应用能力** → **机器人** → 添加即可

![image.png](images/image-23.png)

### Step 4：配置应用权限

在 **权限管理** 页面 → 点击 **批量导入** → 粘贴以下 JSON 配置 → 点击「下一步，确认新增权限」→ 申请开通

![image.png](images/image-24.png)

![image.png](images/image-25.png)

**权限配置 JSON（直接复制粘贴）：**

```json
{
  "scopes": {
    "tenant": [
      "aily:file:read",
      "aily:file:write",
      "application:application.app_message_stats.overview:readonly",
      "application:application:self_manage",
      "application:bot.menu:write",
      "cardkit:card:write",
      "contact:user.employee_id:readonly",
      "corehr:file:download",
      "docs:document.content:read",
      "event:ip_list",
      "im:chat",
      "im:chat.access_event.bot_p2p_chat:read",
      "im:chat.members:bot_access",
      "im:message",
      "im:message.group_at_msg:readonly",
      "im:message.group_msg",
      "im:message.p2p_msg:readonly",
      "im:message:readonly",
      "im:message:send_as_bot",
      "im:resource",
      "sheets:spreadsheet",
      "wiki:wiki:readonly"
    ],
    "user": ["aily:file:read", "aily:file:write", "im:chat.access_event.bot_p2p_chat:read"]
  }
}
```

![image.png](images/image-26.png)

![image.png](images/image-27.png)

![image.png](images/image-28.png)

### Step 5：事件与回调

1. 选择 **使用长连接接收事件**（WebSocket 模式）
2. 添加事件：`im.message.receive_v1`（接收消息）

![image.png](images/image-29.png)

![image.png](images/image-30.png)

搜索 `im.message.receive_v1` → 勾选 → 点击「添加」

![image.png](images/image-31.png)

![image.png](images/image-32.png)

### Step 6：版本管理与发布

选择 **版本管理与发布** → **创建版本** → 填写版本信息 → **保存** → **确认发布**

![image.png](images/image-33.png)

![image.png](images/image-34.png)

![image.png](images/image-35.png)

### Step 7：验证连接

回到手机端飞书 → 找到「开发者小助手」→ 点击「打开应用」→ 发送消息

![image.png](images/image-36.png)

发送消息后会收到回复，同时 Autoclaw 的 IM 频道内也会同步显示 ✅

![9efce8969613e1f565f28df605cc27c7.jpg](images/9efce8969613e1f565f28df605cc27c7.jpg)

![image.png](images/image-37.png)

---

## 五、管理飞书应用

> 💡 如果在飞书开放平台的「凭证与基础信息」内无法删除应用，可以通过管理后台操作。

[Feishu Open Platform](https://open.feishu.cn/app/cli_a939cd012d39dcc5/baseinfo)

![image.png](images/image-38.png)

打开飞书管理后台：[https://yxi5ywpk6ex.feishu.cn/admin/appCenter/manage](https://yxi5ywpk6ex.feishu.cn/admin/appCenter/manage)

[](https://yxi5ywpk6ex.feishu.cn/admin/appCenter/manage)

![image.png](images/image-39.png)

![image.png](images/image-40.png)

在管理后台关闭应用后，即可在开发者平台内删除。

[Feishu Open Platform](https://open.feishu.cn/app/cli_a939cd012d39dcc5/baseinfo)

![image.png](images/image-41.png)

---

## 六、日常使用

Autoclaw 默认已经创建了 **4 只「小龙虾🦞」**，并提供了预设模板，开箱即用！

你可以：

- 在对应的对话窗口与 AI 「唠嗑」
- 随时创建新的龙虾🦞
- 为每只龙虾自定义名称和用途

![image.png](images/image-42.png)

![image.png](images/image-43.png)

### 🔒 安全性设置

在 **设置** → **工作区** 中：

- 建议将默认项目目录更换为自定目录
- 根据需求决定是否开启「限制文件访问范围」

![image.png](images/image-44.png)
