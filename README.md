# Platform Mode

[![Install with APM](https://img.shields.io/badge/📦_Install_with-APM-blue?style=flat-square)](https://github.com/danielmeppiel/apm#-apm-packages) 

**The Future of AI-Enhanced Platform Engineering**

Platform Mode is an advanced, spec-driven development toolkit that transforms how platform engineering teams build and operate Internal Developer Platforms (IDPs). By combining specialized AI agents, comprehensive workflow automation, and systematic quality gates, teams can deliver infrastructure and developer experiences with unprecedented speed and consistency.

## What is Platform Mode?

Platform Mode implements a complete **spec-driven development methodology** specifically designed for platform engineering workflows. Unlike traditional approaches that rely on manual processes and tribal knowledge, Platform Mode provides:

- **Six specialized AI agent personas** for different platform engineering disciplines
- **Seven-phase development lifecycle** with built-in quality gates
- **Complete agile integration** with AI-assisted planning and estimation
- **Systematic knowledge capture** and continuous improvement
- **Azure-native integration** optimized for modern cloud architectures

## Why Platform Mode?

Platform engineering teams face unique challenges: complex multi-service architectures, diverse stakeholder requirements, operational complexity, and the need for self-service developer experiences. Platform Mode addresses these challenges by:

### For Platform Teams
- **Reduces cognitive load** through structured workflows and specialized AI guidance
- **Ensures consistency** across infrastructure and tooling decisions
- **Accelerates delivery** with automated quality gates and spec-driven development
- **Captures knowledge** systematically to prevent repeated mistakes

### For Developers
- **Self-service enablement** through golden paths and opinionated defaults
- **Reduced friction** in accessing platform services and resources
- **Clear abstractions** that hide infrastructure complexity while maintaining flexibility

## How Platform Mode Works in VS Code with GitHub Copilot

### Custom Chat Modes (AI Personas)
Switch between specialized AI agents optimized for different platform engineering tasks:

```
@platform-architect    # System design & architecture decisions
@devops-engineer       # Infrastructure automation & CI/CD
@security-engineer     # Security architecture & compliance
@product-manager       # Requirements & stakeholder alignment
@qa-engineer          # Testing strategies & quality assurance
@scrum-master         # Agile facilitation & team optimization
```

Each chat mode provides:
- **Focused expertise** for the specific domain
- **Curated tool access** (no more overwhelming tool lists)
- **Role-specific prompts** and guidance
- **Integration with organizational standards**

### Slash Commands (Workflow Automation)
Execute complete workflows through simple commands:

#### Development Lifecycle Commands
```
/discovery     # User research & problem analysis
/analysis      # Requirements gathering & validation
/design        # Architecture & system design with ADRs
/plan          # Sprint planning & story breakdown
/execute       # Implementation with quality gates
/validate      # Testing & acceptance verification
/retrospect    # Lessons learned & improvement
```

#### Agile Integration Commands
```
/epic          # Create comprehensive epics
/story         # Generate detailed user stories
/sprint-plan   # Capacity planning & commitment
/estimate      # AI-assisted story point estimation
/definition-of-done  # Multi-level DoD checklists
```

#### Infrastructure Commands
```
/terraform     # Infrastructure as Code following best practices
/quality-gate  # Automated quality checkpoints
/spec-review   # Architecture compliance validation
```

### Custom Instructions
Organizational standards that automatically apply to relevant contexts:

```
.github/instructions/terraform.instruction.md
```
- **Scoped application** via `applyTo:` YAML frontmatter
- **Automatic enforcement** of coding standards and best practices
- **Consistent quality** across team members and projects

## The Platform Engineering UI Layer Revolution

Platform Mode represents the future of platform engineering interfaces - moving beyond traditional CLI tools and web portals to **conversational, AI-enhanced workflows** integrated directly into development environments.

### Traditional Platform Engineering
- **Portal-based**: Separate tools and interfaces
- **Context switching**: Constant movement between tools
- **Manual processes**: Repetitive, error-prone workflows
- **Knowledge silos**: Tribal knowledge and documentation debt

### Platform Mode Approach
- **Embedded experience**: Work where developers already are (VS Code)
- **Conversational interfaces**: Natural language interaction with platform services
- **Automated workflows**: One command executes complete processes
- **Systematic knowledge**: Built-in learning and improvement

### Future Vision
Platform Mode enables platform engineers to:
- **Manage entire cloud environments** through natural conversation
- **Provision infrastructure** with business-context aware AI
- **Debug production issues** with AI-guided troubleshooting
- **Optimize costs and performance** through predictive analytics
- **Onboard new developers** with personalized, interactive guidance

## 📁 Repository Structure

```
.github/
├── chatmodes/           # Specialized AI agent personas
│   ├── platform-architect.chatmode.md
│   ├── devops-engineer.chatmode.md
│   └── ... (6 specialized modes)
├── prompts/             # Workflow automation commands
│   ├── discovery.prompt.md
│   ├── terraform.prompt.md
│   └── ... (20+ workflow commands)
└── instructions/        # Organizational standards
    └── terraform.instruction.md

.platform-mode/
├── standards/          # Best practices & style guides
├── epics/             # Epic definitions & acceptance criteria
├── stories/           # User stories & detailed requirements
├── sprints/           # Sprint planning & execution artifacts
├── validation/        # Quality gates & DoD checklists
├── retrospectives/    # Lessons learned & improvements
└── workflows/         # Orchestrated command sequences
```

## Getting Started

### 1. Choose Your AI Agent
Select the appropriate persona for your current work:
```
@devops-engineer "Help me set up a new Azure Kubernetes Service cluster"
@platform-architect "Design a multi-tenant logging architecture"
@security-engineer "Review this Terraform configuration for security issues"
```

### 2. Execute Workflow Commands
Use slash commands for systematic development:
```
/discovery → /analysis → /design → /plan → /execute → /validate → /retrospect
```

### 3. Leverage Organizational Standards
Standards automatically apply based on file types and contexts, ensuring consistency without manual enforcement.

### 4. Build on Proven Patterns
Platform Mode integrates with Azure-based reference architectures (like [Humanitec's Azure reference architecture](https://humanitec.com/reference-architectures/azure)) providing battle-tested patterns for:
- **Container orchestration** with Azure Kubernetes Service
- **CI/CD automation** with Azure DevOps and GitHub Actions
- **Security integration** with Azure Active Directory and Key Vault
- **Monitoring and observability** with Azure Monitor and Application Insights

## Key Benefits

### For Platform Teams
- **30-40% reduction in rework** through better specifications
- **Improved velocity** with AI-assisted task breakdown
- **Higher code quality** via systematic validation
- **Reduced cognitive load** through automation
- **Better stakeholder alignment** with structured workflows

### For Organizations
- **Faster developer onboarding** with self-service capabilities
- **Consistent platform experiences** across teams
- **Reduced operational overhead** through automation
- **Better compliance** with built-in quality gates
- **Systematic knowledge capture** prevents repeated mistakes

## 🌟 The Future of Platform Engineering

Platform Mode represents a paradigm shift toward **AI-enhanced, conversation-driven platform engineering**. By embedding intelligence directly into development workflows, platform teams can focus on strategic initiatives while automation handles routine tasks.

This is platform engineering designed for the age of AI - where conversations with intelligent agents replace complex UIs, where context-aware automation replaces manual processes, and where systematic learning replaces tribal knowledge.

**Welcome to the future of platform engineering. Welcome to Platform Mode.**

## A note about MCP Servers

As of Sept 16th 2025, GitHub now has an official MCP Registry where you can find and use available MCP Servers both for local install/running and remotely hosted MCP servers as well.

See blog post [here](https://github.blog/ai-and-ml/github-copilot/meet-the-github-mcp-registry-the-fastest-way-to-discover-mcp-servers/)

We will be using this registry to define a minimal set of MCP servers for use in this project and ensure that they are listed, you may modify according to your needs but note that any updates and syncing from upstream will overwrite your config changes in the future.  The list of MCP servers required will be stored in [./vscode/mcp.json](/.vscode/mcp.json)