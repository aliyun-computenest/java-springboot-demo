# 支持Cloud Native Buildpacks构建的Java SpringBoot示例应用
此应用是一个快速入门示例，用于展示支持Cloud Native Buildpacks构建的Java SpringBoot应用。

# 提升Java应用构建成功率
- 本示例应用通过system.properties文件指定了JDK版本，buildpack会读取此版本号。
- 本示例应用通过maven wrapper来构建应用，避免了构建环境maven版本不匹配带来的问题。buildpack会使用mvnw进行构建。
- 本示例应用在project.toml中指定了MAVEN_OPT环境变量，其他构建时的环境变量也可以通过此方式指定。
- 本示例应用Procfile中指定了应用启动命令

# 在阿里云应用管理上部署应用
阿里云应用管理支持从Git仓库部署此应用。可以从以下入口访问应用管理:

- [系统运维管理控制台入口](https://oos.console.aliyun.com/app)
- [云服务器控制台入口](https://ecs.console.aliyun.com/app)
- [计算巢控制台入口](https://computenest.console.aliyun.com/app)

步骤：
1. 在创建应用页面，选择“通过Git仓库创建”
2. 在“应用来源”部分，选择Git平台，授权应用管理使用您的Git平台账号。在“Git clone地址”上填写本仓库的地址
4. 本应用默认应用使用80端口。如需变更，在“应用监听端口”参数指定。
5. 按需修改云服务器的配置。
6. 点击创建后应用开始部署。
7. 部署成功后访问`http://公网IP:端口`

# 手工构建和执行应用

## 使用maven构建
前提条件：下载并安装Java JDK 8
构建应用：`./mvnw clean install`
运行应用：在应用代码所在目录，执行`java -jar target/demo-0.0.1-SNAPSHOT.jar`
打开浏览器，访问`http://localhost`
