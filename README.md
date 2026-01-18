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
# Task A: Claude Architecture - The Full Stack

## Overview

Claude-based workflows operate as a sophisticated layered system where each layer has distinct responsibilities. This architecture enables complex AI workflows while maintaining safety, quality, and alignment with user intent.

## The Five Layers

### Layer 1: .claude.md - "How to Think" (Global Rules)

**Purpose:** Defines the foundational reasoning habits, boundaries, and behavioral constraints that govern all Claude operations.

**What it Contains:**
- **Reasoning Principles:** How to approach problems, when to ask vs assume
- **Tone & Style:** Communication preferences (concise, technical, friendly)
- **Safety Guardrails:** What must never be done (delete production data, expose secrets)
- **Quality Standards:** Output requirements (always include tests, document assumptions)
- **Tool Usage Policies:** Which tools are allowed, required approvals
- **Domain Knowledge:** Industry-specific terminology, compliance requirements

**Example Rules:**
```markdown
## Reasoning
- Always verify assumptions before proceeding
- Ask for missing critical information rather than guessing
- Prefer checklists for complex multi-step tasks

## Safety
- Never execute destructive operations without explicit confirmation
- Redact all credentials, API keys, and PII from logs
- Require human approval for production deployments

## Output Format
- Every report must include: Summary + Findings + Action Items
- Code must include inline comments and type hints
- All decisions must be documented with rationale
```

**Why it Matters:**
The `.claude.md` file acts as the "constitution" of the system. It ensures consistent behavior across all tasks, prevents dangerous operations, and maintains quality standards even as requirements change.

---

### Layer 2: skill/ - Specialized Capabilities (Dynamic Resources)

**Purpose:** Modular, reusable capabilities that encapsulate domain expertise and complex workflows.

**What Skills Store:**
- **Templates:** Structured formats for common outputs (reports, documentation)
- **Procedures:** Step-by-step algorithms for complex tasks (security audits, data migrations)
- **Tool Recipes:** Pre-configured tool call sequences for specific use cases
- **Validation Rules:** Quality checks and acceptance criteria
- **Error Handling:** Common failure modes and recovery strategies

**Example Skill Structure:**
```
skill/security_audit/
├── procedure.md          # Step-by-step audit process
├── patterns.yaml         # Vulnerability detection patterns
├── tools_config.json     # Required tools and configurations
├── report_template.md    # Standard report format
└── test_cases.json       # Validation test cases
```

**Characteristics:**
- **Composable:** Skills can call other skills
- **Reusable:** Same skill works across different projects
- **Maintainable:** Update skill once, all users benefit
- **Testable:** Skills have defined test cases

**Example: skill/triage**
```markdown
# Skill: Issue Triage

## Purpose
Prioritize incoming issues and generate remediation plans

## Inputs
- issue_list: Array of issues with severity, component, description
- sla_requirements: Service level agreement constraints

## Procedure
1. Parse and normalize issue data
2. Classify by severity (Critical/High/Medium/Low)
3. Calculate business impact
4. Check for duplicates and related issues
5. Assign priority score (severity × impact × urgency)
6. Generate remediation plan with time estimates

## Tools Used
- analysis.classify()
- database.query_similar()
- planning.generate_timeline()

## Output Template
{
  "critical_issues": [...],
  "remediation_plan": [...],
  "estimated_completion": "timestamp"
}
```

---

### Layer 3: Claude Engine - Who Executes (Reasoning + Coordination)

**Purpose:** The core orchestration layer that interprets intent, plans execution, manages state, and ensures quality.

**Core Responsibilities:**

#### 3.1 Planning (Decomposer)
- Breaks complex requests into manageable subtasks
- Identifies dependencies between tasks
- Creates execution sequences
- Establishes checkpoints for validation

#### 3.2 Routing (Selector)
- Matches tasks to appropriate skills
- Chooses optimal tools for each step
- Considers safety constraints and permissions
- Implements fallback strategies

#### 3.3 Validation (Checker)
- Verifies outputs against acceptance criteria
- Cross-references results with inputs
- Checks logical consistency
- Validates format compliance

#### 3.4 Clarification (Questioner)
- Distinguishes critical unknowns from safe assumptions
- Asks targeted questions for missing information
- Documents assumptions made
- Escalates when uncertainty is too high

#### 3.5 State Management (Coordinator)
- Tracks workflow progress
- Maintains context across steps
- Manages checkpoints and rollback points
- Coordinates parallel execution streams

**Data Flow Through Engine:**
```
User Intent → Parse → Plan → Route to Skill/Tool → Execute → Validate → 
  ↓ (if invalid)
  Retry/Adjust Plan → Execute → Validate → 
  ↓ (if valid)
  Update State → Next Step or Complete
```

---

### Layer 4: Tools - Hands (External Capabilities)

**Purpose:** Provide concrete capabilities to interact with systems, data, and environments.

**Tool Categories:**

#### File System Tools
- `read_file()` - Read file contents
- `write_file()` - Create or update files
- `search_pattern()` - Find patterns across files
- `list_directory()` - Enumerate files

#### Shell Tools
- `execute_command()` - Run shell commands
- `run_script()` - Execute scripts with parameters
- `check_status()` - Verify command success

#### API Tools
- `http_request()` - Make HTTP calls
- `query_database()` - Execute SQL queries
- `call_service()` - Invoke external services

#### Analysis Tools
- `parse_code()` - Extract code structure
- `validate_schema()` - Check data formats
- `calculate_metrics()` - Compute statistics

**Tool Safety Considerations:**
- Each tool has explicit permissions (read-only vs read-write)
- Destructive operations require confirmation
- Tool calls are logged for auditability
- Rate limiting prevents resource exhaustion

**Example Tool Call:**
```python
# Engine decides to use file_system.search_pattern
result = tool_call(
    name="file_system.search_pattern",
    params={
        "path": "/project/src",
        "pattern": r"password\s*=\s*['\"].*['\"]",
        "file_types": [".py", ".js"]
    }
)
# Engine validates result before proceeding
if result.matches_found > 0:
    flag_security_issue(result)
```

**What Tools Change:**
- **Capabilities:** Claude can now interact with real systems, not just reason abstractly
- **Risks:** Improper tool use can cause real damage (delete files, expose data)
- **Complexity:** Tool failures must be handled gracefully
- **Power:** Complex workflows become possible (build, test, deploy)

---

### Layer 5: User - Director (Provides Intent)

**Purpose:** The human element that sets goals, constraints, priorities, and provides domain context.

**User Responsibilities:**

#### 5.1 Intent Definition
- Clearly state desired outcomes
- Provide acceptance criteria
- Define success metrics
- Set boundaries and constraints

#### 5.2 Context Provision
- Share relevant background information
- Provide domain-specific knowledge
- Explain organizational constraints
- Clarify priorities when conflicts arise

#### 5.3 Feedback Loop
- Review intermediate results
- Answer clarifying questions
- Approve or reject proposals
- Adjust requirements based on learnings

#### 5.4 Constraint Setting
- Time limits and deadlines
- Budget and resource constraints
- Compliance and regulatory requirements
- Risk tolerance levels

**How User Intent Steers Execution:**

The system continuously aligns to user intent through:
- **Initial Prompt:** Shapes the entire workflow plan
- **Clarifying Questions:** Engine asks when ambiguity is detected
- **Checkpoints:** User reviews and approves before proceeding
- **Feedback:** User corrections update the plan
- **Termination:** User can stop execution at any point

**Example User Journey:**
```
User: "Audit our authentication system for vulnerabilities"
  ↓
Engine: "What compliance framework should I check against?"
  ↓
User: "SOC2 and OWASP Top 10"
  ↓
Engine: Executes audit with those constraints
  ↓
Engine: "Found 12 issues. Should I prioritize quick wins or critical risks?"
  ↓
User: "Critical risks first, then we'll tackle quick wins"
  ↓
Engine: Adjusts remediation plan priority
```

---

## Data & Control Flow Diagram

```
┌─────────────────────────────────────────────────────────┐
│                    USER (Layer 5)                       │
│  • Provides: Intent, Context, Constraints, Feedback     │
│  • Controls: Approval, Priorities, Termination          │
└────────────────────┬────────────────────────────────────┘
                     │ Intent & Requirements
                     ▼
┌─────────────────────────────────────────────────────────┐
│              .claude.md (Layer 1)                       │
│  • Loads: Global rules, policies, guardrails            │
│  • Enforces: Safety, quality, compliance                │
└────────────────────┬────────────────────────────────────┘
                     │ Rules Applied
                     ▼
┌─────────────────────────────────────────────────────────┐
│            CLAUDE ENGINE (Layer 3)                      │
│                                                          │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐             │
│  │ Planner  │→ │  Router  │→ │ Executor │             │
│  └──────────┘  └──────────┘  └──────────┘             │
│        ↓              ↓              ↓                  │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐             │
│  │Validator │  │ Clarifier│  │State Mgr │             │
│  └──────────┘  └──────────┘  └──────────┘             │
│                                                          │
└──────┬─────────────────────────────────┬────────────────┘
       │                                 │
       │ Select Skill                    │ Call Tool
       ▼                                 ▼
┌─────────────────┐           ┌─────────────────────┐
│  skill/ (L2)    │           │   TOOLS (Layer 4)   │
│                 │           │                     │
│ • security_audit│           │ • file_system       │
│ • doc_generator │           │ • shell             │
│ • data_pipeline │           │ • api_client        │
│                 │           │ • analysis          │
└─────────────────┘           └─────────────────────┘
       │                                 │
       │ Skill Output                    │ Tool Results
       └────────────┬────────────────────┘
                    ▼
         ┌─────────────────────┐
         │  Aggregated Results │
         └──────────┬──────────┘
                    │
                    ▼ Validation & Quality Check
         ┌─────────────────────┐
         │   Final Deliverable │
         └──────────┬──────────┘
                    │
                    ▼
         ┌─────────────────────┐
         │    USER (Receives)  │
         └─────────────────────┘
```

