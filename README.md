# Mobile Computing

最小 Kotlin Android 应用工程，使用常规的 Activity + XML 布局，暂无业务功能。启动后显示空白页面。

## 在 Android Studio 中运行

1. 打开本仓库根目录，点击 File → Sync Project with Gradle Files，等待 Gradle Sync 完成。
2. 使用 Android Studio 自带的 JDK（Gradle JDK 17 或更高）。
3. 在 SDK Manager 安装 Android API 37，选择模拟器或连接 Android 7.0 及以上设备。
4. 选择 `app` 运行配置，点击 Run。

工程使用 Android Gradle Plugin 9.3.0 和 Gradle 9.5.0，需要支持该插件版本的 Android Studio。首次同步需要网络下载依赖。

AGP 9 内置 Kotlin 支持，不需要额外添加 `org.jetbrains.kotlin.android` 插件。源码目录 `app/src/main/java/` 同样支持 `.kt` 文件，这是常见的 Android 项目结构。

如果 `app` 运行配置显示红叉：先完成 Gradle Sync，再进入 Run → Edit Configurations，确认 Android App 配置的 Module 选择 `MobileComputing.app`（或列表中的 `app` 模块）。若旧配置仍无效，删除旧运行配置并新建 Android App 配置，选择 `app` 模块和 Default Activity。

命令行构建：`./gradlew assembleDebug`（Windows：`gradlew.bat assembleDebug`）。

`local.properties` 由 Android Studio 为每台电脑生成，不提交到 Git。Gradle Wrapper 文件需要提交；`.idea/`、构建输出和签名密钥已加入 `.gitignore`。
