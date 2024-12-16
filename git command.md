# Git 常用命令速查手册



## 一、初始化与配置

### 1. 初始化仓库

   - 在当前目录初始化一个新的 Git 仓库。

     ``` bash
     git init

   - `git init <目录>` : 在指定目录初始化一个新的 Git 仓库。

     ```bash
     git init <目录>
     ```

### 2. 克隆远程仓库

   - 克隆远程仓库到本地。

     ```bash
     git clone <远程仓库地址>
     ```

   - 克隆远程仓库到指定本地目录。

     ```bash
     git clone <远程仓库地址> <本地目录>
     ```

### 3. 配置

   - 设置全局用户名。

     ```bash
     git config --global user.name "github用户名"
     ```

   - 设置全局用户邮箱。

     ```bash
     git config --global user.email "github邮箱地址"
     ```

   - 设置当前仓库用户名。

     ```bash
     git config user.name "<用户名>"

   - 设置当前仓库用户邮箱。

     ```bash
     git config user.email "<邮箱地址>"
     ```

   - 查看当前配置信息。

     ```bash
     git config --list
     ```

     

## 二、基本操作

### 1. 工作区、暂存区、仓库

   - **工作区**：你的本地文件修改。
   - **暂存区 (Staging Area)**：准备提交的文件。
   - **仓库 (Repository)**：提交历史记录和版本信息。

### 2. 查看状态

   - 查看工作区和暂存区的状态。

      ```bash
      git status    #`--short` 或 `-s`:  简洁显示状态。
      ```

### 3. 添加到暂存区

   - 将指定文件添加到暂存区。

     ```bash
     git add <文件名>
     ```

   - 将所有修改和新增的文件添加到暂存区。

     ```bash
     git add .
     ```

### 4. 提交到仓库

   - 将暂存区的文件提交到仓库，并添加提交信息。

     ```bash
     git commit -m "<提交信息>"
     ```

   - 打开编辑器，编辑提交信息。

     ```bash
     git commit
     ```

   - 修改上一次提交，可以修改提交信息，也可以重新提交暂存区的内容。

     ```bash
     git commit --amend
     ```

### 5. 删除文件

   - 删除工作区和暂存区中的文件，并添加到暂存区以便下次提交。

     ```bash
     git rm <文件名>
     ```

   - 只从暂存区删除文件，保留工作区中的文件。

     ```bash
     git rm --cached <文件名>
     ```

### 6. 移动/重命名文件

   - 重命名或移动文件，并添加到暂存区。

     ```bash
     git mv <旧文件名> <新文件名>
     ```

     

## 三、分支操作

### 1. 查看分支

   - 查看本地分支。

     ```bash
     git branch
     ```

   - 查看远程分支。

     ```bash
     git branch -r
     ```

   - 查看所有分支（本地和远程）。

     ```bash
     git branch -a
     ```

### 2. 创建分支

   - 创建新分支。

     ```bash
     git branch <分支名>
     ```

### 3. 切换分支

   - 切换到指定分支。

     ```bash
     git checkout <分支名>
     ```

   - 创建并切换到新分支。

     ```bash
     git checkout -b <新分支名>
     ```

### 4. 合并分支

   - 将指定分支合并到当前分支。

     ```bash
     git merge <分支名>
     ```

   - 将指定分支合并到当前分支，并压缩为一个提交。

     ```bash
     git merge --squash <分支名>
     ```

### 5. 删除分支

   - 删除本地分支 (如果已合并)。

     ```bash
     git branch -d <分支名>
     ```

   - 强制删除本地分支 (即使未合并)。

     ```bash
     git branch -D <分支名>
     ```

   - 删除远程分支。

     ```bash
     git push origin --delete <分支名>
     ```

     

## 四、远程仓库操作

### 1. 添加远程仓库

   - *添加一个新的远程仓库。

     ```bash
     git remote add <远程仓库名> <远程仓库地址>     #常用远程仓库名： origin
     ```

   - 查看所有远程仓库名及其对应的 URL。

     ```bash
     git remote -v   
     ```

