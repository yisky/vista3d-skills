# vista3d-skills

vista3d 的配套 Cursor Skill。与 MCP 服务分开维护：MCP 提供可检索事实，本仓库提供调用顺序与禁止项。

## 安装

克隆到 Cursor 能加载的目录（仓库根必须是 `SKILL.md`）：

```bash
git clone https://github.com/yisky/vista3d-skills.git ~/.cursor/skills/vista3d
```

Windows：

```bash
git clone https://github.com/yisky/vista3d-skills.git %USERPROFILE%\.cursor\skills\vista3d
```

某个业务项目内：

```bash
git clone https://github.com/yisky/vista3d-skills.git .cursor/skills/vista3d
```

更新：`git pull`。

开发时作为 `vista3d` 主仓的 git submodule，目录为仓库根下的 `skills/`。
