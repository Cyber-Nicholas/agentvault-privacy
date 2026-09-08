---
layout: default
title: AgentVault Privacy Policy
---

# AgentVault Privacy Policy

Last updated: 2026-09-08

AgentVault is a local macOS credential broker. The developer operates no backend service and collects no personal data, analytics, crash reports, or advertising identifiers. The app contains no tracking or third-party SDKs.

## Storage and user-directed use

- Website passwords and API tokens are stored in the user's own synchronizable iCloud Keychain records. Apple manages synchronization between devices using the same Apple Account. These records are separate from the entries managed through Apple's Passwords app.
- Each Mac generates its own SSH private key, stored only in that Mac's Data Protection Keychain. SSH private keys are not synchronized or exported through the app, CLI, or MCP.
- After Touch ID authorization, website credentials and API tokens can be returned in plaintext to the local agent the user is using. They enter that agent's tool output and context. AgentVault cannot control how the receiving agent subsequently processes or retains them. Authorization may be reused within its exact scope for up to 10 idle minutes and 30 minutes in total.
- For SSH, AgentVault runs the system SSH client for the requested destination. A private key is temporarily materialized in a permission-restricted local file and removed when the operation ends. User-requested host-key discovery also connects to the chosen SSH server.
- Credential names, allowed targets, SSH public-key metadata and host trust records are stored locally or in the user's Keychain as needed. Local activity records contain time, action, credential ID, requester label, target and outcome, but never secret values or authorization tokens. They are retained for up to 30 days and can be cleared in the app.
- Users can explicitly copy a credential to the clipboard. Secret clipboard contents are cleared after 60 seconds if the clipboard still contains that value.

## Browser import and agent setup

Browser import reads only a password CSV explicitly selected by the user. It does not access browser databases, history or cookies. The CSV is parsed in memory; one Touch ID approval is required before saving a batch to the user's iCloud Keychain. No CSV copy or password log is created. The user is reminded to delete the original plaintext export after verification.

Agent discovery checks a fixed set of common application and configuration locations, not chats or session contents. Configuration is modified only after the user chooses Enable. Other settings are preserved, and an original configuration backup is created locally with owner-only permissions (0600). These files may contain other services' sensitive settings and are not uploaded.

The isolated unsigned preview uses synthetic data and cannot access real credentials protected by an application identity. It does not replace the protected credential service.

## Third parties and deletion

Apple's processing of iCloud Keychain data is governed by Apple's terms and privacy policy. Any agent receiving a user-authorized credential is governed by that agent provider's terms. AgentVault does not sell data or send credentials to the developer.

Users can delete stored credentials in the app; deletion of a synchronizable credential propagates through iCloud Keychain. SSH keys and activity records are local. Removing the app does not automatically delete Keychain records; delete unwanted records before uninstalling.

Questions: [Support](support). Policy changes are published here with an updated date.

## 简体中文

AgentVault 是本机 macOS 凭据代理。开发者不经营后端服务，不收集个人数据、统计分析、崩溃报告或广告标识；应用没有跟踪和第三方 SDK。

- 网站密码和 API Token 保存在用户自己的同步型 iCloud Keychain 项目中，由 Apple 在同一 Apple 账号的设备之间同步。这些项目与 Apple“密码”App 管理的条目独立。
- 每台 Mac 单独生成 SSH 私钥，存入本机 Data Protection Keychain；私钥不同步，也不通过应用、CLI 或 MCP 导出。
- Touch ID 授权后，网站凭据和 API Token 可以明文返回用户当前使用的本机 Agent，并进入其工具输出和上下文。AgentVault 无法控制接收方后续如何处理或保存。授权在限定范围内可复用，闲置上限 10 分钟、总时长上限 30 分钟。
- SSH 使用系统客户端连接用户指定的服务器；私钥短暂写入受权限保护的本地临时文件，操作结束后删除。用户请求的主机公钥检查也会连接对应 SSH 服务器。
- 凭据名称、允许的目标、公钥元数据和主机信任记录按需存放在本机或用户 Keychain 中。本地活动记录仅含时间、操作、凭据 ID、请求方标签、目标和结果，不含秘密或授权 Token，最多保留 30 天，可手动清除。
- 用户主动复制秘密后，剪贴板内容在 60 秒后按值清理；用户已复制其他内容时不会覆盖。
- 浏览器导入只读取用户明确选择的密码 CSV，不读取浏览器数据库、历史或 Cookie。文件在内存中解析，一次 Touch ID 批量保存到用户的 iCloud Keychain；不创建 CSV 副本或密码日志。原导出文件由用户在验证后自行删除。
- Agent 发现只检查支持客户端的常见应用/配置位置，不读取聊天或会话。用户点击启用后才修改配置，保留其他设置，并创建仅限本人读写（0600）的本机备份；配置和备份可能包含其他服务的敏感设置，不会上传。
- 隔离的无签名体验版使用虚构数据，不读取真实凭据，不替代受保护的凭据服务。

Apple 的 iCloud Keychain 处理受 Apple 条款和隐私政策约束；收到授权凭据的 Agent 受其服务商条款约束。AgentVault 不出售数据，也不向开发者发送凭据。

用户可在应用中删除凭据；同步型凭据的删除会通过 iCloud 传播。SSH 私钥和活动记录仅限本机。卸载应用不会自动删除 Keychain 条目，请先在应用中删除不再需要的条目。

联系：[支持页面](support)。政策变更会更新本页日期。