### 3. 推送到远程仓库

   - 推送本地分支到远程仓库
     
      ```bash
      git push <远程仓库名> <本地分支名>:<远程分支名>
      git push origin main   #通常写法：推送本地 `main` 分支到远程 `origin` 的 `main` 分支
      ```
      
   - 推送本地分支到远程仓库，并设置关联关系。
     
      ```bash
      git push -u <远程仓库名> <本地分支名>   #第一次使用时，可以简化推送 `git push -u origin main`，后续可以直接 `git push`
      ```
      
   - 推送所有本地分支到远程仓库。

      ```bash
      git push --all <远程仓库名>`
      ```

### 4. 从远程仓库拉取

   - 从远程仓库拉取并合并到本地分支。

      ```bash
      git pull <远程仓库名> <远程分支名>:<本地分支名>
      ```

   - 通常写法，拉取远程 `origin` 的 `main` 分支并合并到本地 `main` 分支

      ```bash
      git pull origin main

   - 如果本地分支已经和远程分支关联，可以直接使用。

      ``` bash
      git pull
      ```

   - 从远程仓库拉取更新，但不合并到本地分支。
     
      ``` bash
      git fetch <远程仓库名>
      #需要后续使用 `git merge <远程仓库名>/<远程分支名>` 来合并
      #通常使用 `git fetch` + `git merge origin/main` 来更新
      ```

## 五、查看历史

### 1. 查看提交历史

   - `git log` : 查看提交历史。
      - `git log --oneline` : 简洁显示提交历史。
      - `git log --graph` : 图形化显示提交历史。
      - `git log --all --graph --decorate --oneline`: 显示所有分支的提交历史，并用图形显示
      - `git log --author="<用户名>"`: 查看指定用户提交历史。
      - `git log --since=<日期>`: 查看指定日期之后的提交历史。
      - `git log -p`: 查看每次提交的更改内容
   - `git reflog` : 查看操作记录（包括分支切换、提交等），可以用于找回被删除的分支或提交。

### 2. 查看文件差异

   - `git diff` : 查看工作区与暂存区的差异。
   - `git diff --cached` : 查看暂存区与最后一次提交的差异。
   - `git diff <commit_id> <commit_id>`: 查看两个 commit 之间的差异。
   - `git diff <branch_name> <branch_name>`: 查看两个分支之间的差异。
   - `git diff <commit_id> <file_name>`: 查看指定 commit 之后，指定文件的变更。

## 六、撤销操作

### 1. 撤销工作区修改

   - `git checkout -- <文件名>` : 撤销对工作区指定文件的修改。

### 2. 撤销暂存区修改

   - `git restore --staged <文件名>`: 从暂存区移除指定的文件。

### 3. 撤销提交

   - `git revert <commit_id>`: 创建一个新的提交，撤销指定提交的更改。
   - `git reset --soft <commit_id>`: 将 HEAD 指针回退到指定提交，保留工作区和暂存区内容。
   - `git reset --mixed <commit_id>`: 将 HEAD 指针回退到指定提交，重置暂存区，保留工作区内容。
   - `git reset --hard <commit_id>`: 将 HEAD 指针回退到指定提交，重置工作区和暂存区，谨慎使用！

## 七、标签操作 (Tag)

### 1. 创建标签

   - `git tag <标签名>`: 基于当前提交创建轻量级标签。
   - `git tag -a <标签名> -m "<标签信息>"`: 创建带注释的标签。
   - `git tag <标签名> <提交ID>`: 基于指定提交创建标签。

### 2. 查看标签

   - `git tag`: 列出所有标签。
   - `git show <标签名>`: 查看标签详细信息。

### 3. 推送标签

   - `git push origin <标签名>`: 推送指定标签到远程仓库。
   - `git push origin --tags`: 推送所有标签到远程仓库。

### 4. 删除标签

   - `git tag -d <标签名>`: 删除本地标签。
   - `git push origin --delete <标签名>`: 删除远程标签。

## 八、其他

### 1.  解决冲突
```markdown
- 当合并分支或者 `pull` 时，如果多个分支修改了同一行代码，则会产生冲突，需要手动修改后，再次 `add` 和 `commit`
- 可以使用 `git status` 来查看哪些文件存在冲突
- 可以使用图形化工具来解决冲突，例如 VS Code 的 Source Control 工具
```
### 2.  `.gitignore` 文件
```markdown
- 可以使用 `.gitignore` 文件来忽略提交，例如忽略 `node_modules` 文件夹
- `.gitignore` 文件只能忽略没有被 `add` 的文件，已经 `add` 的文件需要使用 `git rm --cached <file_name>` 来取消暂存
```

---

**说明**：

- `<>`：表示需要替换的占位符，例如 `<分支名>`、`<远程仓库地址>` 等。
- 选项：`--` 后面的是选项，例如 `--all`, `--oneline` 等。
-  常用命令已加粗。
- 以上仅为常用命令，Git 功能强大，更多命令请参考官方文档。
