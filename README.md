# 爱文言 Skill for OpenClaw

![爱文言](./logo.png)

`iwenyan` 是由爱文言构想的 OpenClaw 文言文答复技能。安装后，AI 默认以文言文作答，并可在会话中切换六种文体：典雅正宗、史传简劲、骈俪华美、书札尺牍、奏议公牍、禅意清简。

本仓库名为 `wenyan-skill`；实际 ClawHub slug 计划为 `iwenyan`。

## 特性

- 默认纯文言作答。
- 用户明确要求解释、翻译或白话说明时，可转为白话。
- 支持用自然口令切换文体，例如“改为骈体”“改为尺牍体”“恢复默认”。
- 代码、命令、URL、路径、API 名称、日志和错误信息保持原样，外围说明使用文言。
- 纯文本技能，无脚本、无外部 API、无环境变量、无安装前置命令。

## 目录

```text
wenyan-skill/
├── README.md
└── iwenyan/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── references/
    │   └── styles.md
    └── .clawhubignore
```

## 本地使用

将 `iwenyan/` 复制到 OpenClaw 工作区的 `skills/` 目录，或用 ClawHub 安装发布后的版本。

安装后可直接提问；默认文体为“典雅正宗”。

示例口令：

```text
改为骈体
改为史传体
改为尺牍体
恢复默认
```

## ClawHub 发布

发布前先确认已安装并登录 `clawhub` CLI：

```powershell
clawhub login
```

从仓库根目录发布：

```powershell
clawhub skill publish .\iwenyan --slug iwenyan --name "爱文言" --version 0.1.0 --tags latest --changelog "Initial release: classical Chinese response layer with six registers."
```

发布后用户可安装：

```powershell
openclaw skills install iwenyan
```

或：

```powershell
clawhub install iwenyan
```

## 安全声明

本技能不包含脚本，不读取或写入本地文件，不访问外部网络，不要求环境变量，也不要求用户执行安装前置命令。它只通过 `SKILL.md` 和文本参考文件约束 AI 的答复文体。

## 发布检查

首版发布前建议确认：

- `iwenyan/SKILL.md` 中 `name` 为 `iwenyan`。
- ClawHub 发布命令显式传入 `--slug iwenyan`。
- 发布路径为 `.\iwenyan`，不要从仓库根目录发布。
- `logo.png` 仅用于 GitHub README，不包含在 ClawHub 技能包内。

## License

ClawHub 文档说明，发布到 ClawHub 的 skill 按 MIT-0 授权供用户使用、修改和再分发。本仓库亦按 MIT-0 发布。
