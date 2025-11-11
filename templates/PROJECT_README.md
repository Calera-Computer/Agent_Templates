# {{PROJECT_NAME}}

> A {{PROJECT_TYPE}} built with {{PRIMARY_LANGUAGES}}

[![Build Status](https://img.shields.io/github/workflow/status/your-org/{{PROJECT_NAME}}/CI)](https://github.com/your-org/{{PROJECT_NAME}}/actions)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-0.1.0-green.svg)](CHANGELOG.md)

---

## 📖 Overview

**{{PROJECT_NAME}}** is a {{PROJECT_TYPE}} that provides core functionality and services.

**Core Philosophy:** Simple, maintainable {{PROJECT_TYPE}}

### Key Features

- ✅ **Core Functionality** - Essential features for the project
- ✅ **API Integration** - RESTful API endpoints
- ✅ **Configuration Management** - Environment-based configuration
- ✅ **Documentation** - Comprehensive documentation and examples

### Use Cases

- **Development:** Local development and testing
- **Production:** Deployable production-ready application
- **Integration:** Easy integration with other services

---

## 🚀 Quick Start

### Prerequisites

- **{{PRIMARY_LANGUAGES}}** (latest stable version)
- **Docker** (optional, for containerized deployment)

### Installation

**Option 1: From Source**
```bash
git clone https://github.com/your-org/{{PROJECT_NAME}}.git
cd {{PROJECT_NAME}}
# Follow language-specific installation steps
```

**Option 2: Docker**
```bash
docker pull your-org/{{PROJECT_NAME}}
docker run -p 8080:8080 your-org/{{PROJECT_NAME}}
```

### Basic Usage

```bash
# Start the application
./start.sh

# Or use language-specific commands
# python main.py
# go run main.go
# npm start
```

---

## 🏗️ Architecture

### System Components

```
┌─────────────────────────────────────────────┐
│          CoreService                         │
│  (Primary processing/orchestration)          │
└──────────────┬──────────────────────────────┘
               │
       ┌───────┴────────┐
       │                │
┌──────▼──────┐  ┌─────▼──────┐
│   Service   │  │   Service  │
└─────────────┘  └────────────┘
       │                │
       └───────┬────────┘
               │
        ┌──────▼───────┐
        │   Storage    │
        └──────────────┘
```

### Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| **Core** | {{PRIMARY_LANGUAGES}} | Business logic and processing |
| **Framework** | (Framework based on language) | Web services and APIs |
| **Database** | {{DATABASES}} | Persistent storage |
| **Communication** | REST/HTTP | Inter-service messaging |
| **Deployment** | Docker | Containerization |

### Project Structure

```
/{{PROJECT_NAME}}
├── /src              # Source code
├── /tests            # Test suites
│   ├── /unit
│   ├── /integration
│   └── /e2e
├── /docs             # Documentation
├── /config           # Configuration files
│   ├── dev.env
│   ├── staging.env
│   └── production.env
├── /scripts          # Build and utility scripts
├── AGENT_CONTEXT.md  # AI agent context and rules
└── README.md         # This file
```

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the project root:

```bash
# Core Configuration
APP_ENV=development
APP_PORT=8080

# Database (if applicable)
DATABASE_URL={{DATABASE_URL_EXAMPLE}}
DB_POOL_SIZE=10

# API Configuration
API_PORT=8080
API_KEY=your-api-key-here

# Logging
LOG_LEVEL=info
LOG_FORMAT=json
```

### Configuration Files

**Development:**
```bash
cp config/dev.env.example config/dev.env
# Edit config/dev.env with your settings
```

**Production:**
```bash
# Use environment variables or secrets management
export APP_ENV="production"
```

---

## 💻 Development

### Setup Development Environment

```bash
# Clone repository
git clone https://github.com/your-org/{{PROJECT_NAME}}.git
cd {{PROJECT_NAME}}

# Install dependencies
# (Use language-specific package manager)

# Setup pre-commit hooks (if configured)
# pre-commit install

# Start development server
# (Use language-specific command)
```

### Development Workflow

1. **Create feature branch:**
   ```bash
   git checkout -b feat/feature-name
   ```

2. **Make changes following [AGENT_CONTEXT.md](AGENT_CONTEXT.md)**

3. **Run tests:**
   ```bash
   # Use language-specific test command
   ```

4. **Lint and format:**
   ```bash
   # Use language-specific lint/format commands
   ```

5. **Commit using conventional commits:**
   ```bash
   git commit -m "feat(scope): description"
   ```

6. **Push and create pull request:**
   ```bash
   git push origin feat/feature-name
   ```

### Code Standards

This project follows strict development standards defined in **[AGENT_CONTEXT.md](AGENT_CONTEXT.md)**:

- ✅ Conventional Commits
- ✅ Atomic, self-contained changes
- ✅ Comprehensive testing (80%+ coverage)
- ✅ Language-specific style guides
- ✅ Explicit error handling
- ✅ No magic values or hardcoded configs

---

## 🧪 Testing

### Unit Tests

```bash
# Run unit tests
# (Use language-specific test command)
```

### Integration Tests

```bash
# Run integration tests
# (Use language-specific test command)
```

### Test Requirements

- **Critical paths:** 100% coverage
- **Core logic:** 80%+ coverage
- **Integration points:** 70%+ coverage

---

## 📡 API Reference

### Base URL

```
Development: http://localhost:8080
Staging:     https://staging.example.com/api
Production:  https://api.example.com
```

### Authentication

```bash
curl -H "Authorization: Bearer YOUR_TOKEN" \
     https://api.example.com/endpoint
```

### Full API Documentation

- **OpenAPI Spec:** [docs/api/openapi.yaml](docs/api/openapi.yaml)
- **Interactive Docs:** http://localhost:8080/docs

---

## 🚢 Deployment

### Docker Deployment

**Build image:**
```bash
docker build -t your-org/{{PROJECT_NAME}}:0.1.0 .
```

**Run container:**
```bash
docker run -d \
  -p 8080:8080 \
  -e APP_ENV=production \
  your-org/{{PROJECT_NAME}}:0.1.0
```

### Health Checks

```bash
# Health endpoint
curl http://localhost:8080/health

# Metrics
curl http://localhost:8080/metrics
```

---

## 🤖 AI Agent Integration

This project includes AI agent configuration for automated development:

- **[AGENT_CONTEXT.md](AGENT_CONTEXT.md)** - Unified context and rules for AI coding agents, with operational modes (design, implementation, debug)

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Read the standards:** [AGENT_CONTEXT.md](AGENT_CONTEXT.md)
2. **Fork the repository**
3. **Create a feature branch:** `git checkout -b feat/amazing-feature`
4. **Follow coding standards:** See [AGENT_CONTEXT.md](AGENT_CONTEXT.md)
5. **Write tests:** Maintain coverage requirements
6. **Commit changes:** Use conventional commits
7. **Push to branch:** `git push origin feat/amazing-feature`
8. **Open pull request:** Include description and link to issue

### Contributor Guidelines

- ✅ All PRs must pass CI/CD checks
- ✅ Code must be reviewed by at least 1 maintainer
- ✅ Tests must pass with 80%+ coverage
- ✅ Documentation must be updated for API changes
- ✅ Follow [Conventional Commits](https://www.conventionalcommits.org/)

---

## 📋 Roadmap

- [ ] Initial release (v0.1.0)
- [ ] Enhanced features (v0.2.0)
- [ ] Performance improvements (v0.3.0)

See [CHANGELOG.md](CHANGELOG.md) for detailed version history.

---

## 📄 License

This project is licensed under the **MIT** - see the [LICENSE](LICENSE) file for details.

---

## 📞 Support & Contact

- **Documentation:** [docs/](docs/)
- **Issues:** [GitHub Issues](https://github.com/your-org/{{PROJECT_NAME}}/issues)
- **Discussions:** [GitHub Discussions](https://github.com/your-org/{{PROJECT_NAME}}/discussions)

---

**Version:** 1.0  
**Last Updated:** 2025-10-29  
**Template Compatibility:** Universal projects, works with AGENT_CONTEXT.md
