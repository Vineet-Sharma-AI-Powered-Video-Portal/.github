# AI Powered Video Tutorial Portal

## About Project

The AI Powered Video Tutorial Portal is a comprehensive, full-stack learning platform designed to manage, deliver, and enhance video-based educational content. This enterprise-grade solution combines multiple microservices to create a seamless experience for both content administrators and learners, featuring intelligent content processing, robust API management, and modern user interfaces.

The platform is built with a microservices architecture, allowing each component to be developed, deployed, and scaled independently while working together to provide a unified learning experience.

## Project Overviews

### 📊 Course-Portal-Metadata-Update-Agent
**Title**: Automated Metadata Enrichment Agent  
**Overview**: A Node.js service that automatically scrapes course websites, extracts metadata, downloads images, and updates MongoDB records. Acts as an intelligent agent for keeping course information current.

**Key Features**:
- Web scraping with Cheerio
- Image download and local storage
- MongoDB integration
- Docker containerization
- REST API wrapper

**Endpoints**:
- `POST /api/agent/crawl` - Crawl URL and update course metadata
- **Head**: N/A
- **Count**: N/A

**🔗 [View Detailed README](https://gitlab.com/mvineetsharma/ai-powered-video-tutorial-portal/Course-Portal-Metadata-Update-Agent)**

### 🔍 Courses-Data-Processor
**Title**: Course Content Scanner & Metadata Processor  
**Overview**: Python tool that recursively scans course folder structures, extracts comprehensive metadata, and stores it in MongoDB with configurable conflict resolution strategies.

**Key Features**:
- Recursive folder scanning
- Video file metadata extraction
- SRT subtitle processing
- Dry-run mode for testing
- Comprehensive logging

**Endpoints**:
- CLI tool (no HTTP endpoints)
- **Head**: N/A
- **Count**: N/A

**🔗 [View Detailed README](https://gitlab.com/mvineetsharma/ai-powered-video-tutorial-portal/Courses-Data-Processor)**

### ⚡ Courses-Portal-API-NodeJS
**Title**: Node.js REST API Service  
**Overview**: Express.js-based RESTful API providing core course management functionality with MongoDB integration, centralized logging, and CORS support.

**Key Features**:
- CRUD operations for courses, content, and assets
- Winston and Morgan logging
- Environment-based configuration
- Error handling middleware

**Endpoints**:
- Full CRUD for courses, course contents, section assets
- **Head**: Standard HTTP HEAD support
- **Count**: Collection count endpoints

**🔗 [View Detailed README](https://gitlab.com/mvineetsharma/ai-powered-video-tutorial-portal/Courses-Portal-API-NodeJS)**

### 🐍 Courses-Portal-API-Python
**Title**: FastAPI Advanced API Service  
**Overview**: High-performance Python FastAPI service with advanced features including authentication, ETag support, comprehensive search, and health monitoring.

**Key Features**:
- OpenID Connect & Google OAuth
- ETag-based optimistic concurrency
- Advanced field projection and search
- Comprehensive health checks
- Continue watching functionality

**Endpoints**:
- `GET/POST/PUT/DELETE /api/v1/courses`, `/course-contents`, `/course-section-assets`
- `GET /api/v1/auth/*` - Authentication endpoints
- `GET /api/v1/search/*` - Advanced search
- `GET /health` - System health checks
- `GET /api/v1/continue-watching/*` - User progress
- **Head**: Full HEAD support with ETags
- **Count**: Pagination with total counts

**🔗 [View Detailed README](https://gitlab.com/mvineetsharma/ai-powered-video-tutorial-portal/Courses-Portal-API-Python)**

### 📺 Courses-Portal-Content-Server
**Title**: Fastify Video File Server  
**Overview**: Lightweight, high-performance Node.js server using Fastify to browse and stream video files directly from local filesystems with UnionFS support for multiple source folders.

**Key Features**:
- Fastify framework for high performance
- UnionFS for aggregated file sources
- Video file streaming
- Directory browsing interface
- Minimal configuration

**Endpoints**:
- `GET /` - File browser interface
- `GET /video/*` - Video streaming
- `GET /browse/*` - Directory navigation
- **Head**: Standard file HEAD requests
- **Count**: Directory item counts

**🔗 [View Detailed README](https://gitlab.com/mvineetsharma/ai-powered-video-tutorial-portal/Courses-Portal-Content-Server)**

### ⚛️ Courses-Portal-UI-React
**Title**: React/Next.js Frontend Application  
**Overview**: Modern React application with Next.js 14, featuring App Router, TypeScript, and comprehensive course management interface with Docker support for both development and production.

**Key Features**:
- Next.js 14 with App Router
- TypeScript throughout
- Docker hot-reload development
- Responsive design with SCSS
- Authentication integration

**Endpoints**:
- `GET /` - Home page
- `GET /course/[id]` - Course details
- `GET /admin/*` - Administration
- `GET /api/*` - Next.js API routes
- **Head**: Next.js automatic HEAD
- **Count**: Client-side pagination

**🔗 [View Detailed README](https://gitlab.com/mvineetsharma/ai-powered-video-tutorial-portal/Courses-Portal-UI-React)**

## Purpose

The primary purpose of this platform is to:

- **Centralize Course Management**: Provide a unified system for organizing and managing video tutorials across multiple sources and formats
- **Automate Content Processing**: Intelligently scan, process, and enrich course metadata using AI-powered agents
- **Enable Cross-Platform Access**: Deliver content through responsive web interfaces with continuous watching capabilities
- **Support Scalable Delivery**: Handle large video files efficiently with optimized content serving
- **Provide Intelligent Features**: Implement AI-driven enhancements like content search, recommendations, and metadata enrichment

## Technology Stack

### Backend Services
- **Node.js/Express**: RESTful APIs with MongoDB integration
- **Python/FastAPI**: High-performance APIs with advanced features (ETags, authentication, search)
- **MongoDB**: Primary database for course metadata and user data
- **Docker & Docker Compose**: Containerization and service orchestration

### Frontend
- **React/Next.js**: Modern React framework with App Router
- **TypeScript**: Type-safe development across frontend and backend
- **SCSS**: Modular styling architecture
- **Context API**: State management

### Content Processing
- **Python Scripts**: Course folder scanning and metadata extraction
- **Web Scraping**: Automated metadata enrichment using Cheerio
- **File Processing**: Efficient handling of video files and subtitles

### Authentication & Security
- **OAuth 2.0/OpenID Connect**: Google authentication integration
- **JWT Tokens**: Secure access and refresh token management
- **ETag Validation**: Optimistic concurrency control for data integrity

### Content Delivery
- **Fastify**: High-performance video file serving
- **UnionFS**: Virtual file system for aggregated content sources

## Capabilities

### Core Features
- **Course Management**: Complete CRUD operations for courses, sections, and video content
- **Intelligent Metadata Processing**: Automated extraction and enrichment of course information
- **Advanced Search**: Multi-field search across course content, transcripts, and metadata
- **Continue Watching**: Netflix-style resume playback across devices
- **User Progress Tracking**: Comprehensive viewing history and bookmarking

### Content Processing
- **Automated Scanning**: Recursive folder scanning for course structures
- **Metadata Extraction**: Intelligent parsing of video files, subtitles, and supplementary materials
- **Web Scraping**: External content enrichment from course URLs
- **Image Processing**: Automated thumbnail and image asset management

### API Capabilities
- **RESTful APIs**: Comprehensive endpoints for all entities
- **Field Projection**: Optimized data retrieval with customizable field selection
- **Conditional Requests**: ETag support for efficient caching and conflict prevention
- **Health Monitoring**: Comprehensive system health checks and metrics

### User Experience
- **Responsive Design**: Mobile-first approach across all devices
- **Video Streaming**: Efficient video delivery with browser-based playback
- **Cross-Device Sync**: Seamless continuation of learning across platforms
- **Admin Dashboard**: Complete course management interface

### Security & Performance
- **Authentication**: Flexible auth system with feature flag control
- **Authorization**: Role-based access control for admin features
- **Optimized Queries**: Database-level field projection for performance
- **Containerized Deployment**: Consistent environments across development and production

## API Summary

### Core Endpoints Across Services
- **HEAD Support**: All main APIs support HEAD requests for resource metadata
- **Count Operations**: Paginated responses include total counts
- **Health Checks**: Comprehensive system monitoring endpoints
- **Search**: Advanced multi-field search capabilities
- **Authentication**: OAuth2 and JWT token management

### Key Endpoint Categories

#### Course Management
- `GET /api/v1/courses` - List all courses with pagination
- `POST /api/v1/courses` - Create new course
- `GET /api/v1/courses/{id}` - Get course details
- `PUT /api/v1/courses/{id}` - Update course with ETag support
- `DELETE /api/v1/courses/{id}` - Delete course

#### Content Search
- `GET /api/v1/course-contents/search/transcript` - Search within transcripts
- `GET /api/v1/course-contents/search/multi-field` - Multi-field search
- `POST /api/v1/course-contents/search/advanced` - Advanced search with filters

#### User Features
- `GET /api/v1/continue-watching` - User's progress across courses
- `POST /api/v1/continue-watching` - Update viewing progress
- `GET /api/v1/auth/google/login` - OAuth authentication

#### System Management
- `GET /health` - Comprehensive system health check
- `GET /health/database` - Database connectivity
- `GET /health/system` - Hardware and system metrics

## Roadmap

### Phase 1: Foundation (Current)
- ✅ Core microservices architecture
- ✅ Basic course management
- ✅ Content processing pipeline
- ✅ Authentication system
- ✅ Docker containerization

### Phase 2: Enhancement (Q2 2024)
- **AI-Powered Features**
  - Content recommendations based on viewing patterns
  - Automated transcript analysis and summarization
  - Intelligent course tagging and categorization
  - Personalized learning paths

- **Advanced Analytics**
  - User engagement metrics
  - Course completion analytics
  - Learning pattern insights
  - Performance dashboards

### Phase 3: Scale (Q3 2024)
- **Performance Optimization**
  - CDN integration for global content delivery
  - Database sharding and replication
  - Caching layer implementation
  - Load balancing across services

- **Platform Expansion**
  - Mobile application development
  - Offline viewing capabilities
  - Third-party integrations (LMS, CMS)
  - API rate limiting and monetization

### Phase 4: Intelligence (Q4 2024)
- **Advanced AI Integration**
  - Natural language query processing
  - Automated assessment generation
  - Content gap analysis
  - Predictive learning analytics

- **Enterprise Features**
  - Multi-tenant support
  - Advanced reporting and analytics
  - Compliance and accessibility features
  - Advanced admin controls

### Future Vision
- **Collaborative Learning**: Social features and peer interactions
- **Content Marketplace**: Course publishing and monetization
- **AI Tutors**: Personalized learning assistance
- **VR/AR Integration**: Immersive learning experiences
- **Blockchain Verification**: Credential verification and certification

## Quick Links

- [Frontend Application](./Courses-Portal-UI-React/README.md)
- [Python API Service](./Courses-Portal-API-Python/README.md)
- [Node.js API Service](./Courses-Portal-API-NodeJS/README.md)
- [Content Server](./Courses-Portal-Content-Server/README.md)
- [Data Processor](./Courses-Data-Processor/README.md)
- [Metadata Agent](./Course-Portal-Metadata-Update-Agent/README.md)
