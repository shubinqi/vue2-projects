<!--
 * @Author: Shu Binqi
 * @Date: 2023-03-11 19:50:39
 * @LastEditors: Shu Binqi
 * @LastEditTime: 2023-03-11 20:07:26
 * @Description: NVM 使用教程
 * @Version: 1.0.0
 * @FilePath: \interviewQuestionsd:\Git\vue2-projects\NVM.md
-->

## NVM 使用教程

### 安装 NVM

```
# 安装完查看版本
nvm version

```

### 安装 node 前配置一下镜像地址

C:\Users\XXX\AppData\Roaming\nvm\setting.txt

把以下两行代码添加到上述路径文件中，XXX 是您的电脑用户名。

```
node_mirror: https://npm.taobao.org/mirrors/node/
npm_mirror: https://npm.taobao.org/mirrors/npm/
```

或者使用命令行配置

```
nvm node_mirror https://npm.taobao.org/mirrors/node/
nvm npm_mirror https://npm.taobao.org/mirrors/npm/
```

### 使用 NVM

1. 查看可安装的版本

```
nvm ls available
```

2. 安装方式 nvm install 版本号

```
# current：当前最新的版本
# LTS：稳定版本

# 以下是三个稳定版本
nvm install 18.15.0
nvm install 16.9.1
nvm install 14.17.0
```

3. 启用、切换指定 NodeJS 版本

```
# 临时版本 - 只在当前命令窗口生效指定版本
nvm use 18.15.0

# 永久版本 - 所有命令窗口生效指定版本
nvm alias default 16.9.1
```

4. 删除指定 NodeJS 版本

```
# 删除某个版本
nvm uninstall 16.9.1
```

5. 查看已安装版本

```
# 显示当前版本
nvm current

# 列出安装好的所有版本
nvm list
```
