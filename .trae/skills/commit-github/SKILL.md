---
name: commit-github
description: 提交项目到GitHub。当用户说"提交到github"、"推送代码到github"、"push to github"、"sync to github"时使用。Use ONLY when the user explicitly asks to commit and/or push the project to the GitHub remote.
---

# 提交项目到 GitHub

将当前项目提交并推送到 GitHub 远程仓库 https://github.com/Zszzz1/zsc（SSH 公钥已配置）。

## 步骤

1. **检查远程配置**：执行 `git remote -v`。
   - 若没有名为 `github` 的远程，执行 `git remote add github https://github.com/Zszzz1/zsc.git`。
   - 若 `github` 远程地址不对，执行 `git remote set-url github https://github.com/Zszzz1/zsc.git`。
   - 注意：`origin` 是 Gitee 远程，保持不动，不要覆盖。
2. **暂存所有更改**：`git add -A`。
3. **提交**：`git commit -m "更新课程内容"`（若用户指定了提交信息，使用用户的）。
4. **推送**：`git push -u github main`。若 main 分支不存在，先执行 `git branch -M main` 重命名当前分支。

## 注意事项

- 如果 commit 失败提示无更改可提交，告知用户工作区是干净的。
- 如果 push 失败提示认证问题，让用户运行 `ssh -T git@github.com` 检查 SSH 公钥是否生效。
- 提交信息默认使用"更新课程内容"，但优先使用用户指定的信息。
- 所有命令在工作目录 F:\ggg 下执行。
