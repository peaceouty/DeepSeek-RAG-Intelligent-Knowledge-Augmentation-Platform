# DeepSeek RAG 增强检索知识库系统

## 项目简介
DeepSeek RAG 增强检索知识库系统是一套基于检索增强生成（RAG）技术的智能知识库后端解决方案。项目集成了 Ollama DeepSeek 和 OpenAI 双模型，支持文档解析与 Git 仓库分析能力。用户可以上传文档或代码，系统会自动将其转化为向量存储，构建专属知识库，并支持通过自然语言进行问答检索。

## 技术栈
### 后端
- **框架**: Spring Boot
- **数据库**: MySQL
- **ORM**: MyBatis-Plus
- **缓存**: Redis
- **搜索引擎**: Elasticsearch
- **消息队列**: Apache Kafka
- **文件存储**: MinIO
- **文档解析**: Apache Tika
- **安全认证**: Spring Security + JWT
- **AI集成**: DeepSeek API / 本地 Ollama + Embedding
- **实时通信**: WebSocket
- **响应式编程**: WebFlux

### 前端
- **框架**: Vue 3 + TypeScript
- **构建工具**: Vite
- **UI组件**: Naive UI
- **状态管理**: Pinia
- **路由**: Vue Router
- **样式**: UnoCSS + SCSS
- **图标**: Iconify
- **包管理**: pnpm

## 项目功能
### 核心功能
1. **知识库管理**  
   - 支持文档上传与解析，提供分片上传和断点续传功能。
   - 自动生成文档向量索引，支持标签化管理。
   - 提供公开与私有文档权限设置，支持组织标签分类。

2. **AI驱动的 RAG 实现**  
   - 将文档分块并生成高维向量，通过 Elasticsearch 存储和检索。
   - 支持语义搜索与关键词搜索，结合 LLM 提供基于文档的精准响应。

3. **企业级多租户支持**  
   - 通过组织标签实现多租户架构，支持团队或部门独立管理知识库。
   - 数据隔离与权限控制，确保安全性。

4. **实时通信**  
   - 使用 WebSocket 实现用户与 AI 系统的实时交互。
   - 前端采用 SSE 技术，逐字逐句推送 AI 生成内容。

## 项目结构
### 后端
```
src/main/java/com/deepseek/rag/
├── DeepSeekApplication.java      # 主应用程序入口
├── client/                       # 外部 API 客户端
├── config/                       # 配置类
├── consumer/                     # Kafka 消费者
├── controller/                   # REST API 端点
├── entity/                       # 数据实体
├── exception/                    # 自定义异常
├── handler/                      # WebSocket 处理器
├── model/                        # 领域模型
├── repository/                   # 数据访问层
├── service/                      # 业务逻辑
└── utils/                        # 工具类
```

### 前端
```
frontend/
├── packages/           # 可重用模块
├── public/             # 静态资源
├── src/                # 主应用程序代码
│   ├── assets/         # SVG 图标，图片
│   ├── components/     # Vue 组件
│   ├── layouts/        # 页面布局
│   ├── router/         # 路由配置
│   ├── service/        # API 集成
│   ├── store/          # 状态管理
│   ├── views/          # 页面组件
│   └── ...             # 其他工具和配置
└── ...                 # 构建配置文件
```

## 环境要求
在开始之前，请确保已安装以下软件：
- Java 17
- Maven 3.8.6 或更高版本
- Node.js 18.20.0 或更高版本
- pnpm 8.7.0 或更高版本
- MySQL 8.0
- Elasticsearch 8.10.0
- MinIO 8.5.12
- Kafka 3.2.1
- Redis 7.0.11
- Docker（可选，用于运行 Redis、MinIO、Elasticsearch 和 Kafka 等服务）

## 快速开始
### 后端启动
1. 克隆项目代码：
   ```bash
   git clone https://github.com/your-repo/deepseek-rag.git
   cd deepseek-rag
   ```

2. 配置数据库和其他服务：
   - 修改 `application.yml` 文件中的 MySQL、Redis、Kafka 等配置。

3. 启动后端服务：
   ```bash
   mvn spring-boot:run
   ```

### 前端启动
1. 进入前端目录：
   ```bash
   cd frontend
   ```

2. 安装依赖：
   ```bash
   pnpm install
   ```

3. 启动前端服务：
   ```bash
   pnpm dev
   ```

## 联系方式
如有任何问题，请联系 [your-email@example.com](mailto:your-email@example.com)。
