# {{PROJECT_NAME}}

> {{PROJECT_TAGLINE}}

[![Build Status](https://img.shields.io/github/workflow/status/{{ORG}}/{{REPO}}/CI)](https://github.com/{{ORG}}/{{REPO}}/actions)
[![License](https://img.shields.io/badge/license-{{LICENSE}}-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-{{VERSION}}-green.svg)](CHANGELOG.md)

---

## 📖 Overview

**{{PROJECT_NAME}}** is a {{PROJECT_TYPE}} that {{PROJECT_PURPOSE}}.

**Core Philosophy:** {{PROJECT_PHILOSOPHY}}

### Key Features

- ✅ **{{FEATURE_1}}** - {{FEATURE_1_DESCRIPTION}}
- ✅ **{{FEATURE_2}}** - {{FEATURE_2_DESCRIPTION}}
- ✅ **{{FEATURE_3}}** - {{FEATURE_3_DESCRIPTION}}
- ✅ **{{FEATURE_4}}** - {{FEATURE_4_DESCRIPTION}}

### Use Cases

- **{{USE_CASE_1}}:** {{USE_CASE_1_DESCRIPTION}}
- **{{USE_CASE_2}}:** {{USE_CASE_2_DESCRIPTION}}
- **{{USE_CASE_3}}:** {{USE_CASE_3_DESCRIPTION}}

---

## 🚀 Quick Start

### Prerequisites

- **{{LANGUAGE_1}}** {{VERSION_1}} or higher
- **{{LANGUAGE_2}}** {{VERSION_2}} or higher
- **{{DATABASE}}** {{DB_VERSION}} or higher
- **{{TOOL}}** (for {{TOOL_PURPOSE}})

### Installation

**Option 1: From Source**
```bash
git clone https://github.com/{{ORG}}/{{REPO}}.git
cd {{REPO}}
{{INSTALL_COMMAND_1}}
{{INSTALL_COMMAND_2}}
```

**Option 2: Using Package Manager**
```bash
{{PACKAGE_MANAGER}} install {{PACKAGE_NAME}}
```

**Option 3: Docker**
```bash
docker pull {{DOCKER_IMAGE}}
docker run -p {{PORT}}:{{PORT}} {{DOCKER_IMAGE}}
```

### Basic Usage

```{{CODE_LANGUAGE}}
{{BASIC_USAGE_EXAMPLE}}
```

**Expected Output:**
```
{{EXAMPLE_OUTPUT}}
```

---

## 🏗️ Architecture

### System Components

```
┌─────────────────────────────────────────────┐
│          {{CORE_SERVER}}                    │
│  (Primary processing/orchestration)         │
└──────────────┬──────────────────────────────┘
               │
       ┌───────┴────────┐
       │                │
┌──────▼──────┐  ┌─────▼──────┐
│{{COMPONENT_1}}│  │{{COMPONENT_2}}│
└─────────────┘  └────────────┘
       │                │
       └───────┬────────┘
               │
        ┌──────▼───────┐
        │  {{DATABASE}}  │
        └──────────────┘
```

### Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| **Core** | {{PRIMARY_LANGUAGES}} | Business logic and processing |
| **Framework** | {{FRAMEWORKS}} | Web services and APIs |
| **Database** | {{DATABASES}} | Persistent storage |
| **Communication** | {{COMM_PROTOCOLS}} | Inter-service messaging |
| **Deployment** | {{DEPLOYMENT_TECH}} | Containerization and orchestration |

### Project Structure

```
/{{ROOT}}
├── /services           # Core APIs and backend services
│   ├── /{{SERVICE_1}}  # {{SERVICE_1_DESCRIPTION}}
│   └── /{{SERVICE_2}}  # {{SERVICE_2_DESCRIPTION}}
├── /hardware           # Embedded/device code
├── /sdk                # Client libraries and bindings
│   ├── /{{SDK_LANG_1}} # {{SDK_LANG_1}} client
│   └── /{{SDK_LANG_2}} # {{SDK_LANG_2}} client
├── /deployment         # CI/CD and infrastructure
│   ├── docker-compose.yml
│   ├── kubernetes/
│   └── terraform/
├── /tests              # Test suites
│   ├── /unit
│   ├── /integration
│   └── /e2e
├── /docs               # Documentation
│   ├── /api            # API specifications
│   ├── /architecture   # Design docs
│   └── /runbooks       # Operational guides
├── /scripts            # Build and utility scripts
├── /config             # Configuration files
│   ├── dev.env
│   ├── staging.env
│   └── production.env
├── AGENT.md            # AI agent instructions
├── RULES.md            # Development standards
└── README.md           # This file
```

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the project root:

```bash
# Core Configuration
{{VAR_1}}={{VAR_1_DEFAULT}}           # {{VAR_1_DESCRIPTION}}
{{VAR_2}}={{VAR_2_DEFAULT}}           # {{VAR_2_DESCRIPTION}}

# Database
{{DB_URL_VAR}}={{DB_URL_DEFAULT}}     # {{DB_DESCRIPTION}}
{{DB_POOL_VAR}}={{DB_POOL_DEFAULT}}   # Connection pool size

# API Configuration
{{API_PORT_VAR}}={{API_PORT_DEFAULT}} # API server port
{{API_KEY_VAR}}={{API_KEY_EXAMPLE}}   # API authentication key

# Feature Flags
{{FEATURE_FLAG_1}}={{FLAG_1_DEFAULT}} # {{FEATURE_FLAG_1_DESCRIPTION}}
{{FEATURE_FLAG_2}}={{FLAG_2_DEFAULT}} # {{FEATURE_FLAG_2_DESCRIPTION}}

# Logging
LOG_LEVEL={{LOG_LEVEL_DEFAULT}}       # debug, info, warn, error
LOG_FORMAT={{LOG_FORMAT_DEFAULT}}     # json, text
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
export {{VAR_1}}="production-value"
```

---

## 💻 Development

### Setup Development Environment

```bash
# Clone repository
git clone https://github.com/{{ORG}}/{{REPO}}.git
cd {{REPO}}

# Install dependencies
{{DEV_INSTALL_COMMAND}}

# Setup pre-commit hooks
{{HOOK_SETUP_COMMAND}}

# Start development services
{{DEV_START_COMMAND}}
```

### Development Workflow

1. **Create feature branch:**
   ```bash
   git checkout -b feat/{{FEATURE_NAME}}
   ```

2. **Make changes following [RULES.md](RULES.md)**

3. **Run tests:**
   ```bash
   {{TEST_COMMAND}}
   ```

4. **Lint and format:**
   ```bash
   {{LINT_COMMAND}}
   {{FORMAT_COMMAND}}
   ```

5. **Commit using conventional commits:**
   ```bash
   git commit -m "feat({{SCOPE}}): {{DESCRIPTION}}"
   ```

6. **Push and create pull request:**
   ```bash
   git push origin feat/{{FEATURE_NAME}}
   ```

### Code Standards

This project follows strict development standards defined in **[RULES.md](RULES.md)**:

- ✅ Conventional Commits
- ✅ Atomic, self-contained changes
- ✅ Comprehensive testing (80%+ coverage)
- ✅ Language-specific style guides
- ✅ Explicit error handling
- ✅ No magic values or hardcoded configs

### Running Locally

**Backend Services:**
```bash
cd services/{{SERVICE_NAME}}
{{SERVICE_RUN_COMMAND}}
```

**Frontend (if applicable):**
```bash
cd {{FRONTEND_DIR}}
{{FRONTEND_RUN_COMMAND}}
```

**Full Stack:**
```bash
docker-compose up -d
```

---

## 🧪 Testing

### Unit Tests

```bash
{{UNIT_TEST_COMMAND}}
```

### Integration Tests

```bash
{{INTEGRATION_TEST_COMMAND}}
```

### End-to-End Tests

```bash
{{E2E_TEST_COMMAND}}
```

### Coverage Report

```bash
{{COVERAGE_COMMAND}}
# Report available at coverage/index.html
```

### Test Requirements

- **Critical paths:** 100% coverage
- **Core logic:** 80%+ coverage
- **Integration points:** 70%+ coverage

---

## 📡 API Reference

### Base URL

```
Development: http://localhost:{{API_PORT}}
Staging:     https://staging.{{DOMAIN}}/api
Production:  https://{{DOMAIN}}/api
```

### Authentication

```bash
curl -H "Authorization: Bearer {{TOKEN}}" \
     https://{{DOMAIN}}/api/{{ENDPOINT}}
```

### Key Endpoints

**{{ENDPOINT_1}}**
```http
{{HTTP_METHOD_1}} /api/{{ENDPOINT_1}}
```

**Request:**
```json
{{REQUEST_EXAMPLE_1}}
```

**Response:**
```json
{{RESPONSE_EXAMPLE_1}}
```

**{{ENDPOINT_2}}**
```http
{{HTTP_METHOD_2}} /api/{{ENDPOINT_2}}
```

**Request:**
```json
{{REQUEST_EXAMPLE_2}}
```

**Response:**
```json
{{RESPONSE_EXAMPLE_2}}
```

### Full API Documentation

- **OpenAPI Spec:** [docs/api/openapi.yaml](docs/api/openapi.yaml)
- **Interactive Docs:** http://localhost:{{API_PORT}}/docs
- **Postman Collection:** [docs/api/{{PROJECT_NAME}}.postman_collection.json](docs/api/)

---

## 🚢 Deployment

### Docker Deployment

**Build image:**
```bash
docker build -t {{DOCKER_IMAGE}}:{{VERSION}} .
```

**Run container:**
```bash
docker run -d \
  -p {{PORT}}:{{PORT}} \
  -e {{VAR_1}}={{VALUE_1}} \
  -e {{VAR_2}}={{VALUE_2}} \
  {{DOCKER_IMAGE}}:{{VERSION}}
```

### Kubernetes Deployment

```bash
kubectl apply -f deployment/kubernetes/
kubectl rollout status deployment/{{DEPLOYMENT_NAME}}
```

### CI/CD Pipeline

**GitHub Actions:**
```yaml
# .github/workflows/deploy.yml
name: Deploy
on:
  push:
    branches: [main]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Deploy to {{ENVIRONMENT}}
        run: {{DEPLOY_COMMAND}}
```

### Health Checks

```bash
# Health endpoint
curl http://localhost:{{PORT}}/health

# Metrics
curl http://localhost:{{PORT}}/metrics
```

---

## 🤖 AI Agent Integration

This project includes AI agent configuration files for automated development:

- **[AGENT.md](AGENT.md)** - Instructions for AI coding agents
- **[RULES.md](RULES.md)** - Development standards and enforcement rules

### Using with LLM Agents

```bash
# Include in agent context
agent-cli --context AGENT.md,RULES.md --task "{{TASK_DESCRIPTION}}"
```

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Read the standards:** [RULES.md](RULES.md)
2. **Fork the repository**
3. **Create a feature branch:** `git checkout -b feat/amazing-feature`
4. **Follow coding standards:** See [RULES.md](RULES.md)
5. **Write tests:** Maintain coverage requirements
6. **Commit changes:** Use conventional commits
7. **Push to branch:** `git push origin feat/amazing-feature`
8. **Open pull request:** Include description and link to issue

### Contributor Guidelines

- ✅ All PRs must pass CI/CD checks
- ✅ Code must be reviewed by at least {{MIN_REVIEWERS}} maintainers
- ✅ Tests must pass with {{MIN_COVERAGE}}%+ coverage
- ✅ Documentation must be updated for API changes
- ✅ Follow [Conventional Commits](https://www.conventionalcommits.org/)

---

## 📋 Roadmap

- [x] {{COMPLETED_FEATURE_1}}
- [x] {{COMPLETED_FEATURE_2}}
- [ ] {{PLANNED_FEATURE_1}} (v{{NEXT_VERSION}})
- [ ] {{PLANNED_FEATURE_2}} (v{{NEXT_VERSION}})
- [ ] {{FUTURE_FEATURE_1}} (Future)

See [CHANGELOG.md](CHANGELOG.md) for detailed version history.

---

## 📄 License

This project is licensed under the **{{LICENSE}}** - see the [LICENSE](LICENSE) file for details.

---

## 📞 Support & Contact

- **Documentation:** [docs/](docs/)
- **Issues:** [GitHub Issues](https://github.com/{{ORG}}/{{REPO}}/issues)
- **Discussions:** [GitHub Discussions](https://github.com/{{ORG}}/{{REPO}}/discussions)
- **Email:** {{CONTACT_EMAIL}}
- **Slack/Discord:** {{COMMUNITY_LINK}}

---

## 🙏 Acknowledgments

- {{ACKNOWLEDGMENT_1}}
- {{ACKNOWLEDGMENT_2}}
- {{ACKNOWLEDGMENT_3}}

---

## 📝 Template Configuration

**To customize this README, replace all `{{PLACEHOLDERS}}`:**

| Placeholder | Purpose | Example |
|-------------|---------|---------|
| `{{PROJECT_NAME}}` | Project name | "Atlas", "DataForge" |
| `{{PROJECT_TAGLINE}}` | One-line description | "Distributed IoT platform" |
| `{{ORG}}` | GitHub organization | "acme-corp" |
| `{{REPO}}` | Repository name | "atlas-platform" |
| `{{LICENSE}}` | License type | "MIT", "Apache-2.0" |
| `{{VERSION}}` | Current version | "1.0.0" |
| `{{PRIMARY_LANGUAGES}}` | Main languages | "Go, Python, TypeScript" |
| `{{FRAMEWORKS}}` | Core frameworks | "Fiber, FastAPI, React" |
| `{{DATABASES}}` | Database systems | "PostgreSQL, Redis" |
| `{{COMM_PROTOCOLS}}` | Communication protocols | "MQTT, gRPC, WebSockets" |
| `{{API_PORT}}` | API server port | "8080", "3000" |
| `{{DOCKER_IMAGE}}` | Docker image name | "acme/atlas" |

---

**Version:** 1.0  
**Last Updated:** 2025-10-29  
**Template Compatibility:** Universal projects, works with AGENT.md and RULES.md

