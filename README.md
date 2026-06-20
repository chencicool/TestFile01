# GitHub Pages 实训操作记录
## 一、实训目标
通过SSH密钥鉴权、Git版本控制、GitHub Pages静态托管，搭建免费静态网页站点。

## 二、完整操作步骤
1. 注册登录GitHub，新建公开仓库TestFile01，勾选README，初始化main分支。
2. 网页端创建docs/index.html首页，替换两处REPLACE ME占位符为仓库名TestFile01并提交。
3. 虚拟机Ubuntu生成ED25519 SSH密钥对，复制公钥上传GitHub账号SSH配置，测试连通ssh -T git@github.com。
4. 使用SSH地址克隆仓库到本地虚拟机：
mkdir repos
cd repos
git clone git@github.com:chencicool/TestFile01.git
5. 进入docs目录，安装net-tools工具，执行管道命令抓取本机IP，生成ipaddresses.html页面。
6. 编辑index.html，添加iframe嵌入IP展示页面。
7. 新建docs/404.html自定义404错误页面。
8. Git本地提交推送：
git add .
git config user.name "chencicool"
git config user.email "5273405@qq.com"
git commit -m "完成网页编写、新增404页面"
git push origin main
9. 仓库Settings-Pages配置部署源：main分支、/docs文件夹，开启Pages服务。
10. 访问站点地址：https://chencicool.github.io/TestFile01/ 验证网站效果。

## 三、操作中遇到的问题与解决方案
1. VMware Install VMware Tools按钮灰色：改用命令sudo apt install open-vm-tools open-vm-tools-desktop安装工具，实现双向复制粘贴。
2. GitHub Pages Save按钮点击无响应：刷新页面后等待自动部署，最终部署成功。
3. nano编辑器不会退出：先Ctrl+O保存，回车确认，再Ctrl+X退出。

## 四、实训原理总结
1. SSH非对称加密：公私钥配对免密操作GitHub仓库，无需账号密码。
2. Git三区模型：工作区→暂存区git add→本地仓库git commit→远端仓库git push。
3. GitHub Pages CD自动部署：监听main分支docs文件夹，代码推送后自动构建静态网站。
4. 静态网页机制：仅HTML前端文件，无后端，服务器直接分发页面资源。# TestFile01
