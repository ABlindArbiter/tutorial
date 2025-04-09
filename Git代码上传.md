1. **初始`Git`仓库：**

   ```
   git init
   ```

2. **添加文件至暂存区：**

   文件夹下所有文件：

   ```
   git add .
   ```

   或 具体文件：

   ```
   git add file1.py file2.py
   ```

3. **将暂存区的文件提交到本地仓库，并添加提交说明：**

   ```
   git commit -m "首次提交代码"
   ```

4. **关联本地仓库和 `GitHub` 远程仓库：**

   ```
   git remote add origin git@github.com:yourusername/your-repo.git
   ```

   ![image-20250409170022901](/home/blind_arbiter/.config/Typora/typora-user-images/image-20250409170022901.png)

5. **推送本地仓库到 `GitHub`：**

   ```
   git push -u origin main
   ```

   这里假设默认分支是 `main`，如果是 `master`，则将 `main` 替换为 `master`。首次推送时加上 `-u` 参数，会将本地分支和远程分支关联起来，以后推送时只需运行 `git push` 即可。

   提交方法：

   1. **先拉取再合并**

      此方法会将远程仓库的更新拉取到本地，然后与本地的修改进行合并。

      ```
      # 拉取远程仓库的更新，但不自动合并
      git fetch origin main
      
      # 将远程分支的更新合并到本地分支
      git merge origin/main
      ```

      执行上述命令后，如果有冲突，`Git `会提示你手动解决冲突。解决冲突的步骤如下：

      1. **查看冲突文件**：使用 `git status` 命令查看哪些文件存在冲突。

      2. **编辑冲突文件**：打开存在冲突的文件，会看到类似下面的冲突标记：

         ```
         <<<<<<< HEAD
         这是本地的修改内容
         =======
         这是远程的修改内容
         >>>>>>> origin/main
         ```

         你需要手动编辑这些内容，决定保留哪些部分，删除冲突标记。

      3. **标记冲突已解决**：编辑完冲突文件后，使用 `git add` 命令将这些文件标记为已解决冲突。

         ```
         git add <冲突文件路径>
         ```

      4. **提交合并结果**：使用 `git commit` 命令提交合并结果。

         ```
         git commit -m "Merge remote changes"
         ```

      5. **推送本地分支到远程仓库**：冲突解决并提交后，再次尝试推送。

         ```
         git push origin main
         ```

   2. **使用 `git pull`**

      `git pull` 实际上是 `git fetch` 和 `git merge` 的组合命令，可以直接执行：

      ```
      git pull origin main
      ```

      同样，如果有冲突，需要按照上述解决冲突的步骤进行处理，处理完后提交更改并推送：

      ```
      git add .
      git commit -m "Merge remote changes"
      git push origin main
      ```

   3. **强制推送（谨慎使用）（覆盖）**

      如果你确定本地的提交是最新的，并且想要覆盖远程仓库的提交，可以使用强制推送，但这会丢失远程仓库中本地没有的提交，所以要谨慎使用。

      ```
      git push -f origin main
      ```

      

