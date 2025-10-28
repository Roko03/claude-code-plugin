---
name: Agent Reference
description: Complete reference for all specialized AI agents organized by category with model assignments.
version: 1.0.0
---

# Agent Reference

Complete reference for all **specialized AI agents** organized by category with model assignments.

## Agent Categories

### Quality Assurance & Testing

#### QA & Test Automation

| Agent                                                 | Model  | Description                                                                                                                                     |
| ----------------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| [qa-expert](../plugins/qa-expert/agents/qa-expert.md) | sonnet | Comprehensive Quality Assurance Expert for designing, implementing, and managing QA processes, test strategies, and automated testing workflows |

## Model Configuration

Agents are assigned to specific Claude models based on task complexity and computational requirements.

### Model Distribution Summary

| Model  | Agent Count | Use Case                                                                           |
| ------ | ----------- | ---------------------------------------------------------------------------------- |
| Haiku  | 0           | Fast execution tasks: testing, documentation, ops, database optimization, business |
| Sonnet | 1           | Complex reasoning, architecture, language expertise, orchestration, security, QA   |

### Model Selection Criteria

#### Haiku - Fast Execution & Deterministic Tasks

**Use when:**

- Generating code from well-defined specifications
- Creating tests following established patterns
- Writing documentation with clear templates
- Executing infrastructure operations
- Performing database query optimization
- Handling customer support responses
- Processing SEO optimization tasks
- Managing deployment pipelines

#### Sonnet - Complex Reasoning & Architecture

**Use when:**

- Designing system architecture
- Making technology selection decisions
- Performing security audits
- Reviewing code for architectural patterns
- Creating complex AI/ML pipelines
- Providing language-specific expertise
- Orchestrating multi-agent workflows
- Handling business-critical legal/HR matters
- **Developing comprehensive QA strategies and test plans**
- **Analyzing quality metrics and providing data-driven insights**
- **Complex root cause analysis and defect management**

### Hybrid Orchestration Patterns

The plugin ecosystem leverages Sonnet + Haiku orchestration for optimal performance and cost efficiency:

#### Pattern 1: Planning → Execution

```
Sonnet: backend-architect (design API architecture)
  ↓
Haiku: Generate API endpoints following spec
  ↓
Haiku: test-automator (generate comprehensive tests)
  ↓
Sonnet: code-reviewer (architectural review)
```

#### Pattern 2: Reasoning → Action (Incident Response)

```
Sonnet: incident-responder (diagnose issue, create strategy)
  ↓
Haiku: devops-troubleshooter (execute fixes)
  ↓
Haiku: deployment-engineer (deploy hotfix)
  ↓
Haiku: Implement monitoring alerts
```

#### Pattern 3: Complex → Simple (Database Design)

```
Sonnet: database-architect (schema design, technology selection)
  ↓
Haiku: sql-pro (generate migration scripts)
  ↓
Haiku: database-admin (execute migrations)
  ↓
Haiku: database-optimizer (tune query performance)
```

#### Pattern 4: Multi-Agent Workflows

```
Full-Stack Feature Development:
Sonnet: backend-architect + frontend-developer (design components)
  ↓
Haiku: Generate code following designs
  ↓
Haiku: test-automator (unit + integration tests)
  ↓
Sonnet: security-auditor (security review)
  ↓
Haiku: deployment-engineer (CI/CD setup)
  ↓
Haiku: Setup observability stack
```

#### Pattern 5: Quality Assurance Workflow

```
Sonnet: qa-expert (develop test strategy and plan)
  ↓
Haiku: Generate test cases following strategy
  ↓
Playwright MCP: Execute automated E2E tests
  ↓
Haiku: Generate test execution reports
  ↓
Sonnet: qa-expert (analyze results, root cause analysis)
  ↓
Sonnet: qa-expert (provide release readiness recommendation)
```

## QA Expert Capabilities

### Core Features

- **Test Strategy Development**: Comprehensive testing strategies with scope, objectives, and resource planning
- **Test Case Design**: Clear, effective test cases covering various scenarios and code paths
- **Quality Assessment**: Manual and automated testing for functionality, performance, and security
- **Defect Management**: Identification, documentation, tracking, and root cause analysis
- **QA Analytics**: Quality metrics tracking and data-driven insights for stakeholders

### MCP Integration