## Layer Interaction Examples

### Example 1: Security Audit Request

**User Layer:**
```
"Audit our payment processing code for PCI-DSS compliance"
```

**.claude.md Layer:**
```
Rules Applied:
✓ Never expose actual credit card numbers in reports
✓ Require evidence for all findings
✓ Use severity ratings from CVSS
```

**Engine Layer:**
```
Plan:
1. Load skill/security_audit
2. Configure for PCI-DSS framework
3. Scan payment processing modules
4. Validate findings
5. Generate compliant report

Route: skill/security_audit with PCI-DSS config
```

**Skill Layer:**
```
skill/security_audit executes:
- Load PCI-DSS requirements checklist
- Scan for card data handling
- Check encryption methods
- Verify audit logging
```

**Tool Layer:**
```
Tools Used:
- file_system.read() → Read payment.py
- search_pattern() → Find card number patterns
- shell.execute() → Run Bandit security scanner
```

**Return Flow:**
```
Tools → Skill: Scan results
Skill → Engine: Formatted findings
Engine → Validates against .claude.md rules
Engine → User: PCI-DSS compliance report
```

### Example 2: Documentation Generation

**User:** "Generate API documentation for our REST service"

**.claude.md:** Enforce "all examples must be tested" rule

**Engine:** Routes to skill/doc_generator

**Skill:** Executes documentation generation procedure

**Tools:** 
- `file_system.read()` - Read route definitions
- `parse_code()` - Extract endpoint details
- `http_request()` - Test example API calls

**Result:** Complete API reference with validated examples

---

## Key Principles

### 1. Separation of Concerns
Each layer has a distinct responsibility, making the system:
- **Modular:** Change one layer without affecting others
- **Testable:** Validate each layer independently
- **Maintainable:** Clear boundaries for debugging

### 2. Progressive Refinement
Information flows down (intent → execution) and results flow up (outputs → validation):
- User intent becomes increasingly concrete at each layer
- Results become increasingly validated as they return

### 3. Safety Through Layers
Multiple checkpoints prevent harmful actions:
- `.claude.md` defines what's never allowed
- Skills encode safe procedures
- Engine validates before and after
- Tools have explicit permissions
- User must approve critical operations

### 4. Adaptability
The architecture supports changing requirements:
- Update `.claude.md` for new policies
- Add skills for new capabilities
- Configure engine for different workflows
- Integrate new tools as needed

---

## Conclusion

This five-layer architecture enables Claude to:
- Reason about complex tasks (Engine)
- Apply specialized expertise (Skills)
- Interact with real systems (Tools)
- Maintain safety and quality (.claude.md)
- Align with human intent (User)

The architecture is both powerful and safe because each layer constrains and validates the layers below it, creating a system where sophisticated automation operates within carefully defined boundaries.

---

# Task B: .claude.md Configuration

## Sample .claude.md for FinTech Startup

This `.claude.md` configuration is designed for a fictional financial technology startup called "SecurePay" that builds payment processing and compliance systems.

---


# .claude.md - SecurePay Development Standards

## Organization Context
**Company:** SecurePay Inc.
**Domain:** Financial Technology (Payment Processing)
**Compliance:** PCI-DSS Level 1, SOC 2 Type II, GDPR
**Last Updated:** 2026-01-15

---

## Tone and Style Rules

### Communication Style
- **Concise and technical:** Assume audience has software engineering background
- **No marketing fluff:** Focus on facts, data, and actionable information
- **Professional tone:** Appropriate for financial services industry
- **Precision over brevity:** In compliance contexts, include all necessary details

### Code Documentation
- Use clear, descriptive variable names (no abbreviations unless industry-standard)
- Every public function must have a docstring with parameters, returns, and examples
- Complex algorithms require inline comments explaining the "why", not just the "what"
- Include time/space complexity for performance-critical code

### Report Format
All reports must include:
1. **Executive Summary** (2-3 sentences, non-technical)
2. **Key Findings** (bullet points, priority-ordered)
3. **Detailed Analysis** (technical depth with evidence)
4. **Action Items** (specific, assignable, with effort estimates)
5. **Appendix** (supporting data, logs, references)

---

## Reasoning Constraints

### Verification Requirements
- **Always verify assumptions:** Never assume configuration, state, or permissions
- **Explicit > Implicit:** Ask for missing critical information rather than guessing
- **Evidence-based:** Every claim must be backed by logs, tests, or documentation
- **Cross-reference:** Validate consistency across code, docs, and specs

### Decision-Making Framework
- **When to ask for input:**
  - Security tradeoffs affecting compliance
  - Architectural decisions with long-term consequences
  - Ambiguous requirements that could be interpreted multiple ways
  - Any operation affecting production data or systems

- **When to assume:**
  - Industry best practices (e.g., use bcrypt for passwords, HTTPS for APIs)
  - Standard development patterns for the stack (Node.js, Python, PostgreSQL)
  - Common security defaults (principle of least privilege, fail-secure)

### Preferred Problem-Solving Approaches
1. **Checklists for complex tasks:** Break down into verifiable steps
2. **Incremental validation:** Test after each major step, not just at the end
3. **Failure mode analysis:** Consider what could go wrong before proceeding
4. **Rollback planning:** Always have a clear path to undo changes

---

## Tool Usage Policy

### Allowed Tools

#### File System Operations
- **READ:** Unrestricted for code review, analysis, documentation
- **WRITE:** Allowed for:
  - Test files
  - Documentation
  - Configuration in non-production environments
  - Code generation (must be reviewed before commit)
- **DELETE:** Prohibited without explicit user approval

#### Shell/Command Execution
- **Allowed:**
  - Running tests (`npm test`, `pytest`)
  - Build operations (`npm run build`, `make`)
  - Linting and static analysis (`eslint`, `mypy`, `bandit`)
  - Dependency checks (`npm audit`, `safety check`)
  
- **Requires Approval:**
  - Package installation (`npm install`, `pip install`)
  - Database migrations
  - Deployment commands
  
- **Prohibited:**
  - Direct production database access
  - Modifying system files
  - Network configuration changes

#### API/External Services
- **Allowed:**
  - Read-only queries to documentation APIs
  - Security vulnerability databases (NVD, CVE)
  - Package registries (npm, PyPI) for version checks
  
- **Requires Approval:**
  - Any write operations to external services
  - Webhook creation or modification
  - OAuth token generation

### Tool Execution Logging
- **Always log:**
  - Command executed
  - Timestamp
  - User who requested it
  - Exit code and output summary
- **Sensitive data handling:**
  - Redact: passwords, API keys, tokens, PII, card numbers
  - Use: `***REDACTED***` placeholder
  - Never log: full credit card numbers, SSNs, raw passwords

### Error Handling for Tools
- **Retry policy:** Max 3 attempts with exponential backoff (1s, 2s, 4s)
- **Timeout limits:**
  - File operations: 30 seconds
  - Shell commands: 5 minutes
  - API calls: 30 seconds
- **Failure escalation:**
  - Log error with full context
  - Notify user with clear error message
  - Suggest remediation steps
  - Do not retry operations that are idempotent-unsafe

---

## Safety Guardrails

### Data Protection

#### Personally Identifiable Information (PII)
- **Never log or display:**
  - Social Security Numbers
  - Full credit card numbers (only last 4 digits allowed)
  - Bank account numbers
  - Passwords or password hashes
  - Email addresses in error messages
  
- **Redaction requirements:**
  - Replace with `***PII_REDACTED***`
  - Maintain data structure for debugging (e.g., `email: ***@***.com`)
  - Keep metadata (length, type) for analysis

#### Secrets Management
- **Prohibited actions:**
  - Hardcoding API keys, tokens, or credentials in code
  - Committing `.env` files with real secrets
  - Storing secrets in logs or screenshots
  - Sharing secrets via insecure channels (chat, email)
  
- **Required practices:**
  - Use environment variables for all secrets
  - Reference secrets by name, never by value
  - Rotate credentials after any potential exposure
  - Use secret management service (AWS Secrets Manager, HashiCorp Vault)

### Production System Protection
- **Never:**
  - Delete production data without user confirmation + backup verification
  - Modify production databases without migration script review
  - Deploy to production without passing CI/CD pipeline
  - Bypass authentication or authorization checks
  
- **Always:**
  - Test in staging environment first
  - Require code review for production changes
  - Maintain audit trail for all production operations
  - Have rollback plan before deployment

### Compliance Guardrails

#### PCI-DSS Requirements
- **Cardholder data:**
  - Must be encrypted at rest (AES-256) and in transit (TLS 1.2+)
  - Minimize storage (only store when absolutely necessary)
  - Truncate/mask in logs and UI (show only last 4 digits)
  - Implement data retention policy (delete after 90 days if not required)
  
- **Access control:**
  - Principle of least privilege for all system access
  - Multi-factor authentication for production access
  - Unique user IDs (no shared accounts)
  - Quarterly access reviews

#### GDPR Compliance
- **Data subject rights:**
  - Implement data portability (export in machine-readable format)
  - Enable right to erasure (complete data deletion on request)
  - Provide access logs (who accessed what data, when)
  - Maintain consent records
  
