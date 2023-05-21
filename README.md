<ul>
  <li><a href="#chinese">中文</a></li>
  <li><a href="#english">English</a></li>
</ul>

<h1>✨ Web 项目目录结构模板 ✨</h1>

<span style="color:#FF0000; font-weight:bold;">项目中的示例代码仅供参考和演示，实际运行时可能需要根据项目需求进行适当修改和调整。</span>

<p>本项目以Go语言作为演示示例，对于其他编程语言，您可以使用此模板，并删除Go语言特定的代码部分。</p>

<p>欢迎来到我们的 Web 项目！这里是我们的项目目录结构，它有助于我们以逻辑和有组织的方式管理和存储代码及相关资源。</p>

<h2 id="chinese">中文</h2>

<pre>
📂 project_root/                   # 项目根目录
├── 📂 .github/                    # GitHub Actions CI/CD配置，issue和PR模板等
│   ├── 📄 .gitlab-ci.yml          # GitLab CI/CD 配置文件
│   ├── 📄 .travis.yml             # Travis CI 配置文件
│   ├── 📄 Jenkinsfile             # Jenkins Pipeline 配置文件
│   └── ...
├── 📂 .docker/                    # docker配置
│   ├── 📄 Dockerfile              # Docker镜像定义文件
│   ├── 📄 docker-compose.yml      # Docker compose配置文件
│   └── 📄 Jenkinsfile             # Jenkins Pipeline 配置文件
│   └── ...
├── 📂 bin/                        # 可执行文件目录
│   ├── 📄 app.exe                 # 应用程序可执行文件
│   └── ...
├── 📂 cmd/                        # 主程序入口，用于启动应用程序和执行命令
│   ├── 📄 main.go                 # 主程序入口，应用程序的入口点
│   └── ...
├── 📂 internal/                   # 内部代码包（不对外公开的模块和功能）
│   ├── 📂 repositories/           # 仓库层，处理与数据库交互的逻辑
│   │   ├── 📄 user_repository.go  # 用户仓库，提供用户数据的持久化和检索
│   │   ├── 📄 order_repository.go # 示例：订单仓库，提供订单数据的持久化和检索
│   │   └── ...
│   ├── 📂 services/               # 服务层，处理应用程序的业务逻辑
│   │   ├── 📄 user_service.go     # 用户服务，包含处理用户相关业务逻辑的方法
│   │   ├── 📄 order_service.go    # 示例：订单服务，包含处理订单相关业务逻辑的方法
│   │   └── ...
│   ├── 📂 usecases/               # Use Cases 层，定义应用程序的用例和业务逻辑
│   │   ├── 📄 user_usecase.go     # 用户用例，定义与用户相关的用例和业务逻辑
│   │   ├── 📄 order_usecase.go    # 示例：订单用例，定义与订单相关的用例和业务逻辑
│   │   └── ...
│   ├── 📂 controllers/            # 控制器层，处理来自路由的请求和生成响应
│   │   ├── 📄 user_controller.go  # 用户控制器，处理与用户相关的请求
│   │   ├── 📄 order_controller.go # 示例：订单控制器，处理与订单相关的请求
│   │   └── ...
│   ├── 📂 routers/                # 路由层，定义和注册路由
│   │   ├── 📄 router.go           # 路由定义和注册
│   │   └── ...
│   └── ...
│   ├── 📂 middleware/             # 中间件层，处理请求和响应之间的一些公共操作
│   │   ├── 📄 authentication.go   # 身份验证中间件，处理身份验证的逻辑
│   │   ├── 📄 logging.go          # 示例：日志中间件，处理请求和响应的日志记录
│   │   └── ...
│   └── ...
│   ├── 📂 models/                 # 模型层，定义应用程序的数据模型和结构
│   │   ├── 📄 user.go             # 用户模型，定义用户数据的结构和字段
│   │   ├── 📂 generated/          # ORM 生成的模型目录
│   │   │   ├── 📄 user_generated.go
│   │   │   ├── 📄 order_generated.go
│   │   └── ...
│   └── ...
├── 📂 pkg/                        # 公共代码包（可供其他项目共享的代码）
│   ├── 📂 utils/                  # 工具包，提供各种通用的工具函数和方法
│   ├── 📂 logging/                # 日志记录包，封装了日志的创建和记录功能
│   ├── 📂 globals/                # 全局变量包，定义和导出全局变量
│   │   ├── 📄 config.go           # 全局配置变量
│   │   └── ...
│   └── ...
├── 📂 web/                        # Web相关文件夹，存放与Web界面和资源相关的文件
│   ├── 📂 static/                 # 静态资源文件夹，包含CSS、JavaScript等静态文件
│   └── 📂 templates/              # 模板文件夹，存放应用程序的视图模板
├── 📂 configs/                    # 配置文件夹
│   ├── 📄 app.yaml                # 应用程序配置文件
│   ├── 📄 db_mssql.ini            # MSSQL 数据库配置文件
│   ├── 📄 db_mysql.ini            # MySQL 数据库配置文件
│   ├── 📄 db_postgres.ini         # PostgreSQL 数据库配置文件
│   └── 📄 example_config.ini      # 示例配置文件
├── 📂 db/                         # 数据库模块，处理数据库相关的操作和管理
│   ├── 📂 migrations/             # 数据库迁移脚本，用于管理数据库结构的变化
│   │   │   ├── 📂 mysql/          # 针对mysql数据库的迁移脚本
│   │   │   ├── 📂 postgresql/     # 针对postgresql数据库的迁移脚本
│   │   │   └── 📂 mssql/          # 针对mssql数据库的迁移脚本
│   └── 📂 seeds/                  # 数据库种子数据，用于填充数据库的初始数据
│   │   │   ├── 📂 mysql/          # 针对mysql数据库的迁移脚本
│   │   │   ├── 📂 postgresql/     # 针对postgresql数据库的迁移脚本
│   │   │   └── 📂 mssql/          # 针对mssql数据库的迁移脚本
├── 📂 scripts/                    # 脚本文件夹，包含各种辅助脚本
│   ├── 📄 build.sh                # 构建脚本，用于自动化构建应用程序
│   ├── 📄 deploy.sh               # 部署脚本，用于自动化部署应用程序
│   ├── 📄 test.sh                 # 示例：测试脚本，用于自动化测试应用程序
│   └── ...
├── 📂 logs/                       # 日志文件夹
│   ├── 📂 app/                    # 应用日志，按日期分类
│   │   ├── 📄 2022-01-01.log      # 示例：2022年1月1日的应用日志
│   │   ├── 📄 2022-01-02.log      # 示例：2022年1月2日的应用日志
│   │   └── ...
│   └── 📂 error/                  # 错误日志，按日期分类
│       ├── 📄 2022-01-01.log      # 示例：2022年1月1日的错误日志
│       ├── 📄 2022-01-02.log      # 示例：2022年1月2日的错误日志
│       └── ...
├── 📂 shared_lib/                 # 存放动态链接库（共享库）
│   ├── 📄 external_lib.dll        # Windows 平台上的外部 DLL 文件示例
│   ├── 📄 external_lib.so         # Linux 平台上的外部动态链接库文件示例
│   └── ...
├── 📂 docs/                       # 文档文件夹，存放项目的文档
│   ├── 📄 README.md               # 项目的README文档
│   ├── 📄 API.md                  # API文档，详细描述应用程序的API接口
│   ├── 📄 CONTRIBUTING.md         # 贡献指南文档，描述如何为项目做贡献
│   ├── 📄 DESIGN.md               # 设计文档，描述项目的设计理念和架构
│   ├── 📄 FAQ.md                  # 常见问题文档，回答一些常见的问题
│   ├── 📄 GUIDE.md                # 用户指南文档，帮助用户理解和使用应用程序
│   └── ...
├── 📂 tests/                      # 测试目录
│   ├── 📂 unit/                   # 单元测试文件夹
│   ├── 📂 integration/            # 集成测试文件夹
│   ├── 📂 system/                 # 系统测试文件夹
│   └── ...
├── 📄 .gitignore                  # Git忽略文件，列出Git应忽略的文件和文件夹
├── 📄 LICENSE                     # 许可证文件
├── 📄 README.md                   # 项目说明文件
└── ...

