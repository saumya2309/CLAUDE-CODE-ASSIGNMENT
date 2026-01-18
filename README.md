# CLAUDE-CODE-ASSIGNMENT
# Claude Architecture & Agentic Workflows


##  Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Assignment Deliverables](#assignment-deliverables)
- [Quick Start](#quick-start)
- [Documentation](#documentation)
- [Contributing](#contributing)

##  Overview

This repository contains a comprehensive exploration of Claude's architecture and practical implementations of agentic workflows. The assignment covers:

- **Claude Architecture Stack**: Understanding the layered system from `.claude.md` to tool execution
- **Skill Design**: Reusable capabilities for specialized tasks
- **Agent Development**: Single and multi-agent patterns with coordination
- **Practical Implementation**: Working examples and specifications

##  Repository Structure

```
.
├── README.md
├── docs/
│   ├── TASK_A_Architecture.md          # Full stack explanation + diagrams
│   ├── TASK_B_Claude_MD.md             # Sample .claude.md configuration
│   ├── TASK_C_Skills.md                # Three skill specifications
│   ├── TASK_D_Engine_Coordination.md   # Workflow execution examples
│   ├── TASK_E_Agent_Basics.md          # Agent concepts and patterns
│   ├── TASK_F_Agent_Designs.md         # Two complete agent specs
│   └── TASK_G_Multi_Agent.md           # Multi-agent orchestration
├── diagrams/
│   ├── architecture_stack.md           # ASCII architecture diagram
│   └── multi_agent_flow.md             # Agent coordination diagram
├── examples/
│   ├── .claude.md                      # Working .claude.md example
│   ├── skills/
│   │   ├── security_audit.py           # Security audit skill
│   │   ├── doc_generator.py            # Documentation generator
│   │   └── data_pipeline.py            # ETL pipeline skill
│   └── agents/
│       ├── vuln_scanner_agent.yaml     # VulnScanner agent config
│       ├── docgen_agent.yaml           # DocGen agent config
│       └── multi_agent_system.yaml     # Multi-agent orchestration
└── tests/
    └── test_skills.py                  # Skill test cases
```

##  Assignment Deliverables

### ✅ Task A: Architecture Write-up
**Location:** `docs/TASK_A_Architecture.md`

Comprehensive explanation of Claude's five-layer architecture:
- `.claude.md` - Global rules and reasoning habits
- `skill/` - Specialized capability modules
- Claude Engine - Planning, routing, and validation
- Tools - External capabilities (file system, shell, APIs)
- User - Intent and constraints

**Diagram:** `diagrams/architecture_stack.md`

### ✅ Task B: .claude.md Configuration
**Location:** `docs/TASK_B_Claude_MD.md` and `examples/.claude.md`

Sample configuration for an imaginary organization including:
- Tone and style rules
- Reasoning constraints
- Tool usage policies
- Safety guardrails
- Output format requirements

### ✅ Task C: Skill Design
**Location:** `docs/TASK_C_Skills.md`

Three reusable skills with complete specifications:
1. **skill/security_audit** - Vulnerability scanning and remediation
2. **skill/doc_generator** - Automated technical documentation
3. **skill/data_pipeline** - ETL workflow orchestration

### ✅ Task D: Claude Engine Coordination
**Location:** `docs/TASK_D_Engine_Coordination.md`

Detailed workflow execution example showing:
- Task decomposition (planner)
- Skill/tool selection (router)
- Output validation (checker)
- Ambiguity handling (clarifier)
- Multi-step workflow management (state manager)

### ✅ Task E: Agent Basics
**Location:** `docs/TASK_E_Agent_Basics.md`

Conceptual explanation of agents covering:
- Core agent components (role, scope, tools, policies)
- Memory strategies
- Evaluation rubrics
- Two agent patterns: Single-agent and Multi-agent

### ✅ Task F: Agent Designs
**Location:** `docs/TASK_F_Agent_Designs.md`

Two complete agent specifications:
1. **VulnScanner Agent** - Security vulnerability analysis
2. **DocGen Agent** - Technical documentation generation

Each includes: purpose, responsibilities, inputs/outputs, tools, guardrails, quality checklist, and example runs.

### ✅ Task G: Multi-Agent Orchestration
**Location:** `docs/TASK_G_Multi_Agent.md`

Advanced multi-agent architecture with:
- 1 Coordinator (Technical Lead)
- 4 Specialists (Requirements Analyst, Architect, Developer, QA Tester)
- Message flow diagram
- Routing policy
- Conflict resolution strategy
- Final merge strategy

**Diagram:** `diagrams/multi_agent_flow.md`

## 🚀 Quick Start

### Prerequisites
- Python 3.9+
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/claude-architecture-assignment.git
cd claude-architecture-assignment

# Install dependencies (for running examples)
pip install -r requirements.txt
```

### Running Examples

```bash
# Test security audit skill
python examples/skills/security_audit.py --target ./sample_code

# Generate documentation
python examples/skills/doc_generator.py --source ./sample_project

# Run data pipeline
python examples/skills/data_pipeline.py --config pipeline_config.yaml
```

### Running Tests

```bash
# Run all skill tests
pytest tests/test_skills.py -v

# Run specific test
pytest tests/test_skills.py::test_security_audit -v
```

##  Documentation

### Architecture Documentation
- [Full Architecture Stack](docs/TASK_A_Architecture.md)
- [Architecture Diagram](diagrams/architecture_stack.md)

### Configuration & Skills
- [.claude.md Configuration](docs/TASK_B_Claude_MD.md)
- [Skill Specifications](docs/TASK_C_Skills.md)

### Agent Development
- [Engine Coordination](docs/TASK_D_Engine_Coordination.md)
- [Agent Basics & Patterns](docs/TASK_E_Agent_Basics.md)
- [Agent Design Specifications](docs/TASK_F_Agent_Designs.md)
- [Multi-Agent Orchestration](docs/TASK_G_Multi_Agent.md)

### Diagrams
- [Architecture Stack Visualization](diagrams/architecture_stack.md)
- [Multi-Agent Flow](diagrams/multi_agent_flow.md)

##  Testing

All skills include comprehensive test cases covering:
- Happy path scenarios
- Edge cases
- Error handling
- Performance benchmarks

See `tests/test_skills.py` for implementation.

##  Contributing

This is an academic assignment, but suggestions and improvements are welcome:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add improvement'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

##  License

This project is part of an academic assignment. All code is provided as-is for educational purposes.

##  Acknowledgments

- Course instructors for the comprehensive assignment design
- Claude/Anthropic documentation for architecture insights
- Open-source community for security and documentation tools


---

**Assignment Status:** ✅ Complete  
**Last Updated:** January 18, 2026
