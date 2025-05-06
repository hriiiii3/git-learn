# git-learn
# Git与GitHub 实践任务

## 项目简介
本项目记录了我在学习和实践 Git 与 GitHub 过程中所遇到的问题、解决方法及心得体会。通过本次任务，我深入了解了 Git 的使用以及 GitHub 的协作功能，同时解决了上传大文件和 Git 连接问题。

## 学习资料来源

1. **Git 官方文档**
   - 链接：[https://git-scm.com/doc](https://git-scm.com/doc)
   - 说明：Git 的官方文档，全面介绍了 Git 的安装、配置、命令使用以及高级特性。
   
2. **GitHub 官方文档**
   - 链接：[https://docs.github.com/](https://docs.github.com/)
   - 说明：GitHub 的官方文档，涵盖了如何使用 GitHub、协作工作流程、GitHub Pages 等内容。
   
3. **Git Large File Storage (LFS) 文档**
   - 链接：[https://git-lfs.github.com/](https://git-lfs.github.com/)
   - 说明：Git LFS 的官方文档，介绍了如何使用 Git LFS 管理大文件，并将其上传到 GitHub。

## 实践流程

1. **Git 和 GitHub 的基本配置与学习**
   - 阅读 Git 和 GitHub 的文档，了解如何配置本地 Git 环境，如何创建本地 Git 仓库。
   - 创建 GitHub 账户，并学习如何通过 GitHub 的网页界面创建新仓库。

2. **初始化本地 Git 仓库并推送到 GitHub**
   - 在本地计算机上创建项目目录并初始化 Git 仓库：
     ```bash
     git init
     ```
   - 添加文件并提交：
     ```bash
     git add .
     git commit -m "第一次提交 部署版"
     ```
   - 创建远程仓库，并将本地仓库与远程仓库连接：
     ```bash
     git remote add origin https://github.com/hriiiii3/liiuxue.git
     ```
   - 推送到 GitHub：
     ```bash
     git push -u origin master
     ```
   -更改本地项目之后查看文件状态：
    ```bash
     git status
     ```
     -重新提交修改后的文件：
    ```bash
     git add .
     git commit -m "第二次提交，修复了ai问答功能以及Div模型辅助主题分类功能"
     ```
     -查看修改日志：
    ```bash
     git log
     ```
     -返回：
     ```bash
        commit a1595a79b252e0fa39be8d6e89edb24683edad81 (HEAD -> master)
   Author: Rielle Hua <ruihuaiiii3@foxmail.com>
   Date:   Wed May 7 01:07:15 2025 +0800
   
       Add model.safetensors to LFS
   
   commit b0bf0cdbf41b7af5b627b146eaf5f6cf0a72edb8
   Author: Rielle Hua <ruihuaiiii3@foxmail.com>
   Date:   Wed May 7 00:50:43 2025 +0800
   
       第二次提交，修复了ai问答功能以及Div模型辅助主题分类功能
   
   commit c6bce5f38248a9e5fcfe204ac28ec115b1f62b10 (origin/master)
   Author: Rielle Hua <ruihuaiiii3@foxmail.com>
   Date:   Wed May 7 00:15:24 2025 +0800
   
       第一次提交：部署版；项目初始化

     ```

4. **解决上传大文件的难题**
   - 学习并使用 Git Large File Storage（LFS）来上传大文件。因为 GitHub 限制了上传文件的大小（最大 100MB），通过 Git LFS 可以解决这个问题：
     ```bash
     git lfs install
     git lfs track "*.largefile"
     ```
     - 提交并推送大文件：
     ```bash
     git add .gitattributes
     git add path/to/large/file
     git commit -m "Track large file using Git LFS"
     git push origin master
     ```

5. **解决 Git 连接问题**
   - 在推送代码时，遇到连接 GitHub 服务器失败的问题，通过增加 Git 的缓冲区大小（1gb）来解决：
     ```bash
     git config --global http.postBuffer 1048576000
     ```
   - 在更改为 HTTPS 后，遇到网络不稳定的问题，通过配置代理来确保连接的稳定性。

6. **通过 SSH 连接 GitHub**
   - 配置 SSH 密钥并将其添加到 GitHub：
     ```bash
     ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
     ```
   - 修改远程仓库 URL 为 SSH 连接：
     ```bash
     git remote set-url origin git@github.com:hriiiii3/liiuxue.git
     ```

## 遇到的困难及解决方法

1. **Git 提交大文件时超出大小限制**
   - **问题**：GitHub 对单个文件的大小有限制，超过 100MB 的文件不能直接上传。
   - **解决方法**：使用 Git Large File Storage (LFS) 来管理和上传大文件。

2. **推送代码时遇到网络连接问题**
   - **问题**：推送代码时，出现连接中断或 GitHub 服务器无法访问的情况。
   - **解决方法**：增加 Git 的传输缓冲区大小，并在必要时使用代理或切换到更稳定的网络环境。

3. **GitHub 连接超时**
   - **问题**：由于网络问题，无法正常连接 GitHub。
   - **解决方法**：通过配置代理来解决连接超时的问题。

## 心得与总结

1. **Git 和 GitHub 的学习是提高版本管理能力的重要步骤**：通过使用 Git 和 GitHub，我掌握了代码版本控制和团队协作的技能。尤其是在团队合作时，Git 能帮助我们管理代码版本，避免代码冲突。

2. **Git LFS 是处理大文件上传的利器**：通过 Git LFS，我们可以将大文件存储在 GitHub 上而不会超出大小限制，它大大提高了我们处理大型文件的效率。

3. **连接问题的解决需要一定的耐心**：网络问题和 GitHub 的连接问题可能会导致一定的困扰，但通过增加缓冲区、使用代理、切换到 SSH 连接等方法，最终可以找到合适的解决方案。

4. **持续学习和实践是提高的关键**：Git 和 GitHub 是强大的工具，能够提高我们的开发效率和协作能力，持续学习和解决问题将帮助我们更加熟练地掌握这些工具。

## 结语
通过这次的实践任务，我不仅学到了 Git 和 GitHub 的使用技巧，还在实践中解决了很多实际问题，尤其是关于大文件上传和连接稳定性的问题。这些经验让我更加理解版本控制的重要性，并将在未来的开发中持续使用 Git 和 GitHub 来提高工作效率。

