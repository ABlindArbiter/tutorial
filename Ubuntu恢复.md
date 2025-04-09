# Ubuntu恢复 #

### 下载软件 ###

- ```
  sudo dpkg -i 文件名
  ```

### 硬盘管理

- ```
  sudo apt-get install gparted
  ```

### 显示秒数

- ```
  gsettings set org.gnome.desktop.interface clock-show-seconds true
  ```

### 显示星期

- ```
  gsettings set org.gnome.desktop.interface clock-show-weekday true
  ```

### 亮度调节

- ```
  sudo gedit  /etc/default/grub
  ```

- 第10行改成

- ```
  GRUB_CMDLINE_LINUX_DEFAULT="quiet splash acpi_backlight=vendor acpi_osi=Linux"
  ```

### 时间同步

- ```
  sudo apt install ntpdate
  sudo ntpdate time.windows.com
  sudo hwclock --localtime --systohc
  ```

### 更新

- ```
  sudo apt-get update
  ```

### Qt 安装

- ```
  sudo apt-get install build-essential libgl1-mesa-dev
  sudo chmod +x qt-unified-linux-x64-online.run
  ```

  选择组件中在“Qt”选项下选择版本

- ```
  sudo apt-get install libxcb-cursor0
  ```

- 下载完成，在项目中开启“在终端中运行”

- 使用qmake

### 下载Vim

- ```
  sudo apt-get install vim
  ```

- #### Vim操作

  - ```
    编辑模式
    i 键：在当前光标所在位置前插入文本。
    a 键：在当前光标所在位置后追加文本。
    o 键：在当前行的下方新开一行并进入插入模式。
    O 键：在当前行的上方新开一行并进入插入模式。
    s 键：删除当前光标所在的字符并进入插入模式。
    S 键：删除当前整行并进入插入模式。
    按下 Esc 键进入命令模式：
    删除操作
    x 键：删除当前光标所在的字符。
    dd：删除当前整行。
    dw：删除从当前光标位置到下一个单词开头的内容。
    d$：删除从当前光标位置到行尾的内容。
    替换操作
    r 键：替换当前光标所在的字符。
    R 键：进入替换模式，之后输入的每个字符都会依次替换当前光标位置及后续的字符，直到按下 Esc 键退出替换模式。
    复制和粘贴操作
    yy：复制当前整行。复制后，你可以移动光标到需要粘贴的位置，按下 p 键（在光标所在行的下一行粘贴）或 P 键（在光标所在行的上一行粘贴）进行粘贴。
    yw：复制从当前光标位置到下一个单词开头的内容。同样，复制后使用 p 或 P 进行粘贴。
    撤销和重做操作
    u 键：撤销上一步的操作。
    Ctrl + r：重做上一步被撤销的操作。
    查找和替换
    查找：输入 / 后跟上要查找的关键字，然后按下 Enter 键，Vim 会从当前光标位置开始向下查找该关键字。按 n 键可以继续查找下一个匹配项，按 N 键则反向查找上一个匹配项。
    替换：使用 :%s/old/new/g 命令可以将文本中所有的 old 替换为 new。其中，% 表示对整个文件进行操作，s 是替换命令，g 表示全局替换。如果只想替换当前行的第一个匹配项，可以使用 :s/old/new；如果要替换当前行的所有匹配项，使用 :s/old/new/g。
    保存和退出
    :w：保存文件但不退出 Vim。
    :q：退出 Vim，但前提是文件没有被修改过。
    :wq 或 :x：保存文件并退出 Vim。
    :q!：强制退出 Vim，不保存任何修改。
    ```

### QQ音乐

- 下载完成之后运行：

- ```
  sudo vim /usr/share/applications/qqmusic.desktop
  Exec=/opt/qqmusic/qqmusic --no-sandbox %U
  ```

### 压缩操作

- ```
  zip -r 压缩包 名.zip 文件名
  ```