- **context7**: Research QA methodologies, testing frameworks, industry best practices
- **sequential-thinking**: Complex test planning, systematic defect analysis
- **playwright**: Automated browser testing, E2E test execution, visual validation

### Quality Philosophy

1. **Prevention Over Detection**: Engage early in development lifecycle to prevent defects
2. **Comprehensive Testing**: Ensure all new logic is covered by unit, integration, and E2E tests
3. **No Failing Builds**: Strict policy that failing builds are never merged
4. **Test Behavior, Not Implementation**: Focus on user interactions and visible changes

### Definition of Done

A feature is not considered "done" until:

- ✅ All tests (unit, integration, E2E) are passing
- ✅ Code meets established style guides
- ✅ No console errors or unhandled API errors
- ✅ All new API endpoints are fully documented

## Agent Invocation

### Natural Language

Agents can be invoked through natural language when you need Claude to reason about which specialist to use:

```
"Use backend-architect to design the authentication API"
"Have security-auditor scan for OWASP vulnerabilities"
"Get performance-engineer to optimize this database query"
"Use qa-expert to create a comprehensive test plan for the checkout flow"
"Have qa-expert analyze our test coverage and recommend improvements"
"Get qa-expert to perform root cause analysis on these production bugs"
```

### Direct Agent Usage

```bash
# Start Claude Code with specific agent
claude-code --agent qa-expert

# In conversation with Claude Code
@qa-expert help me create E2E tests for user authentication
@qa-expert analyze this code for testability issues
@qa-expert generate a test plan for the payment integration feature
@qa-expert review our test coverage and suggest improvements
```

### Slash Commands

Many agents are accessible through plugin slash commands for direct invocation:

```bash
/backend-development:feature-development user authentication
/security-scanning:security-sast
/incident-response:smart-fix "memory leak in payment service"
```

## Agent Selection Guide

### When to Use QA Expert

Use **qa-expert** (Sonnet) when you need:

- ✅ Comprehensive test strategy and planning
- ✅ Test case design and architecture review
- ✅ Quality metrics analysis and reporting
- ✅ Root cause analysis of complex defects
- ✅ Release readiness assessment
- ✅ E2E test automation with Playwright
- ✅ Security and performance testing guidance
- ✅ QA process improvement recommendations
- ✅ Risk-based testing approach
- ✅ Complex defect analysis and prevention strategies

### QA Expert vs Other Testing Approaches

| Scenario                    | Use QA Expert (Sonnet) | Use Alternative           |
| --------------------------- | ---------------------- | ------------------------- |
| Strategic test planning     | ✅ qa-expert           | ❌                        |
| Complex quality analysis    | ✅ qa-expert           | ❌                        |
| Root cause analysis         | ✅ qa-expert           | ❌                        |
| Release readiness decision  | ✅ qa-expert           | ❌                        |
| Simple test generation      | ❌                     | ✅ test-automator (Haiku) |
| Execute existing tests      | ❌                     | ✅ CI/CD pipeline         |
| Performance benchmarking    | ❌                     | ✅ performance-engineer   |
| Security vulnerability scan | ❌                     | ✅ security-auditor       |

## Contributing

To add a new agent:

1. Create `plugins/{plugin-name}/agents/{agent-name}.md`
2. Add frontmatter with name, description, tools, and model assignment
3. Write comprehensive system prompt following established patterns
4. Update this agents reference file
5. Update plugin definition in `.claude-plugin/marketplace.json`

### Agent Frontmatter Template

```markdown
---
name: agent-name
description: Brief description of agent capabilities
tools: Read, Write, Edit, Bash, WebSearch, mcp__tool-name__function
model: sonnet | haiku
---
```

### QA Expert Frontmatter Example

```markdown
---
name: qa-expert
description: A sophisticated AI Quality Assurance (QA) Expert for designing, implementing, and managing comprehensive QA processes
tools: Read, Write, Edit, MultiEdit, Grep, Glob, Bash, LS, WebSearch, WebFetch, Task, mcp__context7__resolve-library-id, mcp__context7__get-library-docs, mcp__sequential-thinking__sequentialthinking, mcp__playwright__browser_navigate, mcp__playwright__browser_snapshot, mcp__playwright__browser_click, mcp__playwright__browser_type, mcp__playwright__browser_take_screenshot
model: sonnet
---
```

See [Contributing Guide](../CONTRIBUTING.md) for details.

## Version History

- **v1.0.0** (2025-10-28): Initial release with QA Expert agent
