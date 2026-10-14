# Windows 上的 Git 分支与 PR 练习

在 PowerShell 中，先克隆仓库并进入目录：

```powershell
git clone https://github.com/J1ngYue/github-workflow-practice.git
Set-Location github-workflow-practice
git switch -c docs/example-change
```

编辑需要修改的文档，检查差异，再提交并推送：

```powershell
git diff
git add README.md
git commit -m "docs: improve the workflow example"
git push -u origin docs/example-change
```

在 GitHub 仓库页面创建 PR，确认目标分支是默认分支，检查 Files changed 后合并。
完成后更新本地默认分支：

```powershell
git switch main
git pull --ff-only
```

如果切换分支时提示存在未提交的修改，先保存并提交需要保留的内容，再继续。
为防止覆盖其他人的提交，日常同步优先使用 `git pull --ff-only`，不要随意强制推送。
