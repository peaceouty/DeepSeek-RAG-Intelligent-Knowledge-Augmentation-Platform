# DeepSeek-RAG-Intelligent-Knowledge-Augmentation-Platform

## Project Introduction
DeepSeek RAG Enhanced Retrieval Knowledge Base System is an intelligent knowledge base backend solution based on Retrieval-Augmented Generation (RAG) technology. The project integrates both Ollama DeepSeek and OpenAI models, supporting document parsing and Git repository analysis capabilities. Users can upload documents or code, and the system will automatically convert them into vector storage, building a dedicated knowledge base that supports question-and-answer retrieval through natural language.

## Technology Stack
### Backend
- **Framework**: Spring Boot
- **Database**: MySQL
- **ORM**: MyBatis-Plus
- **Cache**: Redis
- **Search Engine**: Elasticsearch
- **Message Queue**: Apache Kafka
- **File Storage**: MinIO
- **Document Parsing**: Apache Tika
- **Security Authentication**: Spring Security + JWT
- **AI Integration**: DeepSeek API / Local Ollama + Embedding
- **Real-time Communication**: WebSocket
- **Reactive Programming**: WebFlux

### Frontend
- **Framework**: Vue 3 + TypeScript
- **Build Tool**: Vite
- **UI Components**: Naive UI
- **State Management**: Pinia
- **Routing**: Vue Router
- **Styling**: UnoCSS + SCSS
- **Icons**: Iconify
- **Package Management**: pnpm

## Project Features
### Core Features
1. **Knowledge Base Management**  
   - Supports document upload and parsing, providing chunked upload and resumable transfer functionality.
   - Automatically generates document vector indexes, supporting tag-based management.
   - Provides public and private document permission settings, supporting organizational tag classification.

2. **AI-Driven RAG Implementation**  
   - Chunks documents and generates high-dimensional vectors, stored and retrieved via Elasticsearch.
   - Supports semantic search and keyword search, combined with LLM for document-based precise responses.

3. **Enterprise-Level Multi-Tenant Support**  
   - Implements multi-tenant architecture through organizational tags, supporting independent knowledge base management for teams or departments.
   - Data isolation and access control to ensure security.

4. **Real-time Communication**  
   - Uses WebSocket for real-time interaction between users and the AI system.
   - Frontend adopts SSE technology to push AI-generated content word by word.

## Project Structure
### Backend
```
src/main/java/com/yizhaoqi/smartpai/
├── SmartPaiApplication.java      # Main application entry point
├── client/                       # External API clients
├── config/                       # Configuration classes
├── consumer/                     # Kafka consumers
├── controller/                   # REST API endpoints
├── entity/                       # Data entities
├── exception/                    # Custom exceptions
├── handler/                      # WebSocket handlers
├── model/                        # Domain models
├── repository/                   # Data access layer
├── service/                      # Business logic
└── utils/                        # Utility classes
```

### Frontend
```
frontend/
├── packages/           # Reusable modules
├── public/             # Static resources
├── src/                # Main application code
│   ├── assets/         # SVG icons, images
│   ├── components/     # Vue components
│   ├── layouts/        # Page layouts
│   ├── router/         # Routing configuration
│   ├── service/        # API integration
│   ├── store/          # State management
│   ├── views/          # Page components
│   └── ...             # Other tools and configurations
└── ...                 # Build configuration files
```

## Environment Requirements
Before starting, please ensure the following software is installed:
- Java 17
- Maven 3.8.6 or higher
- Node.js 18.20.0 or higher
- pnpm 8.7.0 or higher
- MySQL 8.0
- Elasticsearch 8.10.0
- MinIO 8.5.12
- Kafka 3.2.1
- Redis 7.0.11
- Docker (optional, for running services like Redis, MinIO, Elasticsearch, and Kafka)

## Quick Start
### Backend Startup
1. Clone the project code:
   ```bash
   git clone https://github.com/peaceouty/DeepSeek-RAG-Intelligent-Knowledge-Augmentation-Platform.git
   cd DeepSeek-RAG-Intelligent-Knowledge-Augmentation-Platform
   ```

2. Configure database and other services:
   - Modify the MySQL, Redis, Kafka, etc., configurations in the `src/main/resources/application.yml` file.

3. Start the backend service:
   ```bash
   mvn spring-boot:run
   ```

### Frontend Startup
1. Enter the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   pnpm install
   ```

3. Start the frontend service:
   ```bash
   pnpm dev
   ```

## Docker Deployment
The project provides a Docker Compose configuration file for quickly starting all dependent services:

```bash
cd docs
docker-compose up -d
```

This will start the following services:
- MySQL database
- Redis cache
- Elasticsearch search engine
- Kafka message queue
- MinIO object storage

## Project Highlights
- 🚀 **High Performance**: Modern architecture based on Spring Boot + Vue 3
- 🔒 **Secure and Reliable**: JWT authentication + Spring Security access control
- 📊 **Intelligent Retrieval**: Hybrid retrieval combining semantic search and keyword search
- 🏢 **Multi-Tenant**: Supports enterprise-level multi-tenant architecture
- 💬 **Real-time Interaction**: WebSocket + SSE for streaming AI conversations
- 📁 **Multi-Format Support**: Automatic parsing of PDF, Word, TXT, and other document formats
- 🔧 **Easy Deployment**: Docker containerized deployment, ready to use out of the box

## Contribution Guidelines
Welcome to submit Issues and Pull Requests to help improve the project!

1. Fork the project
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is open-sourced under the MIT License.

## Contact Information
For any questions, please contact via:
- GitHub Issues: [Project Issue Feedback](https://github.com/peaceouty/DeepSeek-RAG-Intelligent-Knowledge-Augmentation-Platform/issues)
- Project Author: [@peaceouty](https://github.com/peaceouty)
