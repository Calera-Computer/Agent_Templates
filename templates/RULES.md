---
agent_rules:
  version: 1.0
  project: "{{PROJECT_NAME}}"
  purpose: "Enforces coding standards, workflow discipline, and quality gates for AI agents"
  enforcement_mode: "advisory"
  self_audit_required: true
  compatible_tools:
    - git
    - golangci-lint
    - black
    - flake8
    - ruff
    - eslint
    - prettier
    - mypy
    - pytest
    - go_test
    - github_actions
    - gitlab_ci
---

# Agent Development Rules

> **ENFORCEMENT:** You are an expert advisor. You *must* follow these rules. If a user asks for something that violates a rule, you **must advise them of the violation and the risk** and ask for confirmation before proceeding.

---

## 🎯 Rule Hierarchy

**Priority Levels:**
1. **CRITICAL** → Security, data integrity, breaking changes
2. **MANDATORY** → Code standards, testing, documentation
3. **RECOMMENDED** → Performance optimizations, best practices
4. **OPTIONAL** → Style preferences, non-functional improvements

---

## 📂 1. Project Structure Rules

### 1.1 Directory Organization [MANDATORY]

**Enforce logical separation:**
```
/{{PROJECT_NAME}}
  ├── /src            # Source code
  ├── /tests          # Test suites (unit, integration, e2e)
  ├── /docs           # Architecture, API specs, runbooks
  ├── /scripts        # Build, deploy, and utility scripts
  └── /config         # Environment and configuration files
```

**Action required:** If structure is ambiguous or missing, **propose and create** the minimal required hierarchy before generating code.

### 1.2 Naming Conventions [MANDATORY]

**Language-specific rules:**
- **Go:** `PascalCase` (exported), `camelCase` (unexported)
- **Python:** `snake_case` (functions, variables), `PascalCase` (classes)
- **JavaScript/TypeScript:** `camelCase` (variables, functions), `PascalCase` (classes, components)
- **Files:** `snake_case` or `kebab-case` (language-dependent)
- **Constants:** `UPPER_SNAKE_CASE`

**Enforcement:** Never mix conventions within a single module or package.

### 1.3 Modularity [MANDATORY]

**Requirements:**
- Each module must have a **single, well-defined responsibility**
- Modules must be **independently testable**
- Minimize cross-module dependencies
- Explicitly define public interfaces (exports, APIs, contracts)

**Violations to prevent:**
- Circular dependencies
- God objects or modules
- Hidden coupling through global state

---

## 🌿 2. Version Control Rules

### 2.1 Conventional Commits [MANDATORY]

**Format:**
```
<type>(<scope>): <subject>

[optional body]

[optional footer]
```

**Valid types:**
- `feat` → New feature
- `fix` → Bug fix
- `docs` → Documentation changes
- `refactor` → Code restructuring (no behavior change)
- `test` → Test additions or fixes
- `chore` → Build, tooling, dependencies
- `perf` → Performance improvements

**Examples:**
```
feat(api): add user authentication endpoint
fix(mqtt): resolve connection timeout on reconnect
docs(readme): update installation instructions
```

### 2.2 Atomic Commits [MANDATORY]

**Each commit must:**
- Contain ONE logical change
- Be self-contained and reversible
- Pass all tests and linting
- Include relevant test updates

**Prohibited:** Mixed-purpose commits (e.g., feature + refactor + docs in one commit).

### 2.3 Branch Strategy [MANDATORY]

**Branch naming:**
```
feat/<feature-name>
fix/<bug-description>
chore/<task-name>
hotfix/<urgent-fix>
```

**Protection rules:**
- `main` / `master` → Production-ready code only
- `develop` → Integration branch (if using Git Flow)
- Feature branches → Merged via PR/MR after review
- **Never force-push** to protected branches
- **Never commit directly** to `main` without approval

---

## ⚙️ 3. Development Workflow Rules

### 3.1 Definition Before Implementation [CRITICAL]

**Before writing code, define:**
1. **Inputs:** Data types, sources, validation rules
2. **Outputs:** Return types, side effects, state changes
3. **Dependencies:** External services, libraries, modules
4. **Error cases:** Failure modes and handling strategies

**If unclear:** Ask the user to clarify before proceeding.

### 3.2 Incremental Development [MANDATORY]

**Break large tasks into:**
- Small, reviewable units (< 500 lines per PR)
- Independently testable components
- Verifiable milestones

**Each increment should:**
- Compile/run without breaking existing functionality
- Include relevant tests
- Update documentation

### 3.3 Test-Driven Approach [RECOMMENDED]

**For new features:**
1. Write tests first (or alongside code)
2. Ensure tests fail before implementation
3. Implement until tests pass
4. Refactor with tests as safety net

**Minimum coverage targets:**
- Critical paths: 100%
- Core logic: 80%+
- Integration points: 70%+

---

## ✨ 4. Code Quality Rules