- **Privacy by design:**
  - Minimize data collection (collect only what's necessary)
  - Implement purpose limitation (use data only for stated purposes)
  - Enable pseudonymization where possible
  - Data protection impact assessments for new features

### Security Defaults
- **Authentication:**
  - Minimum password length: 12 characters
  - Require: uppercase, lowercase, number, special character
  - Implement account lockout after 5 failed attempts
  - Session timeout: 30 minutes of inactivity
  
- **Encryption:**
  - TLS 1.2+ for all network communication
  - bcrypt (cost factor 12) for password hashing
  - AES-256 for data at rest
  - Secure random number generation (crypto-grade)

---

## Output Format Requirements

### Code Deliverables
All code submissions must include:
1. **Source files** with:
   - Type hints (Python) or TypeScript types
   - Docstrings/JSDoc for all public functions
   - Inline comments for complex logic
   - Error handling with specific exceptions
   
2. **Tests** with:
   - Unit tests (80%+ coverage minimum)
   - Integration tests for API endpoints
   - Edge case coverage
   - Performance benchmarks for critical paths
   
3. **Documentation** with:
   - README with setup instructions
   - API documentation (OpenAPI/Swagger for REST APIs)
   - Architecture decision records (ADRs) for major choices
   - Migration guides for breaking changes

### Security Assessment Reports
Format:
```markdown
# Security Assessment Report

## Executive Summary
- Total findings: X (Critical: Y, High: Z, Medium: A, Low: B)
- Compliance status: COMPLIANT / NON-COMPLIANT
- Recommended action: IMMEDIATE / PLANNED / MONITOR

## Critical Findings
[C-001] Title
- **Severity:** Critical (CVSS 9.x)
- **CWE:** CWE-XXX
- **Location:** file.py:line
- **Evidence:** [code snippet or log]
- **Impact:** [business risk]
- **Remediation:** [specific fix with code example]
- **Effort:** X hours

## Remediation Roadmap
1. [Priority 1] Fix C-001: [task] (Est: X hours, Due: date)
2. [Priority 2] Fix H-001: [task] (Est: Y hours, Due: date)

## Compliance Checklist
- [ ] PCI-DSS 3.2.1 Requirement 6.5.1: PASSED
- [x] PCI-DSS 3.2.1 Requirement 6.5.2: FAILED (see C-001)
```

### Change Requests
Format:
```markdown
# Change Request: [Title]

## Summary
One-sentence description of the change.

## Motivation
Why is this change needed? What problem does it solve?

## Proposed Solution
Technical approach with:
- Architecture changes
- Database schema modifications
- API contract updates
- Security implications

## Alternatives Considered
1. Option A: [pros/cons]
2. Option B: [pros/cons]

## Testing Plan
- Unit tests: [description]
- Integration tests: [description]
- Manual testing: [steps]

## Rollout Plan
1. Deploy to dev (Date)
2. QA validation (Date)
3. Deploy to staging (Date)
4. Production deployment (Date)
5. Post-deployment validation

## Rollback Plan
Steps to revert if issues found:
1. [step]
2. [step]

## Compliance Impact
- PCI-DSS: No impact / Requires re-certification
- GDPR: No impact / Requires privacy assessment
- SOC 2: No impact / Requires control update
```

---

## Quality Standards

### Code Quality Metrics
- **Test coverage:** Minimum 80% for new code, 90% for critical paths
- **Complexity:** Max cyclomatic complexity of 10 per function
- **Linting:** Zero eslint/pylint errors, warnings allowed with justification
- **Type safety:** 100% type coverage in TypeScript, 95%+ in Python with mypy

### Performance Requirements
- **API response time:** p95 < 200ms, p99 < 500ms
- **Database queries:** Max 100ms per query, no N+1 queries
- **Frontend load time:** First Contentful Paint < 1.5s
- **Build time:** < 5 minutes for full CI/CD pipeline

### Documentation Requirements
- **API endpoints:** OpenAPI spec must match implementation exactly
- **Database schema:** ER diagrams generated from actual schema
- **Architecture:** C4 diagrams (Context, Container, Component levels)
- **Runbooks:** Step-by-step procedures for common operations

---

## Escalation Policy

### When to escalate to human review:
1. **Security issues:**
   - Critical or High severity vulnerabilities
   - Potential data breach or exposure
   - Compliance violations
   
2. **Architectural decisions:**
   - New external dependencies
   - Database schema changes affecting > 1M rows
   - Breaking API changes
   
3. **Ambiguous requirements:**
   - Conflicting business logic
   - Regulatory interpretation questions
   - Performance vs. feature tradeoffs
   
4. **Blocked progress:**
   - Missing access or credentials
   - External service dependencies unavailable
   - Conflicting priorities

### Escalation format:
```markdown
## ESCALATION REQUIRED

**Category:** [Security / Architecture / Requirements / Blocked]
**Severity:** [Critical / High / Medium]
**Summary:** [one-sentence description]

**Context:**
[Detailed background]

**Question:**
[Specific decision needed]

**Options:**
1. Option A: [description, pros, cons, risks]
2. Option B: [description, pros, cons, risks]

**Recommendation:**
[Your recommended option with justification]

**Impact if delayed:**
[What happens if this isn't resolved quickly]
```

---

## Continuous Improvement

This `.claude.md` is a living document. Update it when:
- New compliance requirements are added
- Security incidents reveal gaps in guardrails
- Team workflows change
- Tool capabilities expand
- Lessons learned from production issues

**Version History:**
- v1.0 (2026-01-15): Initial version
- [Future versions will be documented here]

---

# Claude Architecture Stack Diagram

## Full Stack Visualization

```
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│                         USER (Layer 5)                             │
│                         The Director                               │
│                                                                    │
│  Provides:                          Controls:                      │
│  • Intent & Goals                   • Approval/Rejection           │
│  • Context & Constraints            • Priority Adjustments         │
│  • Domain Knowledge                 • Workflow Termination         │
│  • Acceptance Criteria              • Feedback & Corrections       │
│                                                                    │
└───────────────────────────┬────────────────────────────────────────┘
                            │
                            │ Intent, Requirements, Feedback
                            │
                            ▼
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│                    .claude.md (Layer 1)                            │
│                 "How to Think" - Global Rules                      │
│                                                                    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐            │
│  │   Reasoning  │  │    Safety    │  │    Quality   │            │
│  │  Constraints │  │  Guardrails  │  │   Standards  │            │
│  └──────────────┘  └──────────────┘  └──────────────┘            │
│                                                                    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐            │
│  │     Tone     │  │  Tool Usage  │  │    Output    │            │
│  │    & Style   │  │   Policies   │  │   Formats    │            │
│  └──────────────┘  └──────────────┘  └──────────────┘            │
│                                                                    │
│  Enforces: Never delete prod data, Always verify assumptions,     │
│           Redact PII, Require tests, Use checklists               │
│                                                                    │
└───────────────────────────┬────────────────────────────────────────┘
                            │
                            │ Rules & Policies Applied
                            │
                            ▼
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│                   CLAUDE ENGINE (Layer 3)                          │
│              Reasoning & Coordination Hub                          │
│                                                                    │
│  ┌───────────────────────────────────────────────────────────┐   │
│  │                     PLANNER                                │   │
│  │  • Decompose complex tasks into subtasks                  │   │
│  │  • Identify dependencies                                  │   │
│  │  • Create execution sequence                              │   │
│  │  • Establish checkpoints                                  │   │
│  └───────────────────────────┬───────────────────────────────┘   │
│                              │                                    │
│                              ▼                                    │
│  ┌───────────────────────────────────────────────────────────┐   │
│  │                     ROUTER                                 │   │
│  │  • Match tasks to skills                                  │   │
│  │  • Select appropriate tools                               │   │
│  │  • Apply safety constraints                               │   │
│  │  • Choose execution strategy                              │   │
│  └───────────────────────────┬───────────────────────────────┘   │
│                              │                                    │
│            ┌─────────────────┴─────────────────┐                 │
│            │                                   │                 │
│            ▼                                   ▼                 │
│  ┌──────────────────┐              ┌──────────────────┐          │
│  │  Route to SKILL  │              │  Route to TOOL   │          │
│  └────────┬─────────┘              └────────┬─────────┘          │
│           │                                 │                    │
│           │                                 │                    │
└───────────┼─────────────────────────────────┼────────────────────┘
            │                                 │
            │                                 │
            ▼                                 ▼
┌──────────────────────┐          ┌──────────────────────────┐
│                      │          │                          │
│   skill/ (Layer 2)   │          │    TOOLS (Layer 4)       │
│ Specialized Modules  │          │   External Capabilities  │
│                      │          │                          │
│ ┌──────────────────┐ │          │ ┌──────────────────────┐ │
│ │ security_audit   │ │          │ │   File System        │ │
│ │                  │ │          │ │  - read_file()       │ │
│ │ • Patterns       │ │          │ │  - write_file()      │ │
│ │ • Procedures     │ │          │ │  - search_pattern()  │ │
│ │ • Templates      │ │          │ └──────────────────────┘ │
│ │ • Test Cases     │ │          │                          │
│ └──────────────────┘ │          │ ┌──────────────────────┐ │
│                      │          │ │   Shell/Commands     │ │
│ ┌──────────────────┐ │          │ │  - execute()         │ │
│ │ doc_generator    │ │          │ │  - run_script()      │ │
│ │                  │ │          │ │  - check_status()    │ │
│ │ • Code Parsers   │ │          │ └──────────────────────┘ │
│ │ • Templates      │ │          │                          │
│ │ • Diagrams       │ │          │ ┌──────────────────────┐ │
│ │ • Formatters     │ │          │ │   API/External       │ │
│ └──────────────────┘ │          │ │  - http_request()    │ │
│                      │          │ │  - query_db()        │ │
│ ┌──────────────────┐ │          │ │  - call_service()    │ │
│ │ data_pipeline    │ │          │ └──────────────────────┘ │
│ │                  │ │          │                          │
│ │ • Extractors     │ │          │ ┌──────────────────────┐ │
│ │ • Transformers   │ │          │ │   Analysis Tools     │ │
│ │ • Validators     │ │          │ │  - parse_code()      │ │
│ │ • Loaders        │ │          │ │  - validate_schema() │ │
│ └──────────────────┘ │          │ │  - calc_metrics()    │ │
│                      │          │ └──────────────────────┘ │
│                      │          │                          │
└──────────┬───────────┘          └───────────┬──────────────┘
           │                                  │
           │ Skill Output                     │ Tool Results
           │                                  │
           └─────────────┬────────────────────┘
                         │
                         ▼
           ┌──────────────────────────────┐
           │    CLAUDE ENGINE (Layer 3)   │
           │                              │
           │  ┌────────────────────────┐  │
           │  │      VALIDATOR         │  │
           │  │ • Check acceptance     │  │
           │  │ • Verify consistency   │  │
           │  │ • Validate format      │  │
           │  │ • Cross-reference      │  │
           │  └──────────┬─────────────┘  │
           │             │                │
           │             ▼                │
           │  ┌────────────────────────┐  │
           │  │     CLARIFIER          │  │
           │  │ • Detect ambiguity     │  │
           │  │ • Ask questions        │  │
           │  │ • Document assumptions │  │
           │  └──────────┬─────────────┘  │
           │             │                │
           │             ▼                │
           │  ┌────────────────────────┐  │
           │  │   STATE MANAGER        │  │
           │  │ • Track progress       │  │
           │  │ • Maintain context     │  │
           │  │ • Manage checkpoints   │  │
           │  │ • Coordinate parallel  │  │
           │  └──────────┬─────────────┘  │
           └─────────────┼────────────────┘
                         │
                         │ Results + Metadata
                         │
                         ▼
           ┌──────────────────────────────┐
           │    Aggregated & Validated    │
           │         Deliverable          │
           └──────────────┬───────────────┘
                          │
                          ▼
           ┌──────────────────────────────┐
           │         USER (Layer 5)       │
           │       Receives Output        │
           └──────────────────────────────┘
```

## Data Flow Legend

```
→  Direct flow
▼  Downward delegation
┌─┐ Component boundary
│  Organizational grouping
```

## Key Interactions

### 1. Top-Down: Intent → Execution
```
USER provides intent
  → .claude.md applies global constraints
    → ENGINE plans and routes
      → SKILLS/TOOLS execute
```

### 2. Bottom-Up: Results → Validation
```
TOOLS produce raw results
  → SKILLS structure and enrich
    → ENGINE validates and aggregates
      → .claude.md enforces quality standards
        → USER receives final deliverable
```

### 3. Feedback Loop: Clarification
```
ENGINE detects ambiguity
  → Asks USER targeted question
    → USER provides clarification
      → ENGINE updates plan
        → Execution continues
```

## Checkpoint Flow

```
Start
  │
  ▼
┌────────────────┐
│ Parse Intent   │ ← Checkpoint 1: Understanding confirmed?
└───────┬────────┘
        │
        ▼
┌────────────────┐
│ Plan Tasks     │ ← Checkpoint 2: Plan feasible?
└───────┬────────┘
        │
        ▼
┌────────────────┐
│ Execute Step   │ ← Checkpoint 3: Step successful?
└───────┬────────┘
        │
        ▼
┌────────────────┐
│ Validate       │ ← Checkpoint 4: Output valid?
└───────┬────────┘
        │
        ├─ NO → Retry or Adjust Plan
        │
        ▼ YES
┌────────────────┐
│ More Steps?    │
└───────┬────────┘
        │
        ├─ YES → Back to Execute Step
        │
        ▼ NO
┌────────────────┐
│ Final Quality  │ ← Checkpoint 5: All criteria met?
│     Check      │
└───────┬────────┘
        │
        ▼
   Deliver to User
```

## Layer Responsibilities Summary

| Layer | Responsibility | Key Question |
|-------|---------------|--------------|
| **User** | Define what success looks like | "What do I need?" |
| **.claude.md** | Define what's allowed | "What are the rules?" |
| **Engine** | Decide how to proceed | "What's the best approach?" |
| **Skills** | Encapsulate expertise | "How do experts do this?" |
| **Tools** | Perform concrete actions | "What can I actually do?" |

---

# Multi-Agent System Flow Diagram

## System Architecture Overview

```
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│                          USER REQUEST                            │
│         "Build authentication system with email/password"        │
│                                                                  │
└────────────────────────────┬─────────────────────────────────────┘
                             │
                             ▼
┌────────────────────────────────────────────────────────────────────┐
│                                                                    │
│              TECHNICAL LEAD AGENT (Coordinator)                    │
│                                                                    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐   │
│  │Parse Request │→ │  Decompose   │→ │  Route to Specialists│   │
│  └──────────────┘  └──────────────┘  └──────────┬───────────┘   │
│                                                  │               │
│  ┌──────────────────────────────────────────────┘               │
│  │                                                                │
│  │  Routing Decision Tree:                                       │
│  │  • Feature request → Requirements Analyst                     │
│  │  • Design needed → System Architect                           │
│  │  • Code needed → Code Developer                               │
│  │  • Testing needed → QA Tester                                 │
│  │  • Docs needed → Documentation Specialist                     │
│  │                                                                │
└────┬────────────────────┬────────────────────┬───────────────┬───┘
     │                    │                    │               │
     │ Task 1             │ Task 2             │ Task 3        │ Task 4
     │                    │ (depends on 1)     │ (depends on 2)│ (depends on 3)
     ▼                    ▼                    ▼               ▼
┌──────────┐         ┌──────────┐        ┌──────────┐    ┌──────────┐
│          │         │          │        │          │    │          │
│REQUIRE-  │────────▶│ SYSTEM   │───────▶│   CODE   │───▶│QA TESTER │
│  MENTS   │ Output  │ARCHITECT │ Design │DEVELOPER │Code│  AGENT   │
│ ANALYST  │         │  AGENT   │        │  AGENT   │    │          │
│  AGENT   │         │          │        │          │    │          │
│          │         │          │        │          │    │          │
└──────────┘         └──────────┘        └──────────┘    └────┬─────┘
     │                    │                    │              │
     │                    │                    │              │
     │                    │                    │              │ Parallel
     │                    │                    │              │ Execution
     │                    │                    │              │
     │                    │                    │              ▼
     │                    │                    │         ┌──────────┐
     │                    │                    │         │   DOC    │
     │                    │                    └────────▶│SPECIALIST│
     │                    │                              │  AGENT   │
     │                    │                              └────┬─────┘
     │                    │                                   │
     │                    │                                   │
     └────────────────────┴───────────────────────────────────┘
                          │
                          │ All outputs collected
                          │
                          ▼
┌────────────────────────────────────────────────────────────────────┐
│                 TECHNICAL LEAD AGENT (Coordinator)                 │
│                                                                    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐   │
│  │   Aggregate  │→ │   Validate   │→ │  Resolve Conflicts   │   │
│  │   Outputs    │  │ Completeness │  │                      │   │
│  └──────────────┘  └──────────────┘  └──────────┬───────────┘   │
│                                                  │               │
│  Quality Gates:                                  │               │
│  ✓ All acceptance criteria met?                 │               │
│  ✓ Requirements ↔ Tests aligned?                │               │
│  ✓ Design ↔ Code consistent?                    │               │
│  ✓ No unresolved conflicts?                     ▼               │
│                                        ┌──────────────────┐      │
│                                        │  Generate Final  │      │
│                                        │   Deliverable    │      │
│                                        └────────┬─────────┘      │
└─────────────────────────────────────────────────┼────────────────┘
                                                  │
                                                  ▼
                                     ┌──────────────────────┐
                                     │    USER RECEIVES     │
                                     │  Complete Solution   │
                                     └──────────────────────┘
```

## Detailed Agent Communication Flow

```
Time  │ Agent              │ Action                      │ Output
──────┼────────────────────┼─────────────────────────────┼──────────────────
00:00 │ TechLead          │ Receive user request        │ Parse intent
00:01 │ TechLead          │ Route to Req Analyst        │ Task assignment
00:02 │ Requirements      │ Generate user stories       │ Requirements doc
      │ Analyst           │                             │ • 3 user stories
      │                   │                             │ • 8 acceptance criteria
00:03 │ TechLead          │ Validate requirements       │ ✓ Complete
00:04 │ TechLead          │ Route to Architect          │ Task + requirements
00:15 │ System            │ Design architecture         │ Design doc
      │ Architect         │                             │ • 4 components
      │                   │                             │ • API contracts
      │                   │                             │ • DB schema
00:16 │ TechLead          │ Validate design             │ ✓ Consistent
00:17 │ TechLead          │ Route to Developer          │ Task + design
01:23 │ Code              │ Implement features          │ Source code
      │ Developer         │                             │ • 12 files
      │                   │                             │ • 847 LOC
01:24 │ TechLead          │ Check code completeness     │ ✓ All specs met
01:25 │ TechLead          │ Route to QA (parallel)      │ Code + requirements
01:25 │ TechLead          │ Route to Docs (parallel)    │ Code + design
01:45 │ QA Tester         │ Run test suite              │ Test results
      │                   │                             │ • 36/36 passed
      │                   │                             │ • 94% coverage
01:52 │ Documentation     │ Generate docs               │ Documentation
      │ Specialist        │                             │ • README
      │                   │                             │ • API docs
01:53 │ TechLead          │ Aggregate all outputs       │ Combined package
01:54 │ TechLead          │ Final validation            │ ✓ Quality score: 92
01:55 │ TechLead          │ Deliver to user             │ Complete solution
```

## Agent Routing Decision Matrix

```
┌─────────────────┬──────────────────────────────────────────────────┐
│ Request Pattern │ Agent Route                                      │
├─────────────────┼──────────────────────────────────────────────────┤
│ "feature"       │ Requirements Analyst                             │
│ "requirement"   │                                                  │
│ "user story"    │                                                  │
├─────────────────┼──────────────────────────────────────────────────┤
│ "design"        │ System Architect                                 │
│ "architecture"  │ (Requires: Requirements)                         │
│ "system"        │                                                  │
├─────────────────┼──────────────────────────────────────────────────┤
│ "implement"     │ Code Developer                                   │
│ "code"          │ (Requires: Architecture)                         │
│ "build"         │                                                  │
├─────────────────┼──────────────────────────────────────────────────┤
│ "test"          │ QA Tester                                        │
│ "validate"      │ (Requires: Code)                                 │
│ "verify"        │                                                  │
├─────────────────┼──────────────────────────────────────────────────┤
│ "document"      │ Documentation Specialist                         │
│ "README"        │ (Requires: Code, can run parallel with QA)       │
│ "API docs"      │                                                  │
├─────────────────┼──────────────────────────────────────────────────┤
│ "complete"      │ ALL agents in sequence:                          │
│ "end-to-end"    │ Analyst → Architect → Developer →                │
│ "full feature"  │ [QA + Docs in parallel]                          │
└─────────────────┴──────────────────────────────────────────────────┘
```

## Conflict Resolution Flow

```
                    ┌─────────────────────┐
                    │ Conflict Detected   │
                    └──────────┬──────────┘
                               │
                ┌──────────────┴──────────────┐
                │                             │
          Type 1: Spec              Type 2: Test
          Conflicts                  Failures
                │                             │
                ▼                             ▼
      ┌──────────────────┐         ┌──────────────────┐
      │ Compare Outputs  │         │ Return to        │
      │ Architect vs Dev │         │ Developer        │
      └────────┬─────────┘         └────────┬─────────┘
               │                            │
               ▼                            ▼
      ┌──────────────────┐         ┌──────────────────┐
      │ Developer has    │         │ Developer fixes  │
      │ documented       │         │ Max 3 iterations │
      │ rationale?       │         └────────┬─────────┘
      └────┬─────────────┘                  │
           │                                │
    ┌──────┴──────┐                         │
   YES            NO                        │
    │              │                        │
    ▼              ▼                        ▼
Update Arch    Rollback to        ┌──────────────────┐
Document       Spec               │ If still failing:│
    │              │               │ Escalate to User │
    │              │               └──────────────────┘
    └──────┬───────┘
           │
           ▼
   ┌──────────────────┐
   │ Continue Workflow│
   └──────────────────┘

                ┌──────────────────────────┐
                │                          │
          Type 3: Ambiguous       Type 4: Performance
          Requirements             vs Quality
                │                          │
                ▼                          ▼
      ┌──────────────────┐       ┌──────────────────┐
      │ Create comparison│       │ Evaluate severity│
      │ Present to User  │       └────────┬─────────┘
      └────────┬─────────┘                │
               │                   ┌──────┴──────┐
               ▼               Critical    Non-Critical
      ┌──────────────────┐        │              │
      │ User clarifies   │        ▼              ▼
      │ Requirements     │   Redesign      Document &
      └────────┬─────────┘   Architecture  Add to Backlog
               │                │              │
               ▼                └──────┬───────┘
      ┌──────────────────┐            │
      │ Re-run affected  │            │
      │ agents           │            │
      └──────────────────┘            │
               │                      │
               └──────────┬───────────┘
                          │
                          ▼
                  Continue Workflow
```

## Parallel Execution Example

```
Step 3 Complete: Code Developer finishes implementation
            │
            └─────────┬──────────────────────────┐
                      │                          │
                      ▼                          ▼
            ┌──────────────────┐      ┌──────────────────┐
            │   QA TESTER      │      │ DOCUMENTATION    │
            │                  │      │  SPECIALIST      │
            │ Running:         │      │                  │
            │ • Unit tests     │      │ Generating:      │
            │ • Integration    │      │ • README         │
            │ • Performance    │      │ • API docs       │
            │ • Security       │      │ • Setup guide    │
            │                  │      │                  │
            │ Time: ~20 min    │      │ Time: ~25 min    │
            └────────┬─────────┘      └────────┬─────────┘
                     │                         │
                     └────────┬────────────────┘
                              │
                    Both complete at ~25 min
                              │
                              ▼
            ┌──────────────────────────────────┐
            │   TECHNICAL LEAD                 │
            │   Merge both outputs             │
            │   • Tests results + Documentation│
            └──────────────────────────────────┘
```

## Final Merge Strategy Visualization

```
┌────────────────────────────────────────────────────────────────┐
│              TECHNICAL LEAD: Merge Process                     │
└───────────────────┬────────────────────────────────────────────┘
                    │
                    ▼
      ┌─────────────────────────────────┐
      │ Collect All Agent Outputs       │
      └──────────┬──────────────────────┘
                 │
    ┌────────────┼────────────┐
    │            │            │
    ▼            ▼            ▼
┌────────┐  ┌────────┐  ┌─────────┐
│ Req    │  │ Design │  │  Code   │
│ Docs   │  │ Docs   │  │ Files   │
└────┬───┘  └───┬────┘  └────┬────┘
     │          │            │
     └──────────┴────────────┘
                 │
                 ▼
      ┌──────────────────────┐
      │ Cross-Reference      │
      │ • Req ↔ Tests        │
      │ • Design ↔ Code      │
      │ • API spec ↔ Impl    │
      └──────────┬───────────┘
                 │
                 ▼
      ┌──────────────────────┐
      │ Validate Consistency │
      └──────────┬───────────┘
                 │
          ┌──────┴──────┐
         OK            Issues
          │              │
          ▼              ▼
    ┌─────────┐   ┌──────────────┐
    │Continue │   │Resolve or    │
    │         │   │Escalate      │
    └────┬────┘   └──────┬───────┘
         │               │
         └───────┬───────┘
                 │
                 ▼
      ┌──────────────────────┐
      │ Generate Metadata    │
      │ • Execution time     │
      │ • Quality score      │
      │ • Coverage metrics   │
      └──────────┬───────────┘
                 │
                 ▼
      ┌──────────────────────┐
      │ Package Deliverable  │
      │ {                    │
      │   summary: "...",    │
      │   requirements: {},  │
      │   design: {},        │
      │   implementation: {},│
      │   validation: {},    │
      │   documentation: {}  │
      │ }                    │
      └──────────┬───────────┘
                 │
                 ▼
      ┌──────────────────────┐
      │ Deliver to User      │
      └──────────────────────┘
```

## Agent Handoff Protocol

```
Agent A completes work
        │
        ▼
┌────────────────────┐
│ Create Output      │
│ Package:           │
│ • Results          │
│ • Metadata         │
│ • Confidence       │
│ • Warnings         │
└────────┬───────────┘
         │
         ▼
┌────────────────────┐
│ Validate Output    │
│ meets Contract     │
└────────┬───────────┘
         │
    ┌────┴────┐
   YES       NO
    │         │
    │         ▼
    │    ┌────────────┐
    │    │ Flag Issue │
    │    │ Retry      │
    │    └──────┬─────┘
    │           │
    │           │
    └─────┬─────┘
          │
          ▼
┌────────────────────┐
│ Send to TechLead   │
└────────┬───────────┘
         │
         ▼
┌────────────────────┐
│ TechLead Validates │
│ & Routes to Next   │
│ Agent              │
└────────┬───────────┘
         │
         ▼
    Agent B receives
    work package
```

## System Scaling Visualization

```
Simple Request (1 agent):
USER → TechLead → Single Agent → TechLead → USER
       (Router)                   (Validator)

Medium Request (2-3 agents):
USER → TechLead → Agent A → Agent B → TechLead → USER
                     ↓         ↓
                  Output    Output
                     └────┬────┘
                       Merge

Complex Request (4+ agents):
                    TechLead
                        │
        ┌───────┬───────┼───────┬───────┐
        │       │       │       │       │
     Agent1  Agent2  Agent3  Agent4  Agent5
        │       │       │       │       │
        │       │       │       └───┬───┘
        │       │       │       Parallel
        │       │       │           │
        └───┬───┴───┬───┴───────────┘
            │       │
         Merge   Merge
            │       │
            └───┬───┘
            TechLead
                │
              USER
```

# Tasks D, E, F, G - Complete Documentation

This document contains the complete implementations for Tasks D (Engine Coordination), E (Agent Basics), F (Agent Designs), and G (Multi-Agent Orchestration).

---

# Task D: Claude Engine - Coordination & Validation

## Overview
The Claude engine serves as the central orchestrator in the architecture, bridging user intent with execution capabilities. It acts as a sophisticated reasoning system that manages the entire workflow lifecycle.

## Core Coordination Functions

### 1. Task Decomposition (Planner)
The engine breaks down complex requests into manageable subtasks:
- Analyzes user intent to identify core objectives
- Identifies dependencies between subtasks
- Creates a logical execution sequence
- Establishes checkpoints for validation
- Maintains flexibility to adjust plans based on intermediate results

### 2. Skill/Tool Selection (Router)
The engine intelligently chooses appropriate resources:
- Matches task requirements to available skills
- Evaluates tool capabilities against needs
- Considers safety constraints and permissions
- Selects optimal execution paths
- Falls back to alternative approaches when primary methods fail

### 3. Output Validation (Checker)
The engine ensures quality and correctness:
- Verifies outputs against acceptance criteria
- Cross-references results with input requirements
- Checks for logical consistency
- Validates format compliance
- Flags anomalies or unexpected results

### 4. Ambiguity Handling (Clarifier)
The engine manages uncertainty intelligently:
- Distinguishes between safe assumptions and critical unknowns
- Asks targeted questions for missing critical information
- Documents assumptions made during execution
- Provides confidence levels for uncertain outputs
- Escalates when ambiguity affects mission-critical decisions

### 5. Multi-Step Workflow Management (State Manager)
The engine maintains execution context:
- Tracks progress through workflow stages
- Preserves intermediate results
- Manages rollback points for error recovery
- Coordinates parallel execution streams
- Synthesizes outputs from multiple steps

## Workflow Example: Security Audit Request

**User Request:** "Audit our authentication system for security vulnerabilities and provide remediation recommendations."

**Execution Trace:**

```
Step 1: INTENT ANALYSIS
- Engine: Parse request → identify scope (auth system), objective (security audit), deliverable (recommendations)
- Decision: Multi-phase workflow required
- Checkpoint: Scope confirmed

Step 2: INFORMATION GATHERING
- Engine: Check for missing inputs
- Action: Query user for codebase location, authentication type, compliance requirements
- User provides: GitHub repo URL, OAuth 2.0 + JWT, SOC2 compliance needed
- Checkpoint: Context complete

Step 3: SKILL SELECTION & DECOMPOSITION
- Engine: Route to skill/audit_crypto + skill/code_scanner
- Decompose into subtasks:
  a) Scan authentication endpoints
  b) Analyze token handling
  c) Check encryption methods
  d) Review session management
  e) Verify access controls
- Checkpoint: Execution plan validated

Step 4: PARALLEL EXECUTION
- Engine: Invoke skill/code_scanner → file_system.read + pattern_matching
- Tool calls:
  - read_file("auth/oauth_handler.py")
  - read_file("auth/jwt_manager.py")
  - search_pattern("crypto\.|hashlib\.|secrets\.")
- Checkpoint: Data collected (47 files scanned)

Step 5: ANALYSIS & VALIDATION
- Engine: Process scan results using skill/audit_crypto
- Findings identified:
  - JWT secret in environment variable (medium risk)
  - SHA-256 for password hashing (OUTDATED - should be bcrypt/argon2)
  - No rate limiting on login endpoint (high risk)
  - Token expiration set to 24h (excessive)
- Engine validates: Cross-check findings against OWASP Top 10 + SOC2 requirements
- Checkpoint: Findings validated against security standards

Step 6: REMEDIATION PLANNING
- Engine: Route to skill/remediation_planner
- Generate prioritized action plan:
  - Priority 1: Implement rate limiting (prevents brute force)
  - Priority 2: Migrate to bcrypt with cost factor 12
  - Priority 3: Reduce token expiration to 1h with refresh tokens
  - Priority 4: Move JWT secret to secure vault
- Checkpoint: Plan feasibility verified

Step 7: OUTPUT SYNTHESIS
- Engine: Compile final report per .claude.md requirements
- Format: Executive Summary + Detailed Findings + Remediation Roadmap + Test Cases
- Validate: Ensure all sections complete, technical accuracy confirmed
- Checkpoint: Quality checklist passed

Step 8: DELIVERY & FOLLOWUP
- Engine: Present report to user
- Offer: "Generate implementation code for rate limiter?" or "Create migration script for bcrypt?"
- Track: User acceptance, additional requests
- Final Checkpoint: Mission complete
```

## Key Principles

**Adaptive Planning:** The engine adjusts its approach based on intermediate results rather than rigidly following a predetermined path.

**Fail-Safe Validation:** Multiple checkpoints ensure errors are caught early before propagating to subsequent steps.

**Context Preservation:** All state is maintained throughout execution, enabling coherent multi-turn workflows.

**Transparent Reasoning:** The engine can explain its decisions and show its work at any checkpoint.

---

# Task E: Agent Basics (Conceptual)

## What is an Agent?

In Claude-style workflows, an **agent** is a specialized, goal-oriented component with a defined scope of responsibility, explicit permissions, and built-in guardrails. Unlike simple functions or scripts, agents exhibit autonomous decision-making within their boundaries, can use tools strategically, and maintain awareness of their mission context.

## Core Agent Components

### 1. Role & Mission
The agent's primary purpose and value proposition. This defines what problem the agent solves and what success looks like. For example, a "Security Auditor" agent's mission is to identify vulnerabilities and assess risk, while a "Documentation Generator" agent's mission is to create clear, accurate technical documentation.

### 2. Scope Boundaries
Explicit limitations on what the agent must NOT do. This prevents mission creep and ensures safety. For instance, an auditor agent should not attempt to fix vulnerabilities it finds—only report them. A documentation agent should not modify source code.

### 3. Tool Permissions
A whitelist of tools the agent is authorized to use. This implements the principle of least privilege. A read-only analyst agent might only access file reading and search tools, while a deployment agent needs shell execution and file writing capabilities.

### 4. Policies & Guardrails
Safety and quality constraints that govern agent behavior:
- Safety rules (no deletion of production data, no credential exposure)
- Quality standards (code must be tested, documentation must include examples)
- Compliance requirements (PII redaction, audit logging)
- Error handling protocols (what to do when uncertain)

### 5. Inputs & Outputs
Clearly defined interfaces for interaction:
- Inputs: Required data, optional parameters, context needs
- Outputs: Structured deliverables, status reports, confidence levels
- Format specifications: JSON schemas, markdown templates, etc.

### 6. Memory Strategy
What information the agent retains and for how long:
- Session memory: Current task context and intermediate results
- Working memory: Recent interactions for coherence
- Long-term memory: Patterns learned from past executions (if applicable)
- Forgetting policy: What data should be discarded for privacy/efficiency

### 7. Evaluation Rubric
Measurable criteria for success:
- Objective metrics (accuracy, completeness, response time)
- Subjective criteria (clarity, usefulness, alignment with intent)
- Failure conditions (when to abort, when to escalate)

## Agent Patterns

### Pattern 1: Single-Agent Architecture

In this pattern, one generalist agent handles the entire workflow using a comprehensive toolset.

**Structure:**
```
User Request → Single Agent → Tools → Results → User
```

**Characteristics:**
- Agent has broad capabilities and multiple tool permissions
- Agent performs planning, execution, and validation internally
- Simpler architecture with fewer coordination overheads
- Agent maintains all context in its working memory

**Best For:**
- Straightforward tasks with clear workflows
- Situations where context shouldn't be fragmented
- Rapid prototyping and simple automation
- Personal productivity tools

**Example: Personal Research Assistant**
```
Agent: Research Assistant
Mission: Help user gather, analyze, and summarize information on any topic
Tools: web_search, web_fetch, file_write, code_execution
Workflow:
  1. Understand research question
  2. Search for relevant sources
  3. Fetch and analyze content
  4. Synthesize findings
  5. Generate structured report
```

**Limitations:**
- Can become overwhelmed with complex, multi-domain tasks
- Harder to enforce specialized expertise
- Difficult to parallelize work
- Single point of failure

### Pattern 2: Multi-Agent Architecture

In this pattern, a coordinator agent delegates to specialized agents, each focused on a specific domain or capability.

**Structure:**
```
User Request → Coordinator Agent → [Specialist Agent 1, Specialist Agent 2, ...] → Tools → Coordinator → User
```

**Characteristics:**
- Clear separation of concerns with domain expertise
- Coordinator handles routing, not execution
- Specialists are highly optimized for their domain
- Enables parallel execution of independent tasks
- Built-in quality assurance through specialization

**Best For:**
- Complex workflows requiring diverse expertise
- Tasks benefiting from parallel execution
- Scenarios requiring domain-specific validation
- Enterprise-scale automation systems

**Example: Software Development Team**
```
Coordinator: Technical Lead
  Mission: Manage development workflow from requirements to deployment
  
Specialists:
  - Requirements Analyst: Extract and structure requirements from descriptions
  - Architect: Design system structure and component interfaces
  - Developer: Implement code following architectural specs
  - Tester: Generate test cases and validate implementation
  - Documenter: Create technical documentation
  
Workflow:
  1. Coordinator receives project request
  2. Routes to Requirements Analyst → structured requirements doc
  3. Routes to Architect → system design
  4. Routes to Developer → implementation (may iterate)
  5. Routes to Tester → validation results
  6. If tests fail → back to Developer
  7. Routes to Documenter → final documentation
  8. Coordinator compiles complete deliverable
```

**Coordination Mechanisms:**
- **Sequential:** Agent B starts only after Agent A completes
- **Parallel:** Multiple agents work simultaneously on independent subtasks
- **Iterative:** Agents pass results back and forth until quality threshold met
- **Hierarchical:** Coordinator delegates to sub-coordinators for complex domains

**Advantages:**
- Superior quality through specialized expertise
- Scalability through parallelization
- Easier to test and validate individual components
- Better error isolation and recovery

**Challenges:**
- Higher complexity in coordination logic
- Context sharing between agents must be managed
- Potential for inconsistent outputs if not properly integrated
- Requires sophisticated conflict resolution

## Choosing Between Patterns

**Use Single-Agent when:**
- Task is well-defined and linear
- Context must remain unified throughout
- Speed of execution is critical (less coordination overhead)
- System complexity must be minimized

**Use Multi-Agent when:**
- Task requires diverse domain expertise
- Different subtasks can be parallelized
- Quality benefits from specialized validation
- System will grow and evolve over time
- Failure isolation is important

---

# Task F: Build 2 Agents (Practical Design)

## Agent 1: Security Vulnerability Scanner

### 1. Agent Name
**VulnScanner Agent**

### 2. Purpose / Mission
Systematically analyze codebases, configurations, and dependencies to identify security vulnerabilities, assess their severity, and provide actionable remediation guidance aligned with industry standards (OWASP, CWE, CVE).

### 3. Responsibilities
- Scan source code for security anti-patterns (SQL injection, XSS, CSRF, etc.)
- Analyze dependencies for known vulnerabilities (CVEs)
- Review authentication and authorization implementations
- Identify secrets, credentials, and sensitive data exposure
- Check cryptographic implementation quality
- Evaluate security headers and configurations
- Generate risk-prioritized vulnerability reports
- Provide specific remediation recommendations with code examples

### 4. Out-of-Scope
- Implementing fixes (only recommends, does not modify code)
- Performing penetration testing or active exploitation
- Making architectural decisions about system redesign
- Guaranteeing complete security (provides best-effort analysis)
- Runtime security monitoring or intrusion detection
- Compliance certification or legal assessment

### 5. Inputs Required
- **Required:**
  - Codebase location (file paths or repository URL)
  - Programming languages/frameworks used
  - Scan depth level (quick/standard/deep)
  
- **Optional:**
  - Compliance framework to check against (SOC2, PCI-DSS, HIPAA, etc.)
  - Known false positives to exclude
  - Priority areas or specific file patterns
  - Risk tolerance threshold

### 6. Outputs Produced
- **Structured Vulnerability Report:**
  - Executive Summary (total findings by severity)
  - Detailed Findings List (each with: CWE/CVE ID, severity, location, description, evidence)
  - Remediation Roadmap (prioritized action items)
  - Code Examples (vulnerable code vs. secure alternative)
  - Compliance Gaps (if framework specified)
  - False Positive Assessment
  - Scan Metadata (timestamp, coverage percentage, tool versions)

### 7. Tools Allowed
- `file_system.read` - Read source files and configurations
- `file_system.search` - Pattern matching across codebase
- `code_execution` - Run static analysis tools (Bandit, Semgrep, ESLint security plugins)
- `web_search` - Look up CVE details and security advisories
- `web_fetch` - Retrieve OWASP guidelines and CWE descriptions

### 8. Rules & Guardrails
- **Safety:**
  - Never execute potentially malicious code from the codebase
  - Do not expose secrets found during scanning in logs or reports (redact with `***`)
  - Do not make network calls to external services from user's code
  
- **Quality:**
  - Validate each finding with evidence (line numbers, code snippets)
  - Severity ratings must follow CVSS scoring or equivalent standard
  - Every vulnerability must include a remediation recommendation
  - False positive rate target: <10%
  
- **Privacy:**
  - Redact PII, API keys, passwords in all outputs
  - Do not store sensitive findings beyond session memory
  
- **Transparency:**
  - Clearly mark findings with confidence levels (High/Medium/Low)
  - Distinguish between confirmed vulnerabilities and potential issues

### 9. Decision Policy
**When to Ask:**
- User's risk tolerance is unclear (ask severity threshold for reporting)
- Ambiguous finding could be either vulnerability or intentional design
- Codebase uses unfamiliar framework (ask for context)
- Multiple remediation approaches with different tradeoffs

**When to Assume:**
- Standard security best practices apply unless told otherwise
- Common frameworks follow documented security patterns
- Modern encryption standards preferred over legacy (e.g., bcrypt over MD5)
- Higher security is preferred when in doubt

**When to Escalate:**
- Critical severity vulnerability found in production code
- Evidence of active credential compromise
- Widespread systemic security failures (>50 high-severity findings)

### 10. Quality Checklist
Before delivering report, verify:
- [ ] All findings include: severity, location, description, remediation
- [ ] Evidence provided for each vulnerability (code snippet or log)
- [ ] Severity ratings justified with CVSS scores or rationale
- [ ] Remediation recommendations are specific and actionable
- [ ] No false positives from known exclusion list
- [ ] All secrets/PII redacted from output
- [ ] Executive summary accurately reflects detailed findings
- [ ] Report format matches .claude.md requirements
- [ ] Scan coverage percentage calculated and reported
- [ ] Findings sorted by severity (Critical → High → Medium → Low)

### 11. Example Runs

**Example 1: Quick Scan of Python Flask App**

*Input:*
```json
{
  "codebase_path": "/project/flask-api",
  "languages": ["python"],
  "scan_depth": "quick",
  "framework": "Flask"
}
```

*Output:*
```markdown
# Security Vulnerability Report
**Generated:** 2026-01-18 14:32 UTC
**Scan Coverage:** 87% (26/30 files)

## Executive Summary
- Critical: 1
- High: 3
- Medium: 5
- Low: 2
- Total: 11 findings

## Critical Findings

### [C-001] SQL Injection Vulnerability
- **Severity:** Critical (CVSS 9.8)
- **CWE:** CWE-89
- **Location:** `app/routes/user.py:45`
- **Evidence:**
```python
query = f"SELECT * FROM users WHERE username = '{username}'"
cursor.execute(query)
```
- **Risk:** Allows arbitrary SQL execution, potential data breach
- **Remediation:** Use parameterized queries
```python
query = "SELECT * FROM users WHERE username = ?"
cursor.execute(query, (username,))
```

## Remediation Roadmap
1. **Immediate (Critical):** Fix SQL injection in user.py (Est: 30 min)
2. **This Week (High):** Rotate and externalize secret keys (Est: 2 hours)
3. **This Sprint (Medium):** Implement rate limiting on auth endpoints (Est: 4 hours)
```

**Example 2: Deep Compliance Scan for Healthcare App**

*Input:*
```json
{
  "codebase_path": "/project/health-records",
  "languages": ["javascript", "typescript"],
  "scan_depth": "deep",
  "compliance_framework": "HIPAA",
  "priority_areas": ["patient_data", "authentication"]
}
```

*Output:*
```markdown
# Security & HIPAA Compliance Report
**Generated:** 2026-01-18 15:47 UTC
**Compliance Framework:** HIPAA Security Rule
**Scan Coverage:** 94% (156/166 files)

## Executive Summary
- HIPAA Compliance: **Non-Compliant** (8 critical gaps)
- Security Findings: 23 total (4 Critical, 7 High, 9 Medium, 3 Low)

## HIPAA Compliance Gaps

### [HIPAA-001] Insufficient Audit Logging
- **Requirement:** §164.312(b) - Audit Controls
- **Finding:** Patient record access not logged
- **Location:** `services/patient-service.ts:89-112`
- **Impact:** Cannot detect unauthorized PHI access
- **Remediation:** Implement comprehensive audit logging

## Remediation Roadmap (HIPAA Priority)
1. **Immediate:** Remove authentication bypass (C-002)
2. **This Week:** Implement audit logging (HIPAA-001, HIPAA-003)
3. **This Sprint:** Enable HTTPS everywhere (HIPAA-002)
4. **This Month:** Encrypt database backups (HIPAA-004)
```

---

## Agent 2: Technical Documentation Generator

### 1. Agent Name
**DocGen Agent**

### 2. Purpose / Mission
Automatically generate clear, comprehensive, and maintainable technical documentation from codebases, APIs, and system specifications, ensuring developers and stakeholders have accurate, up-to-date reference materials.

### 3. Responsibilities
- Analyze source code to extract structure, functions, classes, and modules
- Generate API reference documentation with endpoint details
- Create architecture diagrams and system overviews
- Write usage examples and integration guides
- Document configuration options and environment variables
- Generate changelog summaries from git history
- Create README files with setup instructions
- Produce onboarding guides for new developers
- Maintain consistent documentation style and formatting

### 4. Out-of-Scope
- Writing marketing copy or sales materials
- Making architectural recommendations or refactoring code
- Creating user-facing product documentation (focuses on technical docs)
- Translating documentation to multiple languages
- Hosting or deploying documentation sites
- Writing tutorials on programming concepts (focuses on project-specific docs)

### 5. Inputs Required
- **Required:**
  - Codebase location (file paths or repository)
  - Documentation type (API reference, README, architecture, etc.)
  - Target audience (internal developers, external contributors, API consumers)
  
- **Optional:**
  - Existing documentation to update/enhance
  - Documentation style guide or template
  - Specific sections to focus on
  - Examples of good documentation to emulate
  - Output format preference (Markdown, reStructuredText, HTML, etc.)

### 6. Outputs Produced
- **Documentation Artifacts:**
  - README.md (project overview, setup, usage)
  - API_REFERENCE.md (endpoints, parameters, responses)
  - ARCHITECTURE.md (system design, component diagrams)
  - CONTRIBUTING.md (development setup, guidelines)
  - CHANGELOG.md (version history)
  - Code comments (inline documentation)
  - Configuration documentation (env vars, settings)
  
- **Metadata:**
  - Documentation coverage report (% of code documented)
  - Missing documentation warnings
  - Quality assessment (readability, completeness)

### 7. Tools Allowed
- `file_system.read` - Read source code and existing documentation
- `file_system.write` - Write documentation files
- `file_system.search` - Find patterns, function definitions, config files
- `code_execution` - Run documentation generators (JSDoc, Sphinx, Doxygen)
- `web_search` - Look up framework conventions and documentation best practices
- `artifact_creation` - Generate formatted documentation artifacts

### 8. Rules & Guardrails
- **Accuracy:**
  - All code examples must be valid and tested
  - API documentation must match actual implementation
  - Version numbers and dependencies must be current
  - Never invent features or capabilities that don't exist
  
- **Clarity:**
  - Use simple language appropriate for target audience
  - Include examples for every major feature
  - Organize content logically (concept → usage → reference)
  - Avoid jargon without explanation
  
- **Completeness:**
  - Every public API/function should be documented
  - Required parameters must be clearly marked
  - Error conditions and exceptions must be documented
  - Security considerations highlighted where relevant
  
- **Maintainability:**
  - Use templates and consistent formatting
  - Include timestamps and version indicators
  - Link related documentation sections
  - Mark auto-generated sections clearly

### 9. Decision Policy
**When to Ask:**
- Target audience technical level is unclear
- Multiple documentation approaches possible (API-first vs. tutorial-first)
- Existing documentation conflicts with code (ask which is correct)
- Unclear whether to document internal/private methods

**When to Assume:**
- Follow language/framework documentation conventions (e.g., JSDoc for JavaScript)
- Public APIs need comprehensive documentation, private methods need minimal
- Examples should be simple and focused on one concept
- README should include quickstart before detailed reference

**When to Flag:**
- Significant code sections with zero comments
- Public APIs missing parameter descriptions
- Breaking changes without CHANGELOG entry
- Security-sensitive code lacking usage warnings

### 10. Quality Checklist
Before delivering documentation, verify:
- [ ] All public APIs/functions documented
- [ ] Code examples are syntactically valid
- [ ] Installation/setup instructions tested for completeness
- [ ] Links to external resources are valid
- [ ] Formatting is consistent throughout
- [ ] TOC (table of contents) included for docs >500 lines
- [ ] No placeholder text like "TODO" or "Coming soon" remains
- [ ] Version/date stamps included
- [ ] Examples include both success and error cases
- [ ] Security warnings included where appropriate

### 11. Example Runs

**Example 1: Generate README for Python Data Pipeline**

*Input:*
```json
{
  "codebase_path": "/project/data-pipeline",
  "doc_type": "README",
  "target_audience": "data engineers",
  "include_sections": ["overview", "setup", "usage", "configuration"]
}
```

*Output:*
````markdown
# Data Pipeline Framework

> A scalable Python framework for building ETL workflows with built-in monitoring and error recovery.

## Installation

```bash
pip install -r requirements.txt
python manage.py db init
```

## Usage

```python
from pipeline import Pipeline, PostgreSQLSource, S3Destination

pipeline = Pipeline(name="user_export")
source = PostgreSQLSource(query="SELECT * FROM users")
destination = S3Destination(bucket="data-exports")

pipeline.run(source=source, destination=destination)
```

## Configuration

| Variable | Description | Required |
|----------|-------------|----------|
| `DATABASE_URL` | PostgreSQL connection | Yes |
| `S3_BUCKET` | Default S3 bucket | No |
````

**Example 2: Generate API Reference for REST Service**

*Input:*
```json
{
  "codebase_path": "/project/payment-api",
  "doc_type": "API_REFERENCE",
  "target_audience": "external developers"
}
```

*Output:*
````markdown
# Payment API Reference

## Create Payment

**Endpoint:** `POST /payments`

**Request:**
```json
{
  "amount": 1999,
  "currency": "USD",
  "payment_method": "card_xyz123"
}
```

**Response (201):**
```json
{
  "id": "pay_1234567890",
  "status": "succeeded",
  "amount": 1999
}
```

**Errors:**
- `400`: Invalid amount
- `402`: Payment declined
````

---

# Task G: Multi-Agent Orchestration (Advanced)

## Multi-Agent Architecture: Software Development Team

This architecture implements a coordinated team of specialist agents for end-to-end software development.

## Agent Roster

### 1. Coordinator Agent: Technical Lead

**Name:** TechLead Coordinator

**Mission:** Orchestrate the complete software development workflow by routing tasks to appropriate specialists, managing dependencies, resolving conflicts, and ensuring deliverable quality.

**Responsibilities:**
- Parse user requirements and decompose into subtasks
- Route subtasks to appropriate specialist agents
- Manage workflow state and dependencies
- Aggregate outputs from multiple specialists
- Resolve conflicts between agent outputs
- Validate final deliverables against acceptance criteria
- Provide status updates and progress tracking

**Tools:** None directly (coordinates other agents)

**Routing Logic:**
```
IF request contains: "requirements", "user story", "feature request"
  → ROUTE to Requirements Analyst

IF request contains: "design", "architecture", "system structure"
  → ROUTE to System Architect

IF request contains: "implement", "code", "build"
  → ROUTE to Code Developer
  → DEPENDENCIES: Requires design from Architect

IF request contains: "test", "validate", "verify"
  → ROUTE to Quality Assurance
  → DEPENDENCIES: Requires code from Developer

IF request contains: "document", "README", "API docs"
  → ROUTE to Documentation Specialist
  → DEPENDENCIES: Can run parallel with testing
```

### 2. Specialist Agent: Requirements Analyst

**Mission:** Transform vague user requests into structured, testable requirements with acceptance criteria.

**Inputs:** Natural language feature descriptions, user stories, business goals

**Outputs:** 
- Structured requirements document
- User story format (As a... I want... So that...)
- Acceptance criteria checklist
- Edge cases and constraints

**Tools:** `web_search`, `file_write`

### 3. Specialist Agent: System Architect

**Mission:** Design scalable, maintainable system architecture with clear component boundaries.

**Inputs:** Requirements document

**Outputs:**
- System architecture diagram
- Component specifications
- Interface definitions
- Technology stack recommendations

**Tools:** `artifact_creation`, `web_search`, `file_write`

### 4. Specialist Agent: Code Developer

**Mission:** Write clean, tested, production-ready code following architecture specifications.

**Inputs:** Architecture design, component specifications

**Outputs:**
- Functional source code
- Unit tests
- Integration tests
- Error handling

**Tools:** `file_write`, `code_execution`, `file_read`

### 5. Specialist Agent: Quality Assurance

**Mission:** Ensure code correctness, edge case handling, and acceptance criteria fulfillment.

**Inputs:** Source code, requirements

**Outputs:**
- Test results report
- Coverage metrics
- Bug reports
- Pass/fail decision

**Tools:** `code_execution`, `file_read`, `file_write`

## Workflow Diagram

See `diagrams/multi_agent_flow.md` for detailed visualization.

## Routing Policy

```python
def route_request(request, current_state):
    if matches(request, ["feature", "requirement"]):
        return ["RequirementsAnalyst"]
    
    if matches(request, ["design", "architecture"]):
        if not current_state.has("requirements"):
            return ["RequirementsAnalyst", "SystemArchitect"]
        return ["SystemArchitect"]
    
    if matches(request, ["implement", "code"]):
        if not current_state.has("architecture"):
            return ["SystemArchitect", "CodeDeveloper"]
        return ["CodeDeveloper"]
    
    if matches(request, ["complete", "end-to-end"]):
        return [
            "RequirementsAnalyst",
            "SystemArchitect",
            "CodeDeveloper",
            ["QATester", "DocumentationSpecialist"]  # Parallel
        ]
```

## Conflict Resolution Strategy

### Type 1: Specification Conflicts
**Policy:** Architecture is source of truth unless Developer provides documented justification.

**Resolution:**
1. Technical Lead identifies discrepancy
2. Check if Developer documented rationale
3. If YES: Update architecture docs
4. If NO: Rollback to spec or escalate to user

### Type 2: Test Failures
**Policy:** Code must pass ALL tests before proceeding.

**Resolution:**
1. Send test report back to Developer
2. Developer fixes bugs and resubmits
3. Iterate maximum 3 times
4. If still failing: Escalate with detailed analysis

### Type 3: Requirements Ambiguity
**Policy:** Never guess user intent.

**Resolution:**
1. Create comparison document
2. Present to user for clarification
3. Update requirements
4. Re-run affected agents

### Type 4: Performance vs. Code Quality
**Resolution:**
- If critical (>500ms slower): Architect redesigns
- If non-critical (<20% variance): Document and add to backlog

## Final Merge Strategy

```python
def merge_outputs(requirements, architecture, code, tests, documentation):
    final_deliverable = {
        "summary": generate_executive_summary(),
        "requirements": {
            "user_stories": requirements.user_stories,
            "fulfillment_status": cross_reference(requirements, tests)
        },
        "design": architecture.components,
        "implementation": {
            "source_code": code.files,
            "test_coverage": tests.coverage_report
        },
        "validation": tests.results,
        "documentation": documentation.artifacts,
        "metadata": {
            "quality_score": calculate_overall_quality()
        }
    }
    
    validate_completeness(final_deliverable)
    return final_deliverable
```

## Example: Complete Workflow Execution

**User Request:** "Build user authentication system with email/password"

**Execution:**
```
[00:00] TechLead: Route to RequirementsAnalyst
[00:02] RequirementsAnalyst: Generated 3 user stories, 8 acceptance criteria
[00:02] TechLead: Route to SystemArchitect
[00:15] SystemArchitect: Designed 4-component architecture
[00:15] TechLead: Route to CodeDeveloper
[01:23] CodeDeveloper: Implemented 12 files, 847 LOC
[01:23] TechLead: Route to QATester + DocumentationSpecialist (parallel)
[01:45] QATester: 36/36 tests passed, 94% coverage
[01:52] DocumentationSpecialist: README + API docs complete
[01:53] TechLead: Validation passed, quality score: 92/100
[01:54] TechLead: COMPLETE - Delivering to user
```

**Final Deliverable:**
- Requirements (3 user stories, 8 acceptance criteria)
- Architecture (4-component system, API contracts)
- Source Code (12 files, 94% coverage)
- Test Results (36/36 passed, approved)
- Documentation (README + API Reference)

# Core Dependencies
pyyaml>=6.0
requests>=2.31.0

# Security Analysis Tools
bandit>=1.7.5
safety>=2.3.0

# Code Analysis
pylint>=3.0.0
mypy>=1.7.0

# Testing
pytest>=7.4.0
pytest-cov>=4.1.0

# Documentation Generation
sphinx>=7.2.0
markdown>=3.5.0

# Data Processing
pandas>=2.1.0
openpyxl>=3.1.0

# Optional: Static Analysis
semgrep>=1.45.0

# Development Tools
black>=23.12.0
isort>=5.13.0
```
