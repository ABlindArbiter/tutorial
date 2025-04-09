1. **安装`Git`（首次使用）**

   ```
   sudo apt update
   sudo apt install git
   ```

   检查：

   ```
   git --version
   ```

2. **配置 `Git`**

   配置用户名和邮箱：

   ```
   git config --global user.name "你的GitHub用户名"
   git config --global user.email "你的GitHub注册邮箱"
   ```

3. **生成 `SSH` 密钥：**

   ```
   ssh-keygen -t rsa -b 4096 -C "你的GitHub注册邮箱"
   ```

4. **将公钥添加到 `GitHub` 账户：**

   ```
   cat ~/.ssh/id_rsa.pub
   ```

   复制输出的公钥内容，登录 `GitHub`，进入 `Settings` -> `SSH and GPG keys`，点击 `New SSH key`，将公钥粘贴到相应字段并保存。