</pre>

<p>每个文件夹的目的和内容都已在 <code>README.md</code> 文件中明确描述，这使得任何新成员或者外部贡献者都可以很快理解项目的结构和组织。

以上就是我们的项目目录结构！记住，根据项目的需求和你的个人偏好，这个目录结构是可以调整的。祝你在项目中顺利！

<h2 id="english">English</h2>
<h1>✨ Web Project Directory Structure Template ✨</h1>
<span style="color:#FF0000; font-weight:bold;">The sample code in the project is for reference and demonstration purposes only. It may need to be modified and adjusted according to the project requirements during actual implementation.</span>

<p>Welcome to our web project! Here is our project directory structure, which helps us manage and store code and related resources in a logical and organized manner.</p>

<pre>
📂 project_root/                   # Project root directory
├── 📂 .github/                    # GitHub Actions CI/CD configurations, issue and PR templates, etc.
│   ├── 📄 .gitlab-ci.yml          # GitLab CI/CD configuration file
│   ├── 📄 .travis.yml             # Travis CI configuration file
│   ├── 📄 Jenkinsfile             # Jenkins Pipeline configuration file
│   └── ...
├── 📂 .docker/                    # Docker configurations
│   ├── 📄 Dockerfile              # Docker image definition file
│   ├── 📄 docker-compose.yml      # Docker Compose configuration file
│   └── 📄 Jenkinsfile             # Jenkins Pipeline configuration file
│   └── ...
├── 📂 bin/                        # Executable files directory
│   ├── 📄 app.exe                 # Application executable file
│   └── ...
├── 📂 cmd/                        # Main program entry points for starting the application and executing commands
│   ├── 📄 main.go                 # Main program entry, the entry point of the application
│   └── ...
├── 📂 internal/                   # Internal code packages (modules and functionalities not exposed to the outside)
│   ├── 📂 repositories/           # Repository layer, handles logic for interacting with the database
│   │   ├── 📄 user_repository.go  # User repository, provides persistence and retrieval of user data
│   │   ├── 📄 order_repository.go # Example: Order repository, provides persistence and retrieval of order data
│   │   └── ...
│   ├── 📂 services/               # Service layer, handles the business logic of the application
│   │   ├── 📄 user_service.go     # User service, contains methods to handle user-related business logic
│   │   ├── 📄 order_service.go    # Example: Order service, contains methods to handle order-related business logic
│   │   └── ...
│   ├── 📂 usecases/               # Use Cases layer, defines the use cases and business logic of the application
│   │   ├── 📄 user_usecase.go     # User use case, defines use cases and business logic related to users
│   │   ├── 📄 order_usecase.go    # Example: Order use case, defines use cases and business logic related to orders
│   │   └── ...
│   ├── 📂 controllers/            # Controller layer, handles requests from routes and generates responses
│   │   ├── 📄 user_controller.go  # User controller, handles requests related to users
│   │   ├── 📄 order_controller.go # Example: Order controller, handles requests related to orders
│   │   └── ...
│   ├── 📂 routers/                # Router layer, defines and registers routes
│   │   ├── 📄 router.go           # Router definition and registration
│   │   └── ...
│   └── ...
│   ├── 📂 middleware/             # Middleware layer, handles common operations between requests and responses
│   │   ├── 📄 authentication.go   # Authentication middleware, handles authentication logic
│   │   ├── 📄 logging.go          # Example: Logging middleware, handles request and response logging
│   │   └── ...
│   └── ...
│   ├── 📂 models/                 # Model layer, defines the data models and structures of the application
│   │   ├── 📄 user.go             # User model, defines the structure and fields of user data
│   │   ├── 📂 generated/          # Directory for generated ORM models
│   │   │   ├── 📄 user_generated.go
│   │   │   ├── 📄 order_generated.go
│   │   └── ...
│   └── ...
├── 📂 pkg/                        # Public code packages (code shared with other projects)
│   ├── 📂 utils/                  # Utility package, provides various common utility functions and methods
│   ├── 📂 logging/                # Logging package, encapsulates logging creation and recording functions
│   ├── 📂 globals/                # Global variable package, defines and exports global variables
│   │   ├── 📄 config.go           # Global configuration variables
│   │   └── ...
│   └── ...
├── 📂 web/                        # Web-related folders, contains files related to the web interface and resources
│   ├── 📂 static/                 # Static resource folder, contains CSS, JavaScript, and other static files
│   └── 📂 templates/              # Template folder, stores view templates for the application
├── 📂 configs/                    # Configuration folder
│   ├── 📄 app.yaml                # Application configuration file
│   ├── 📄 db_mssql.ini            # MSSQL database configuration file
│   ├── 📄 db_mysql.ini            # MySQL database configuration file
│   ├── 📄 db_postgres.ini         # PostgreSQL database configuration file
│   └── 📄 example_config.ini      # Example configuration file
├── 📂 db/                         # Database module, handles database-related operations and management
│   ├── 📂 migrations/             # Database migration scripts, used for managing changes to the database structure
│   │   │   ├── 📂 mysql/          # Migration scripts for the MySQL database
│   │   │   ├── 📂 postgresql/     # Migration scripts for the PostgreSQL database
│   │   │   └── 📂 mssql/          # Migration scripts for the MSSQL database
│   └── 📂 seeds/                  # Database seed data, used to populate initial data in the database
│   │   │   ├── 📂 mysql/          # Seed data scripts for the MySQL database
│   │   │   ├── 📂 postgresql/     # Seed data scripts for the PostgreSQL database
│   │   │   └── 📂 mssql/          # Seed data scripts for the MSSQL database
├── 📂 scripts/                    # Script folder, contains various auxiliary scripts
│   ├── 📄 build.sh                # Build script, used for automated application building
│   ├── 📄 deploy.sh               # Deployment script, used for automated application deployment
│   ├── 📄 test.sh                 # Example: Test script, used for automated application testing
│   └── ...
├── 📂 logs/                       # Log folder
│   ├── 📂 app/                    # Application logs, categorized by date
│   │   ├── 📄 2022-01-01.log      # Example: Application log for January 1, 2022
│   │   ├── 📄 2022-01-02.log      # Example: Application log for January 2, 2022
│   │   └── ...
│   └── 📂 error/                  # Error logs, categorized by date
│       ├── 📄 2022-01-01.log      # Example: Error log for January 1, 2022
│       ├── 📄 2022-01-02.log      # Example: Error log for January 2, 2022
│       └── ...
├── 📂 shared_lib/                 # Directory for shared libraries
│   ├── 📄 external_lib.dll        # Example external DLL file on Windows platform
│   ├── 📄 external_lib.so         # Example external shared library file on Linux platform
│   └── ...
├── 📂 docs/                       # Documentation folder, contains project documentation
│   ├── 📄 README.md               # Project README documentation
│   ├── 📄 API.md                  # API documentation, provides detailed description of the application's API interfaces
│   ├── 📄 CONTRIBUTING.md         # Contribution guide documentation, describes how to contribute to the project
│   ├── 📄 DESIGN.md               # Design documentation, describes the design principles and architecture of the project
│   ├── 📄 FAQ.md                  # Frequently asked questions documentation, answers common questions
│   ├── 📄 GUIDE.md                # User guide documentation, helps users understand and use the application
│   └── ...
├── 📂 tests/                      # Test directory
│   ├── 📂 unit/                   # Unit tests folder
│   ├── 📂 integration/            # Integration tests folder
│   ├── 📂 system/                 # System tests folder
│   └── ...
├── 📄 .gitignore                  # Git ignore file, lists files and folders to be ignored by Git
├── 📄 LICENSE                     # License file
├── 📄 README.md                   # Project README file
└── ...

</pre>
<p>The purpose and contents of each folder are explicitly described in the <code>README.md</code> file, making it easy for new members or external contributors to quickly understand the project's structure and organization.
That's our project directory structure! Remember, this structure can be adjusted based on the project requirements and your personal preferences. Good luck with your project!</p>
