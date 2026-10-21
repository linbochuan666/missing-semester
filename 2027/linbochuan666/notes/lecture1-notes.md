# 27赛季DynamicX第一节培训课笔记 
>内容：Linux、 Vim && Shell、Git && GitHub
## Linux 基础
- ***Windows,macOS与Linux***  
  - Windows ：常见于个人桌面。软件、游戏生态丰富   
    macOS   ：Apple生态。日常使用与开发  
    Ubuntu(linux)：服务器、机器人、嵌入式。也可以作为桌面系统    
- ***Linux与发行版***  
  - **Ubuntu | Debian | Fedora | Arch Linux**
  - 团队使用Ubuntu：ROS兼容性、部署一致性和现有开发生态  
- ***机器人开发中的Linux***  
  - 开发电脑----(SSH/网络)--->Ubuntu Server--------->ROS节点/控制程序
  - *C++工具链、SSH远程开发、服务自动启动*
- ***Linux的目录从 / 开始***
  - *路径大小写敏感;  ~ 是当前用户的家目录,  .是当前目录,  ..是上一级*
  - / 

    |  目录路径|功能说明  |     
    | :--- | :--- | 
    | `/home/user` | 用户文件 |  
    | `/etc` | 系统配置 |        
    | `/usr` | 程序与库 |        
    | `/var` | 日志等可变数据 |   
    | `/dev` | 设备文件 |         
    

    |路径示例|类型/含义|
    |:---|:---|
    |`/home/user/example`|绝对路径：从/开始|
    |`./hello.txt`|相对路径：从当前位置开始|
    |` ~/example`|home目录中的example；~为快捷用法相当/home/user|
    
    ---
## Shell 与 Vim
### Shell
- ***Shell命令的结构***
  | **ls** | **-la** | **~/projects**|
  |:---|:---|:---|
  |**命令** | **选项**| **参数**|
  |做什么| 怎样执行 | 操作哪个对象|
  | | -l详细信息，-a含隐藏项|这里是目标目录  

- ***当前位置与目录切换***  
  - ~ home目录 -------> example  
    相对路径以当前位置为起点  
  -
    | **命令** | **作用** |
    |:--- | :---|
    | pwd | 显示当前目录|
    |ls | 列出目录内容|
    |cd目录 | 进入指定目录|
    |cd..| 返回上一级
    |cd~| 返回家目录|  

- ***文件和目录操作***
  |**命令**|**作用** | **示例**|
  |:---|:---|:---|
  |`mkdir -p`| 创建目录，允许补齐父目录|`mkdir -p ~/linux_demo`|
  |`touch`|创建空文件/更新时间|`touch hello.txt`|
  |`cp`|复制文件|`cp hello.txt hello-copy.txt`|
  |`rm`|删除文件|`rm backup.txt`|
  |`cat/less`|直接查看/分页查看|`cat hello.txt`|  

- ***Shell的四种常用组合***
    | 功能类型| 语法示例| 作用说明|
    |:---|:---|:---|
    |**变量**|`name="RM" echo"$name" `|保存一个值，再通过变量引用它|
    |**重定向**|`echo "hello">hello.txt`|>覆盖写入;>>追加到文件末尾|
    |**管道**|`ls -la ; grep txt`| 将输出交给下一个程序|
    |**条件连接**|`mkdir -p demo && cd demo`|前一条成功后，再执行下一条|  

- ***陌生命令的帮助入口***
    | 操作| 功能说明|
    |:--- |:---|  
    |**`ls --help`**| 快速查看选项和用法|
    |**`man ls`**| 打开手册，按q退出|
    |**`Tab`**|补全命令或路径|
    |**`↑/↓`**|调出历史命令|
### Vim
- ***Vim模式与必备按键***  
```txt
             i  
  普通模式----------->插入模式   
    ⬇️           Esc返回普通模式 
    ⬇️ 普通模式按：  
    命令行输入
    :w   :q   :wq   :q!
    :w保存; :q退出; :wq保存退出; :q!放弃修改退出
```
 


- ***Vim基本使用***  
  | 命令| 作用|
  |:---|:---|
  |`vim name.txt`|打开文件|
  |`h  j  k  l`|左 下 上 右|
  |`i`|插前|
  |`a`|附后|
  |`o`|新增下一行
  |`O`|新增上一行
  |`G`|到最后一行
  |`gg`|到第一行
  |`yy`|复制当前行
  |`dd`|剪切当前行|
  |`.`|重复前次操作|
  |`u`|撤销前次操作|
  |Ctrl+r|恢复前次操作|
  |`dw`|删除单词|
  |`cw`|改变单词|
  |`yw`|复制单词|
  |`w`|下个单词首部|
  |`e`|下个单词尾部|
  |`b`|上个单词首部|
  |`/word`|搜索单词|
  |`:%s/旧字符/新字符/g`|全局替换|
  |`p`|粘贴|
  |`np`|粘贴n次|
  |`ci{`|删除括号内的内容|
  |Ctrl+v|可视化块|
  |Shift+v|可视化行|
  ---