### 4.1 Idiomatic Code [MANDATORY]

**Apply language-specific standards:**

| Language | Linter/Formatter | Style Guide |
|----------|------------------|-------------|
| Go | `gofmt`, `golangci-lint` | Effective Go |
| Python | `black`, `ruff`, `mypy` | PEP 8 |
| JavaScript/TypeScript | `eslint`, `prettier` | Airbnb / Standard |
| Rust | `rustfmt`, `clippy` | Rust API Guidelines |

**Enforcement:** Auto-format on save; fail CI if linting errors exist.

### 4.2 No Magic Values [MANDATORY]

**Prohibited:**
```python
# ❌ BAD
timeout = 30
server_url = "http://192.168.1.100:8080"
```

**Required:**
```python
# ✅ GOOD
TIMEOUT_SECONDS = 30  # or from config/env
SERVER_URL = os.getenv("API_SERVER_URL", "http://localhost:8080")
```

**Configuration hierarchy:**
1. Environment variables (production)
2. Config files (development)
3. Named constants (defaults)

### 4.3 Error Handling [CRITICAL]

**Requirements:**
- **Never ignore errors** (no empty `catch`/`except` blocks)
- Use structured logging for errors (include context)
- Propagate errors with sufficient information
- Use typed errors or error codes where applicable

**Examples:**

**Go:**
```go
if err != nil {
    return fmt.Errorf("failed to connect to database: %w", err)
}
```

**Python:**
```python
try:
    result = risky_operation()
except SpecificError as e:
    logger.error("Operation failed", exc_info=e, extra={"context": "value"})
    raise
```

### 4.4 Type Safety [MANDATORY]

**Use type hints/annotations:**
- Python: `typing` module, enforce with `mypy`
- TypeScript: strict mode enabled
- Go: leverage strong typing
- Rust: no `unsafe` without explicit justification

**Example:**
```python
from typing import List, Optional

def process_items(items: List[str], limit: Optional[int] = None) -> dict[str, int]:
    """Process items and return counts."""
    ...
```

---

## ✍️ 5. Documentation Rules

### 5.1 Comment Quality [MANDATORY]

**Explain WHY, not WHAT:**
```python
# ❌ BAD: Increment counter
counter += 1

# ✅ GOOD: Track number of retry attempts for exponential backoff
retry_count += 1
```

**Required documentation:**
- Public APIs: Full docstrings with params, returns, raises
- Complex algorithms: Explain approach and complexity
- Workarounds: Explain issue and link to ticket

### 5.2 README Standards [MANDATORY]

**Each module/service must include:**
```markdown
# Module Name

## Purpose
One-paragraph description

## Installation
Step-by-step setup

## Configuration
Environment variables and config files

## Usage
Basic examples

## API Reference
Key functions/endpoints

## Testing
How to run tests
```

### 5.3 API Documentation [MANDATORY]

**For public APIs:**
- OpenAPI/Swagger for REST
- Protocol Buffers for gRPC
- Inline docs for libraries

**Include:**
- Endpoint/function purpose
- Request/response schemas
- Error codes and meanings
- Usage examples

---

## 🧩 6. Enforcement & Verification Rules

### 6.1 Self-Audit Before Response [MANDATORY]

**Before finalizing any code, verify:**
- [ ] Follows naming conventions
- [ ] No hardcoded secrets or magic values
- [ ] Error handling is explicit
- [ ] Tests are included or updated
- [ ] Documentation is updated
- [ ] Linting passes
- [ ] Security best practices followed

**Output format:**
```
✅ Self-Audit Passed
   - Naming: Compliant
   - Error Handling: Explicit
   - Tests: Added/Updated
   - Documentation: Current
   - Linting: Clean
```

### 6.2 CI/CD Integration [RECOMMENDED]

**Automated checks in pipeline:**
```yaml
# Example: .github/workflows/quality.yml
- name: Lint
  run: make lint
- name: Type Check
  run: make typecheck
- name: Test
  run: make test
- name: Security Scan
  run: make security-scan
```

### 6.3 Security Checklist [CRITICAL]

**Always verify:**
- [ ] No secrets in code or config files
- [ ] Input validation on all external data
- [ ] SQL injection prevention (parameterized queries)
- [ ] XSS prevention (output escaping)
- [ ] Authentication/authorization on protected endpoints
- [ ] Dependency vulnerability scanning

---

## 🚨 Violation Handling

**When rules are broken:**
1. **Identify** the violated rule(s)
2. **Explain** why it's problematic
3. **Propose** compliant alternative
4. **Ask for confirmation** before implementing fix

**Severity levels:**
- **CRITICAL** → Block until fixed
- **MANDATORY** → Warn and require acknowledgment
- **RECOMMENDED** → Suggest improvement

---

**Version:** 1.0  
**Last Updated:** 2025-10-29  
**Compatibility:** LLM agents (Claude, GPT-4, etc.), CI/CD systems, pre-commit hooks
