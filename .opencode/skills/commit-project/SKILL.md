---
name: commit-project
description: 提交项目到Gitee。当用户说"提交项目"、"推送代码"、"sync to gitee"、"commit and push"时使用。Use ONLY when the user explicitly asks to commit and/or push the current project to the Gitee remote.
---

# 提交项目

将当前项目提交并推送到 Gitee 远程仓库 https://gitee.com/zhang-shunchang010/zsc010。

## 步骤

1. **检查远程配置**：执行 `git remote -v`。若输出为空，执行 `git remote add origin https://gitee.com/zhang-shunchang010/zsc010`。
2. **暂存所有更改**：`git add -A`。
3. **提交**：`git commit -m "更新课程内容"`（若用户指定了提交信息，使用用户的）。
4. **推送**：`git push -u origin main`。若 main 分支不存在，先执行 `git branch -M main` 重命名当前分支。

## 注意事项

- 如果 commit 失败提示无更改可提交，告知用户工作区是干净的。
- 如果 push 失败提示认证问题，告知用户检查凭据（Gitee 账号密码或 SSH key）。
- 提交信息默认使用"更新课程内容"，但优先使用用户指定的信息。
- 所有命令在工作目录 F:\ggg 下执行。