## Git 与 GitHub
- ***Git与GitHub的分工***
  - Git:本地版本控制工具
    - 记录每次提交
    - 比较修改、查看历史
    - 为新功能创建分支
  - GitHub:远程托管与协助的平台
    - 托管Git仓库
    - 通过PR讨论和评审
    - 合并团队认可的修改
- ***Git的四个位置***
  ```txt
               git add          git commit           git push
        工作区------------>暂存区------------->本地仓库---------->GitHub远程仓库
  (实际编辑代码的地方)(临时存放准备提交的修改)(保存已提交的历史版本) （云端备份与协助中心）
  ```

- ***首次配置***  
  安装Git后，必须设置用户名和邮箱，否则无法提交
  - git config --global user.name"Your Name"
  - git config --global user.email"you@example.com" 
  - 查看配置是否生效：git config --list 
  **提交作者信息**：回答“这次修改由谁提交”  
  **SSH认证**  ：证明你有权访问远程仓库  
  

- ***SSH密钥***  
  一、SSH密钥是什么
    SSH密钥是一对用于身份验证的加密文件，包含私钥和公钥两部分
    - 私钥：留在本地电脑，绝不能泄漏或分分享。它用于向服务器证明“你是你”。
    - 公钥：可以安全地交给GitHub等平台。GitHub保存个人的公钥后，当个人通过SSH操作时，会用公钥来验证个人是否持有对于的私钥。
    - **总的来说**：公钥在GitHub,私钥在个人的电脑，两者匹配即通过验证，从而免去每次输入账号密码的麻烦。  
  
  二、检查是否已有密钥  
  - ls -al -/.ssh  

  三、生存SSH密钥并连接  
  - **生成密钥：ssh-keygen -t ed25519 -C "你的GitHub邮箱"**
  **复制公钥内容：cat ~/.ssh/id_ed25519.pub**

    |**公钥.pub**|**私钥**|
    |:---|:---|
    |id_ed25519.pub|id_ed25519|
    |复制到GitHub的SSH设置|不上传、不截图、不分享|  
    
  - ***把SSH公钥添加到GitHub***
  在GitHub界面中  
  1.Settings
  2.选择SSH and GPS keys
  3.点击New SSH key  
  4.Tittle填写一个名称
  5.Key粘贴刚才复制的公钥内容
  6.点击Add SSH key确认
  - ***将私钥添加到ssh-agent***
   #启动ssh-agent
   `eval "$(ssh-agent -s)"`
   #添加私钥
   `ssh-add ~/.ssh/id_ed25519` 
  - ***测试连接***
  输入：`ssh -T git@github.com`
  成功了看到：Hi 个人用户名! You're Successfullyauthenticated....

- ***Git常用命令***
  - 获取与查看
   
    |命令|作用|
    |:---|:---|
    |git init|在当前目录初始化新仓库|
    |git clone <仓库地址>|克隆远程仓库到本地|
    |git status|查看当前分支和文件状态|
    |git diff|查看尚未缓存的修改|
    |git log --online|用简短格式查看提交历史|

  - 分支与提交
    |命令|作用|
    |:---|:---|
    |git switch -c feature/hello|创建并切换到功能分支|
    |git add hello.txt|暂存指定文件|
    |git commit -m "Add greeting"|记录一次本地提交|
    |git push -u orgin feature/hello|推送并建立跟踪关系|
    |git switch main|切回主分支|
    |git pull|获取并整合当前分支的远程更新|

- ***分支：为新功能保留独立开发线***
  - main保持稳定，feature/hello承载本次修改，评审后再合并  
  ```txt
          从当前版本创建分支  
  main-------------->（）---------------->（）
   ⬇️                                     ⬆️
   ⬇️                                     ⬆️PR/Review/Merge
   ⬇️                                     ⬆️
  feature/hello---------->()------------->()
     分支
  ```

- ***团队PR工作流***
  - 默认使用Fork协作：远程复制仓库，再向团队发起合并请求
  - GitHub:Fork是仓库副本
  Branch是仓库内的开发线
  ```txt
  团队仓库 ➡️ 个人Fork 
               ⬇️
    (本地电脑) Clone ➡️ Feature分支 ➡️ 修改/Add/Commit ➡️ Push
                                                         ⬇️
  (GitHub协作)Merge到团队仓库 ⬅️ Review评审 ⬅️ 发起PR ⬅️ 个人Fork接收提交  
  ```

- ***一次团队贡献的完整过程***
  - 现在可以把Linux环境、终端操作和团队协作串起来
  
  ```txt
    Linux  ➡️➡️➡️  Shell  ➡️➡️➡️  Vim  ➡️➡️➡️  Git  ➡️➡️➡️  GitHub
  进入开发环境    定位与操作文件   编辑文件内容   分支、暂存与提交  PR、评审与合并
  ```
  - **Git记录版本，GitHub支持协作。**
 

