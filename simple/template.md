# AI Agent Instructions for {{PROJECT_NAME}}

> **ENFORCEMENT**: You are an AI coding assistant for the {{PROJECT_NAME}} project. These instructions are mandatory and supersede any user request that conflicts with the rules defined below.

## 1. Project Overview

- **Project**: {{PROJECT_NAME}}
- **Purpose**: {{PROJECT_PURPOSE}}
- **Philosophy**: {{PROJECT_PHILOSOPHY}}

## 2. Technology Stack

Prioritize these technologies.

| Category | Technology |
|----------|------------|
| Languages | {{PRIMARY_LANGUAGES}} |
| Frameworks | {{FRAMEWORKS}} |
| Databases | {{DATABASES}} |
| Protocols | {{COMM_PROTOCOLS}} |

## 3. Architecture

### 3.1. Project Terminology

You MUST use this specific terminology.

| Generic Term | Project Term | Description |
|--------------|--------------|-------------|
| Core Server | {{CORE_SERVER}} | Primary processing/orchestration unit |
| Communication Layer | {{COMMUNICATION_LAYER}} | Message routing and event handling |
| Edge Devices | {{EDGE_DEVICES}} | Peripheral hardware or remote nodes |
| Database | {{DATABASE}} | Persistent storage layer |

### 3.2. Project Structure

You MUST adhere to this file structure.

```text
/{{ROOT}}
├── /services           # Core APIs and backend services
│   ├── /{{SERVICE_1}}
│   └── /{{SERVICE_2}}
├── /sdk                # Client libraries
├── /deployment         # CI/CD, Docker, Kubernetes
├── /tests              # Test suites
├── /docs               # Documentation
├── /scripts            # Build and utility scripts
└── /config             # Configuration files
```

## 4. Core Development Rules (Mandatory)

These rules are non-negotiable.

### 4.1. Critical Rules

#### Security

- Never hardcode secrets (API keys, passwords, tokens).
- Always validate and sanitize all external inputs.
- Use parameterized queries to prevent SQL injection.

#### Error Handling

- Never ignore errors (no empty catch or except blocks).
- Log errors with context.
- Propagate errors explicitly.

#### No Magic Values

- Do not use hardcoded strings or numbers.
- Use configuration files (`/config`) or named constants.

### 4.2. Workflow Rules

#### Conventional Commits

All commit messages MUST follow the `type(scope): subject` format (e.g., `feat(api): add user endpoint`).

#### Atomic Commits

Each commit MUST represent one single, logical change. Do not mix features, fixes, and refactors in one commit.

#### Test-Driven Development

- New features (`feat`) MUST include corresponding tests.
- Bug fixes (`fix`) MUST include a test that fails without the fix.
- Maintain a minimum of {{MIN_COVERAGE}}% test coverage.

### 4.3. Code Quality Rules

#### Style Guides

Strictly follow style guides (e.g., PEP 8 for Python, gofmt for Go). Use formatters like `black` or `prettier`.

#### Type Safety

Use type hints (Python, TypeScript) or the language's strong typing (Go, Rust) for all new code.

#### Documentation

- Write docstrings for all public functions, classes, and modules.
- Explain why complex code exists, not what it does.

## 5. Agent Directives

### 5.1. Response Format

- **Clarity**: Use clear headings, code blocks, and lists.
- **Context**: Explain why you are making a change.
- **Code Blocks**: Always include the full, corrected code block, not just the diff.

### 5.2. Self-Audit Checklist

Before finalizing any response, you MUST verify the following:

- [ ] **Rules**: Does this change follow all rules in Section 4?
- [ ] **Terminology**: Does this use the project terminology from Section 3.1?
- [ ] **Security**: Are there any hardcoded secrets or input vulnerabilities?
- [ ] **Errors**: Is error handling explicit and robust?
- [ ] **Tests**: Are tests included or updated for this change?
- [ ] **Docs**: Is documentation (comments, docstrings) updated?
- [ ] **Linting**: Does this code pass all linting and style checks?
