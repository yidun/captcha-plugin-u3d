# 验证码对应的 Unity package 工程

## 使用方法

下载并解压出 captcha_u3d.unitypackage，在 Assets 目录右键选择 Import Package 导入 captcha_u3d.unitypackage 资源包

其中 Test.cs 是调用事例代码

## iOS 导入NTESVerifyCodeResources.bundle到工程中：

进入`Build Phase`，在`Copy Bundle Resources`选项中，添加`NTESVerifyCodeResources.bundle`文件(请勾选Copy items if needed选项) 。

## 设置 Api

- Init(Options options)
初始化 

Options 是配置项，具体的可配置属性看注释
- ShowCaptcha()

显示验证码

