# iOS_debug
将 Xcode调用第三方应用

## 原理
Xcode 运行时会在 Mac 系统的缓存文件夹(BUILT_PRODUCTS_DIR)里 创建 xxx.app,然后把 xxx.app 安装到手机上去,Xcode本身是可以调试这个xxx.app的.
如果想要让 Xcode 调试第三方app,需要在Xcode运行前 把Xcode创建的 xxx.app 替换成第三方 app.
而 Xcode 本身是可以通过 Run Script 运行 shell 脚本的,把替换 xxx.app 的功能写在这个 shell脚本里就可以实现调试第三方app的作用

## 使用
### 1. 处理待调试app包
脱壳后获取ipa包,解压后把 xxx.app 放在 target_app 目录下
### 2. 指定待调试 app
设置MyScript.sh 里待调试的 app名, TARGET_APP_NAME=xxxx.app
