# Dark Factory Template Parts

Modular, language-specific templates that can be composed to bootstrap new projects.

## Structure

```
template-parts/
├── README.md                          # This file
├── go/                               # Go module template
│   ├── README.md
│   ├── cmd/app/main.go               # Entry point with graceful shutdown
│   ├── internal/
│   │   ├── api/
│   │   │   ├── server.go            # HTTP server
│   │   │   └── middleware.go        # CORS, auth, logging middleware
│   │   ├── logger/
│   │   │   └── logger.go           # slog-based structured logging
│   │   └── config/
│   │       └── config.go           # Configuration management
│   ├── db/migrations/
│   │   └── 001_initial.sql         # Example migration
│   └── _fixtures/
│       └── example_test.go         # Test patterns
├── python/                           # Python project template
├── typescript/                       # TypeScript project template
├── rust/                             # Rust project template
├── e2e-testing/
│   ├── README.md
│   ├── framework/
│   │   ├── harness.go              # Test harness + setup/teardown
│   │   ├── session.go              # Test session management
│   │   ├── reporter.go             # Multi-format reporter
│   │   ├── debugger.go             # Debug utilities
│   │   └── ai_coverage.go         # AI-driven coverage analyzer
│   └── tests/
├── code-library/
│   ├── README.md
│   └── snippets/
│       ├── go/                      # Go code snippets
│       ├── python/                  # Python code snippets
│       ├── bash/                    # Bash code snippets
│       └── common/
│           ├── git_hooks.sh         # Hook installation helpers
│           └── ci_validation.sh    # CI validation patterns
├── common/
│   ├── CLAUDE.md                    # AI instruction template
│   ├── AGENTS.md                    # Agent behavior rules
│   ├── .claude/settings.json       # Claude Code MCP settings
│   └── .github/
│       ├── CODEOWNERS               # Parameterized code owners
│       ├── PULL_REQUEST_TEMPLATE.md
│       ├── FUNDING.yml
│       ├── dependabot.yml
│       └── ISSUE_TEMPLATE/
├── atheon-enhanced/                  # Security scanner integration
│   ├── README.md
│   └── .github/workflows/atheon.yml
├── vite-react-pwa/                  # Vite + React PWA template
├── vite-ssr/                        # Vite + React SSR template
└── scaffolding/                     # Pre-built project templates
    ├── api-service/                 # Go HTTP API
    ├── cli-tool/                   # Go CLI application
    ├── worker-service/              # Go background worker
    ├── data-pipeline/              # Go data pipeline
    └── repository-ruleset/         # GitHub ruleset config
        ├── rules/
        │   ├── branch_protection.yml
        │   ├── commit_rules.yml
        │   └── pr_rules.yml
        └── script/
            └── setup-ruleset.sh
```

## Usage

```bash
# Copy a template part into a new project
cp -r template-parts/go/ ./my-project/
cp -r template-parts/common/.github/ ./.github/
cp -r template-parts/e2e-testing/ ./tests/e2e/

# Use bootstrap script for full project setup
./scripts/setup-repo.sh owner new-repo --include-go --include-e2e
```

## Coverage Targets

| Component | Target |
|-----------|--------|
| Core business logic | 95%+ |
| API handlers | 90%+ |
| E2E coverage | 80%+ |
| Configuration | 85%+ |
| Utility/helper functions | 85%+ |

## Stack Coverage Goals

| Stack | Target |
|-------|--------|
| Go | 90%+ |
| Python | 85%+ |
| Bash/Shell | 70%+ (linting coverage) |
| JavaScript/TypeScript | 85%+ |
