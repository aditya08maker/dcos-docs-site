---
layout: layout.pug
navigationTitle:  dcos task
title: dcos task
menuWeight: 16
excerpt: 管理 DC/OS 任务
render: mustache
model: /mesosphere/dcos/2.1/data.yml
enterprise: false
---

# 说明

`dcos task` 命令可让您管理 DC/OS 任务。

**从 DC/OS 2.0 开始，此命令已弃用，请使用 `dcos task list` 代替。**

# 使用

```bash
dcos task [OPTIONS]
```

# 选项

| 名称 | 说明 |
|---------|-------------|
| `-h`, `--help` |  打印用法。 |
| `--agent-id`  |    仅列出指定代理的任务。 |
| `--info` | 打印该子命令的简短描述。|
| `--version` | 打印版本信息。|

# 命令

