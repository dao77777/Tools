> **创建日期:** 2021/10/9
>
> **作者:** 道五七

- [Vscode](#vscode)
  - [插件](#插件)
- [Vim](#vim)
  - [普通模式](#普通模式)
  - [插入模式](#插入模式)
  - [可视模式](#可视模式)
- [Git&GitHub](#gitgithub)
  - [.gitignore](#gitignore)
  - [配置](#配置)
  - [工作区-暂存区-本地库](#工作区-暂存区-本地库)
  - [远程库](#远程库)
  - [标签](#标签)
  - [分支](#分支)

# Vscode
## 插件
- Auto Rename Tag
- Bracket Pair Colorizer
- C/C++
- Code Runner
- Live Server
- Volar

# Vim
## 普通模式
- 进入方式: `esc`
- 光标移动
  - 字符移动: `h`(左移), `l`(右移), `k`(上移), `j`(下移)
  - 单词移动: `b`, `e`, `w`, `ge`
  - 行移动: `0`(行首), `^`(行首字符), `$`(行尾), `gg`(首行), `G`(末行)
  - 字符查找: `f<char>`(向后找), `F<char>`(向前找), `t<char>`, `T<char>`, `;`(向后重复上次查找指令), `,`(向前重复上次查找字符)
- 操作
  - 删除: `d`
  - 修改: `c`
  - 复制: `y`
  - 粘贴: `p`
  - 撤销: `u`
- 动作
  - `xx`(xx一行),`<number>xx`(xx指定行数)
  - `i`(inner), `a`(around), `w`, `t`, `s`, `p`, `e`, 各种括号引号(", ', `, <, [, {(B), ((b), )
  - `f<char>`, `F<char>`, `^`, `$`
- 大小写切换
 - 切换当前字符大小写: `~`
 - 切换指定数量字符的大小写: `<number>~`
 - 切换一整行大小写: `g~~`
 - 切换一整行为大写: `gUU`
 - 切换一整行为小写: `guu`
 - 改变动作选取的字符: `gU<动作>`
 - 改变动作选取的字符为小写:： `gu<动作>`
- 跳转
  - 跳转到定义: `gd`, `gD`
  - 跳转页签: `gt`, `gT`
## 插入模式
- 进入方式: `i`
- 光标前插入: `i`(insert)
- 光标后插入: `a`(append)
- 行尾插入: `I`
- 行首插入: `A`
- 下一行插入: `o`
- 上一行插入: `O`
## 可视模式
- 进入方式: `v`

# Git&GitHub
## .gitignore
- 作用: 用来忽略掉项目中某些文件
- 用法
  - `#`: 注释
  - `!`: 否定  
  - `[a-z], [abc]`: 或
  - `*`: 任意
  - `/abc`: 当前目录
  - `abc/abc`: 子目录
  - `abc/**/abc`: 任意级目录
## 配置
- 配置: 系统, 用户, 本地
- `git --version`: 查看版本
- `git 命令 -h`: 帮助指令
- `git config user.name 昵称`: 初始化昵称, `--global` 全局
- `git config --global user.email 邮箱`: 初始化邮箱, `--global` 全局
- `git config --global init.defaultBranch 默认分支名`: 配置默认分支名
- `git config --list --show-orgin`: 显示所有配置
## 工作区-暂存区-本地库
- 区: 工作区, 暂存区, 本地库, 远程库
- 文件状态: 未追踪, 未修改, 已修改
- `git status 文件名`: 工作区&暂存区, 暂存区&本地库, 文件差别
- `git diff 文件名`: 工作区&暂存区 详细差别, `--staged` 暂存区&本地库 详细差别
- `git log`: 本地库提交记录
  - `分支名`: 显示指定分支
  - `--all`: 显示所有
  - `--oneline`: 简明显示
  - `--graph`: 图结构显示
- `git reflog`: 本地库提交记录
- `git show commit编号|标签名`: 查看指定版本
- `git add 文件名`: 工作区->暂存区, 追踪
- `git commit -m "评论内容"`: 暂存区->本地库
- `git rm 文件名`: 取消追踪, `--cache` 取消追踪但保留文件
- `git restore 文件名`: 本地库->暂存区, `--staged` 暂存区->工作区
- `git reset --hard commit编号`: 回滚
- `git commit --amend`: 修改上次提交
## 远程库
- `git remote -v`: 查看远程库
- `git remote show 远程库别名`: 详细查看远程库
- `git remote rename 源名 目的名`: 重命名
- `git rmeote add 远程库别名 远程库地址`: 添加远程库
- `git remote remove 远程库别名`: 移除远程库
- `git clone 远程库地址`: 克隆远程库
## 标签
- `git tag`: 列出当前标签
  - `标签名 commit编号` 为当前commit打简单标签
  - `-a 标签名 -m 标签注释 commit 编号` 打注释标签
  - `-d 标签名` 删除指定标签
  - `-l 正则` 列出正则匹配的标签
- `git push 远程库别名`:
  - `标签名|--tags` 给远程库打标签
  - `--delete 标签名` 给远程库删标签
- `git checkout 标签名`: 建立独立分支并切换到标签所对应的commit
## 分支
- `git branch`: 
  - `分支名` 建分支
  - `-d 分支名` 删分支
  - `--merged` 显示已合并分支
  - `--no-merged` 显示未合并分支
  - `--move oldName newName` 分支改名
- `git checkout`:
  - `分支名` 切分支
  - `-b 分支名` 建并切分支
- `git merge 分支名`: 合并分支
- `git push 远程库别名 本地分支名:远程分支名`: 推送远程分支
- `git push --set-upstream 远程库别名 本地分支名:远程分支名`: 远程分支改名
- `git push --delete 远程库别名 分支名`: 删远程分支
- `git pull 远程库别名 远程分支名:本地分支名`: 拉取远程分支
