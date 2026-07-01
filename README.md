# Dark Factory

> **AI-first, 90%+ coverage, Dark Factory powered repository template.**

Dark Factory is an opinionated development methodology and GitHub repo template
for building production-grade software with automated test, code, and
documentation coverage. It enforces a hands-off, deterministic pipeline
through CI/CD, pre-commit/push hooks, and GitHub Actions.

## Features

- ✅ **90%+ automated coverage** — Built into the workflow, not bolted on at the end
- 🔒 **Strict pre-commit/push hooks** — Format, lint, test, and coverage gates
- ⚡ **Consolidated CI/CD** — One workflow to rule them all, with AI-assisted review
- 📦 **Template parts** — Modular, language-specific templates (Go, E2E, Code Library)
- 🏷️ **Branch protection** — Required reviews, required status checks, auto-delete branches
- 🔄 **Dependabot** — Automated dependency updates for Go and GitHub Actions
- 📚 **GitHub Wiki** — Auto-published from `.github/wiki/`
- 🤖 **AI Copilot instructions** — `.github/copilot-instructions.md` for context-aware AI assistance
- 🔍 **CodeQL + govulncheck** — Security scanning built in
- 📊 **Codecov integration** — Coverage tracking and enforcement

## Quick Start

### Use as a template

```bash
# Create a new repo from this template
gh repo create my-project --template aliasfoxkde/dark-factory --public

# Or use the bootstrap script
./scripts/setup-repo.sh owner my-project --public
```

### Clone and customize

```bash
git clone https://github.com/aliasfoxkde/dark-factory.git
cd dark-factory

# 1. Replace 'aliasfoxkde' with your GitHub username in:
#    - .github/CODEOWNERS
#    - .github/FUNDING.yml
#    - README.md (this file)

# 2. Set up git hooks
make setup

# 3. Push your first commit
git add -A && git commit -m "feat: initial commit"
git push
```

## Template Parts

| Part | Purpose |
|------|---------|
| `template-parts/go/` | Go module structure with standard packages |
| `template-parts/python/` | Python project with uv, ruff, pytest |
| `template-parts/typescript/` | TypeScript project with ESLint, Vitest |
| `template-parts/rust/` | Rust project with Cargo, clippy |
| `template-parts/e2e-testing/` | E2E test harness with AI coverage analysis |
| `template-parts/code-library/` | Reusable code snippets (Go, Python, Bash) |
| `template-parts/common/` | Shared configs (CLAUDE.md, AGENTS.md, .github/) |
| `template-parts/atheon-enhanced/` | Security scanner integration |
| `template-parts/vite-react-pwa/` | Vite + React PWA template |
| `template-parts/vite-ssr/` | Vite + React SSR template |
| `template-parts/scaffolding/` | Pre-built project templates |

### Scaffolding Templates

| Template | Purpose |
|----------|---------|
| `scaffolding/api-service/` | Go HTTP API with handlers, middleware, config |
| `scaffolding/cli-tool/` | Go CLI with Cobra commands |
| `scaffolding/worker-service/` | Go background worker with queue |
| `scaffolding/data-pipeline/` | Go data processing pipeline |
| `scaffolding/repository-ruleset/` | GitHub ruleset configuration |

## Coverage Targets

| Layer | Target |
|-------|--------|
| Core business logic | 95% |
| API handlers | 90% |
| Configuration | 85% |
| E2E tests | 80% |

## GitHub Setup (Automated)

When you create a repo from this template, the `setup-repo.yml` workflow
automatically configures:

- Wiki, Issues, Projects enabled
- Branch protection on `main`
- Required PR reviews + required CI checks
- Default labels (`bug`, `enhancement`, `documentation`, etc.)
- Milestones (`v1.0`, `Backlog`, `Technical Debt`)
- GitHub Project board with columns (Backlog, In Progress, Review, Done)
- Repository variables (coverage threshold, Go versions, etc.)
- Git hooks path configured

## CI/CD Pipeline

```
push / PR → ci.yml
  ├── go-test (Go 1.21-1.24, all OS, -race, coverage gate)
  ├── lint (go vet, gofmt, golangci-lint, goimports)
  ├── build (cross-platform binaries)
  ├── quality-grep (TODO without issue refs)
  └── vuln (govulncheck)

security.yml (on push + schedule)
  ├── CodeQL
  ├── govulncheck
  ├── secrets scan
  ├── dependency review
  └── security anti-pattern grep

auto-merge.yml (on PR)
  └── Squash-merge Dependabot + same-repo PRs

release.yml (on tag v*)
  └── GoReleaser cross-platform builds + SBOM

wiki.yml (on push to wiki/)
  └── Publish to GitHub Wiki
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full contribution guide.

## License

MIT License — see [LICENSE](LICENSE)