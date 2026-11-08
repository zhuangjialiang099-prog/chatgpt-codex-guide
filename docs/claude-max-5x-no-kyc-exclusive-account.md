测试# Claude Max 5x免KYC独享成品号使用教程

先检查电脑里是否留有旧的中转 API 配置，再确认网络可访问 Claude，使用官方安装器装好 Claude Code，最后在系统终端发起授权。已经安装的人可先运行 `claude --version` 检查版本，再按需要进入对应步骤。

## 适用订单与使用范围

本教程适用于 GPT-DUO Claude Max 5x 免KYC独享成品号。该商品由客服人工交付，订阅周期为一个月。原账号充值订单请看对应商品的办理说明。 [Max 5x 成品号](https://www.gpt-duo.com/products/claude-max-5x-no-kyc-exclusive-account-monthly)

本教程适用于 Claude Code 的终端安装和登录排查。网页、桌面端、手机端、Cowork 及第三方应用的使用范围，以所购商品页和订单说明为准。

## 开始前准备什么？

保存原订单号，按订单说明查收客服交付的三项信息：**邮箱地址、邮箱账号、邮箱密码**。如果需要客服协助，提供终端报错、网络检测结果和 `claude --version` 的输出。分享截图时遮住密码和验证码。

## 第一步 检查并清理旧中转配置

过去用过第三方 API 地址、API Key 或中转工具的，先确认 `ANTHROPIC_BASE_URL`、`ANTHROPIC_AUTH_TOKEN`、`ANTHROPIC_API_KEY` 的来源。只处理确定属于已停用中转服务的配置。团队网关、工作账号的 API Key 和其他项目配置按原用途保留。没有配置过中转的人可以直接进入下一步。 [Claude Code 官方认证说明](https://code.claude.com/docs/en/authentication)

| 系统 | 从哪里检查 | 常见问题 |
| --- | --- | --- |
| Windows | 用 PowerShell 打开系统终端，检查当前进程、用户级或系统级环境变量，以及用户和项目的 Claude Code 设置。可以从 Windows 的「编辑系统环境变量」窗口核对变量名称。 | 提示找不到脚本时，核对桌面或下载目录的实际文件路径，以及文件名是否多了 `(1)`。遇到执行策略限制，仍可手工完成配置检查。 |
| macOS | 用聚焦搜索打开「终端」，检查以前修改过的 `~/.zshrc`、`~/.zprofile` 或其他 Shell 启动文件，以及用户和项目的 Claude Code 设置。 | 遇到权限、路径错误或系统拦截时，先核对文件来源、实际路径和重复下载的文件名，再按手工步骤处理。 |

对照设置时，先备份要改的文件，只移除已确认的旧 API 地址和认证项。Claude Code 的 `~/.claude.json` 还存有账户和项目状态。完成后新开终端，再查看 Claude Code 是否仍显示旧的 API 计费方式或服务地址。 [官方设置文件说明](https://code.claude.com/docs/en/settings)

![图 1　旧配置下 Claude Code 仍显示 API 计费](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/01-old-api-login-469f76adeedd.png)

图 1 旧配置下 Claude Code 仍显示 API 计费

![图 2　重新打开后出现首次设置界面](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/02-clean-onboarding-0f9a5c3107ba.png)

图 2 重新打开后出现首次设置界面

重新打开 Claude Code 后，核对当前登录方式。如果仍显示 API 计费或旧服务地址，继续检查终端环境变量和设置文件。需要客服协助时，可附上脱敏后的终端截图。

熟悉脚本的用户可以查看 Windows 和 macOS 的源码参考。脚本可能改写 Claude 状态文件、重置 Codex 登录配置或在终端显示配置内容。只需要清理旧 API 设置时，按上面的手工步骤逐项处理。 [PowerShell 源码参考](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/clean-claude-proxy.ps1-de50b03dbe6a.txt) · [macOS 源码参考](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/clean-claude-proxy.sh-627a71a44b2a.txt)

## 第二步 检查网络能否完成安装和授权

### 先看检测分数，再测实际连接

打开检测页，看左侧的「Claude AI 信任评分」。**达到 80 分即可作为初步参考**。图 3 的 86 分就是一个例子。图中「机房 IP」指服务器的出口地址，「住宅 IP」指家庭宽带一类的出口地址。图里的机房 IP 也达到了参考分数。 [Net.Coffee 网络检测](https://ip.net.coffee/claude/)

![图 3　第三方网络检测页的出口地址和评分](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/03-network-check-b8cc1f61f7eb.jpeg)

图 3 第三方网络检测页的出口地址和评分

接着确认浏览器能打开 Claude 登录页，再从系统终端重试下载或登录。浏览器和终端都能正常连接时，就可以继续下一步。 [Claude Code 官方网络排查](https://code.claude.com/docs/en/troubleshoot-install#check-network-connectivity)

### 不会改网络设置，就把报错交给 AI 排查

如果网页能打开，但 Claude Code 在下载或登录时卡住，把**出错的那一步、终端报错和检测截图**一起发给你能正常使用的 AI，再复制下面这段话。已经在用 Clash 的话，重试时顺手截一张「连接」或「日志」页面。截图里遮住完整 IP、账号、授权码和订阅链接。

先用 Net.Coffee 测一次。需要补充时，可以再用另外两个检测站查看相关项目。把和报错有关的结果发给 AI 即可，能否修好以终端重试的结果为准。 [Net.Coffee](https://ip.net.coffee/claude/) · [浏览器环境检测](https://fuck-claude.vercel.app/zh/) · [CheckCC](https://checkcc.org/)

**复制给 AI**

```text
我在安装或登录 Claude Code 时卡住了。我把报错和网络检测截图发给你，请用新手能听懂的话帮我排查。

我的系统：[Mac 或 Windows]
卡住的步骤：[下载、打开 Claude Code 或浏览器授权]
Claude 网页能否打开：[能 / 不能 / 没试过]
代理客户端和版本（如有）：[例如 Clash，版本不清楚就填不知道]
终端报错：[粘贴报错]

请先判断问题更像是下载地址不可达、终端没有走预期路线、DNS 解析失败，还是浏览器授权异常。信息不够时，告诉我下一步点哪里、看哪一行。

如果我在用 Clash，请先让我重试一次，并教我在连接列表中看 TUN 有没有接到终端请求，以及 Claude 的请求实际命中了哪个域名规则。只有报错指向 DNS 时，再检查 DNS 分流、DoH、Fake-IP 和 respect-rules，按我现有的客户端和版本解释怎么查。

如果证据指向连接不稳定，再判断是否需要对照测试 QUIC 或 IPv6、检查节点断线时有没有回退到直连，或检查备用协议切换前后的出口 IP 是否一致。保留其他应用的网络设置。检测分数只作为参考，请根据实际报错给建议。

每次只给我一个改法，写清楚到哪里操作、怎么恢复、怎么回到原终端复测。如果你能操作我的电脑，先告诉我准备改哪一项，等我确认再改。
```

按 AI 给的步骤改完一项，就回到原来的终端重试。下载、连接或授权恢复正常后，可以继续安装或登录。 [Claude Code 官方网络排查](https://code.claude.com/docs/en/troubleshoot-install#check-network-connectivity)

## 第三步 用官方安装器安装 Claude Code

| 系统 | 在哪里打开 |
| --- | --- |
| macOS | 用聚焦搜索或启动台打开「终端」。 |
| Linux／WSL | 打开系统终端。Windows 使用 WSL 的，从开始菜单打开已安装的 Linux 发行版。 |
| Windows PowerShell | 从开始菜单打开 PowerShell，提示符通常带 `PS`。 |
| Windows CMD | 从开始菜单打开「命令提示符」，提示符通常没有 `PS`。 |

**macOS、Linux 或 WSL**

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows PowerShell**

```powershell
irm https://claude.ai/install.ps1 | iex
```

**Windows CMD**

```cmd
curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd
```

安装完成后打开新终端，运行 `claude --version`。能够显示版本号后运行 `claude`。之前用 npm 安装过的人，如果发现系统还在运行旧版本，先按官方指引检查是否存在多套安装或 PATH 顺序问题。 [Anthropic 官方安装方法](https://code.claude.com/docs/en/quickstart)

## 第四步 在系统终端发起 Claude Code 授权

### 4.1 打开对应系统的终端

先在系统终端发起授权，便于排查 VS Code、Cursor 等编辑器的集成终端是否加载了不同的环境变量。登录后可在支持的编辑器中继续使用。

![图 4　macOS 系统终端打开 Claude Code](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/04-macos-terminal-b3947aae100c.png)

图 4 macOS 系统终端打开 Claude Code

![图 5　Windows CMD 打开 Claude Code](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/05-windows-cmd-a63bfb6d15ec.png)

图 5 Windows CMD 打开 Claude Code

![图 6　Windows PowerShell 打开 Claude Code](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/06-windows-powershell-b0cf5e443d4b.png)

图 6 Windows PowerShell 打开 Claude Code

### 4.2 核对版本

运行 `claude --version` 核对版本。若命令报错，回到安装步骤检查当前终端能否找到 Claude Code。需要客服协助时，提供版本号或这一屏的脱敏截图。

### 4.3 发起登录并选择账号类型

首次打开时按界面提示选主题和登录方式。已有登录时，可输入 `/login` 重新发起。使用 Claude 订阅时，选择 Claude 订阅账号入口。画面上的按钮和套餐名以当前版本为准。

![图 7　Claude Code 连接被拒绝时的提示](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/07-connection-error-e0563fa6f1cd.png)

图 7 Claude Code 连接被拒绝时的提示

![图 8　首次启动选择终端主题](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/08-theme-selection-0f9a5c3107ba.png)

图 8 首次启动选择终端主题

![图 9　选择 Claude 订阅账号登录](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/09-login-method-9a04b465454e.png)

图 9 选择 Claude 订阅账号登录

出现连接被拒绝、超时或 OAuth 错误时，先记录报错信息，再检查是网络、账号还是授权环节出了问题。若终端提示授权已过期，用当前终端重新发起授权。 [官方安装与登录排障](https://code.claude.com/docs/en/troubleshoot-install)

### 4.4 按订单说明完成授权

浏览器打开 Claude 登录页后，按本单交付说明选择登录方式。使用邮箱登录时，在 Claude 页面填入本单账号绑定的电子邮箱，再按交付说明打开收件邮箱，用收到的邮箱账号和邮箱密码登录，查收 Claude 发来的登录链接或按提示完成验证。如果订单说明使用 Google 登录，则通过「Continue with Google」进入 Google 登录页面，核对本单邮箱后继续。

确认浏览器当前登录的是本单账号，再按页面提示完成授权。如果官方页面要求手动输入授权码，把代码贴回发起本次登录的终端。 [Claude 账号登录说明](https://support.claude.com/en/articles/13189465-log-in-to-your-claude-account) · [Claude Code 官方授权流程](https://code.claude.com/docs/en/quickstart)

![图 10　终端等待输入授权码](https://www.gpt-duo.com/uploads/claude-code-tutorial-20261108/10-authorization-code-prompt-d474ba83b05f.png)

图 10 终端等待输入授权码

## 登录后怎么验收？

在 Claude Code 输入 `/status` 检查连接和当前账号。在测试目录里发一个简单问题，收到回复后再开始实际任务。套餐档位和订阅起止时间按订单与账号实际显示核对。

## 常见问题怎么排查？

| 现象 | 先检查什么 |
| --- | --- |
| 找不到 `claude` 命令 | 新开终端，确认安装是否完成、安装目录是否在 PATH。 |
| 显示旧的 API 地址或 API 计费方式 | 回到第一步，核对残留环境变量和 Claude Code 设置。 |
| 终端显示错误账号 | 用 `/login` 切换，核对当前授权账号。需要完全退出时可用 `/logout`。 |
| 官方通知账号已停用 | 查看官方通知，认为处理有误时按指引申诉。有订单疑问时凭订单号联系本站客服。 |

[Claude Code 官方排障](https://code.claude.com/docs/en/troubleshoot-install) · [Claude 账号停用与申诉](https://support.claude.com/en/articles/8241253-safeguards-warnings-and-appeals)

## 附录 Claude Code 常用操作与用量

| 操作 | 怎么用 |
| --- | --- |
| 自动编辑与 Plan 模式 | 用 Shift+Tab 切换模式并核对界面上的模式名称，也可用 `/plan` 进入 Plan 模式。快捷键以当前终端提示为准。 |
| 指定文件 | 输入 `@` 后选文件路径，把文件作为当前问题的上下文。 |
| 粘贴图片 | 使用当前终端提示的粘贴快捷键，也可以拖入图片或输入图片的文件路径。 |
| 管理会话 | `/clear` 开始新对话，`/compact` 压缩当前会话，`/status` 查看状态，`/doctor` 检查安装与设置，`/model` 切换模型。 |
| 项目记忆 | 用项目的 `CLAUDE.md` 写项目约定，用 `~/.claude/CLAUDE.md` 写个人通用约定。 |
| 思考和推理强度 | 按当前模型和版本支持的方式调整推理强度。部分版本可在提示中使用 `ultrathink`，具体以当前界面和命令说明为准。 |
| 查看订阅额度 | 在当前账号的用量界面查看，CLI 如提供 `/usage` 或状态界面中的 Usage 入口，也可以从终端打开。 |
| 查看本地用量统计 | 可用第三方工具 `ccusage` 查看本地记录。用 `npm install -g ccusage` 安装后，运行 `ccusage daily` 查看按天统计。订阅剩余额度请在账户用量页查看。 |

[官方命令参考](https://code.claude.com/docs/en/commands) · [官方记忆说明](https://code.claude.com/docs/en/memory) · [ccusage 项目](https://github.com/ryoppippi/ccusage)

## 订阅周期内掉订阅怎么处理？

本款成品号的质保范围如下。

- **质保首登。** 首次登录本单交付的账号遇到问题，可联系 GPT-DUO 客服核实处理。
- **质保掉订阅。** 本次一个月订阅周期内掉订阅，按剩余订阅天数比例退款。
- **不质保封号。** 账号被封禁不属于质保范围。

联系售后时，请保留原订单，并提供相应的订阅状态或脱敏后的报错截图。
