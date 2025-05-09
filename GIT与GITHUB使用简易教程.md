## 从零开始创建 GitHub 仓库的简单教程
下面是一个非常简单的教程，从创建一个目录和一个文件开始，然后将其推送到 GitHub。

## 步骤 1: 创建一个新目录
``` sh
# 创建一个新目录
mkdir demo

# 进入该目录
cd demo
```
## 步骤 2: 创建一个简单的 README 文件
``` sh
# 创建一个简单的 README 文件
echo "# 我的第一个仓库" > README.md
```
## 步骤 3: 初始化 Git 仓库
``` sh
# 初始化 Git 仓库
git init
```
## 步骤 4: 添加文件到 Git
``` sh
# 添加 README 文件到暂存区
git add README.md

# 查看状态（可选）
git status
```
## 步骤 5: 提交更改
``` sh
# 提交更改
git commit -m "第一次提交"
```
## ## 步骤 6: 在 GitHub 上创建新仓库
1. 登录 GitHub
2. 点击右上角的 "+" 图标，选择 "New repository"
3. 仓库名称输入 "demo"
4. 不要勾选 "Initialize this repository with a README"
5. 点击 "Create repository"
## 步骤 7: 连接到 GitHub 远程仓库
``` sh
# 添加远程仓库（替换为你的 GitHub 用户名）
git remote add origin https://github.com/你的用户名/demo.git

# 验证远程仓库已添加
git remote -v
```
## ## 步骤 8: 推送到 GitHub
``` sh
# 推送到 GitHub
git push -u origin master
# 或者如果默认分支是 main
# git push -u origin main
```
## 完成！
现在你已经成功创建了一个仓库，添加了一个文件，并将其推送到了 GitHub。

## 后续操作
如果你想添加更多文件，可以重复步骤 4-5 和 8：
``` sh
# 创建新文件
echo "这是一个新文件" > 新文件.txt

# 添加到暂存区
git add 新文件.txt

# 提交更改
git commit -m "添加新文件"

# 推送到 GitHub
git push
```
希望这个简单的教程对你有所帮助！

# GitHub 分支名称变更说明
## 为什么 master 不成功而 main 成功
您遇到的情况是因为 GitHub 在 2020 年 10 月左右进行了一项重要变更，将默认分支名称从 master 改为 main 。
## 解决方法
### 方法一：使用 main 分支（推荐）
既然 main 分支推送成功，建议继续使用 main 作为您的默认分支：
``` sh
# 确认当前分支
git branch

# 如果需要，创建并切换到 main 分支
git checkout -b main

# 推送到 main 分支
git push -u origin main
```
### 方法二：如果必须使用 master 分支
如果您有特殊需求必须使用 master 分支：
``` sh
# 在 GitHub 上创建 master 分支
# 1. 登录 GitHub
# 2. 进入仓库
# 3. 点击分支下拉菜单
# 4. 输入 "master" 创建新分支

# 然后在本地推送到 master 分支
git push -u origin master
```
### 方法三：将旧仓库的默认分支改为 main
如果您想统一使用 main ，可以将旧仓库的默认分支也改为 main ：
``` sh
# 在本地创建 main 分支
git checkout -b main

# 推送到远程
git push -u origin main

# 在 GitHub 网站上将 main 设为默认分支
# 然后可以删除 master 分支
```
## 总结
GitHub 的这一变更反映了软件行业对术语的重新思考。对于新项目，建议直接使用 main 作为默认分支，以符合当前的最佳实践。

希望这个解释能帮助您理解为什么会出现这种情况！