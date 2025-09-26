# System Overview Generation Prompt Template

## 🏗️ Master System Overview Prompt Template

### Instructions for AI Model

```
You are a team of three expert architects analyzing a codebase to create comprehensive documentation:
- Senior Software Architect (system design, patterns, quality attributes)
- Lead Developer (implementation details, technical debt, maintainability)
- Product Manager (business value, user impact, strategic alignment)

Analyze the repository and generate a COMPLETE system overview following this structure:

---

## PHASE 1: Initial Discovery

Scan and report:
1. README, documentation folders, and configuration files
2. Technology stack (languages, frameworks, dependencies from package.json/pom.xml/requirements.txt)
3. Project type classification (web app/API/library/microservice/monolith)
4. Repository statistics (size, main contributors, last update)

---

## PHASE 2: Architectural Analysis (arc42-based)

### 1. Introduction & Goals
- **Business Context**: What problem does this system solve?
- **Essential Features**: Top 3-5 capabilities
- **Target Users**: Primary and secondary stakeholders
- **Success Metrics**: How is this system's success measured?

### 2. Constraints
- **Technical Constraints**: Required technologies, platforms, standards
- **Organizational Constraints**: Team size, skills, timeline
- **Regulatory/Compliance**: Security, privacy, legal requirements

### 3. System Context (C4 Level 1)
Create a context diagram showing:
- External users/personas
- External systems/integrations  
- Data flows between system and external entities

`mermaid graph TB
    User[End Users] -->|HTTP Requests| System[Your System]
    System -->|API Calls| ExtAPI[External API]
    System -->|Read/Write| DB[(Database)]
    Admin[Administrators] -->|Configure| System
`

### 4. Solution Strategy
- **Architecture Style**: (e.g., layered, microservices, event-driven)
- **Key Design Decisions**: Top 3 architectural choices and WHY
- **Technology Decisions**: Core tech choices with rationale

### 5. Building Blocks (C4 Level 2 - Containers)

Table format:

| Container | Purpose | Technology | Key Files/Folders | Dependencies |
|-----------|---------|------------|-------------------|--------------|
| [Name]    | [Role]  | [Stack]    | [Locations]       | [Libraries]  |
| Frontend  | UI      | React      | /src/components   | React, Redux |
| API       | Backend | Node.js    | /api              | Express      |
| Database  | Storage | PostgreSQL | /migrations       | pg           |

### 6. Runtime Behavior

Describe ONE critical user journey:
1. Trigger/Input
2. Processing steps (with component interactions)
3. Output/Result
4. Error handling approach

`mermaid
sequenceDiagram
    participant U as User
    participant F as Frontend
    participant A as API
    participant D as Database
    
    U->>F: User Action
    F->>A: API Request
    A->>D: Query Data
    D-->>A: Return Results
    A-->>F: JSON Response
    F-->>U: Update UI
`

### 7. Deployment View
- **Environments**: Development, staging, production setup
- **Infrastructure Requirements**: Servers, databases, external services
- **Deployment Process**: Build and deployment pipeline overview

### 8. Cross-Cutting Concepts

Pick the 3 most important:
- Security approach (authentication, authorization, data protection)
- Error handling and logging strategy
- Performance optimization techniques
- Configuration management
- Testing strategy

### 9. Architecture Decisions (ADRs)

Top 3 significant decisions observable in code:

| Decision | Context | Choice | Consequences |
|----------|---------|--------|--------------|
| Database | Need flexible schema | NoSQL (MongoDB) | Easier iterations, complex queries harder |
| Auth | Security requirement | JWT tokens | Stateless, but token management needed |
| API Style | Multiple clients | REST | Standard, but multiple calls needed |

### 10. Quality Scenarios

| Quality Attribute | Scenario | Implementation |
|------------------|----------|----------------|
| Performance | Handle 1000 concurrent users | Caching, load balancing |
| Security | Prevent unauthorized access | JWT + role-based access |
| Maintainability | Add new features easily | Modular architecture |

### 11. Risks & Technical Debt
- **High Priority Risks**: Top 3 identified risks
- **Technical Debt**: Most significant areas needing refactoring
- **Missing Capabilities**: Important features not yet implemented

---

## PHASE 3: Developer Guide

### Quick Start Guide

```bash
# Prerequisites
- Node.js 18+
- PostgreSQL 14+
- Docker (optional)

# Installation steps
1. git clone <repository>
2. npm install
3. cp .env.example .env
4. npm run db:migrate
5. npm run dev

# Verification
curl http://localhost:3000/health
```

### Code Organization

```
project-root/
├── src/               # Application source code
│   ├── components/    # UI components
│   ├── services/      # Business logic
│   ├── models/        # Data models
│   └── utils/         # Helper functions
├── tests/             # Test suites
│   ├── unit/          # Unit tests
│   └── integration/   # Integration tests
├── docs/              # Documentation
├── config/            # Configuration files
└── scripts/           # Build and deployment scripts
```

### Key Entry Points
1. **Main Application**: `src/index.js` - Application bootstrap
2. **API Routes**: `src/routes/index.js` - API endpoint definitions
3. **Configuration**: `config/app.js` - Application settings
4. **Database Models**: `src/models/` - Data structure definitions

### Development Workflow
- **Local Development**: `npm run dev` - Starts development server with hot reload
- **Testing**: `npm test` - Runs test suite
- **Linting**: `npm run lint` - Checks code style
- **Building**: `npm run build` - Creates production build

---

## PHASE 4: Learning Path

### For New Developers

1. **Start Here**: `README.md` and `docs/architecture.md`
2. **Then Explore**: `src/routes/` to understand API structure
3. **Deep Dive**: `src/services/` for business logic
4. **Advanced**: `src/middleware/` for cross-cutting concerns

### Key Concepts to Understand
- **Domain Concept 1**: User authentication flow
- **Domain Concept 2**: Data validation pipeline
- **Pattern/Convention**: Repository pattern for data access
- **Architecture Pattern**: MVC separation

### Useful Resources
- **Internal Documentation**: `/docs` folder
- **API Documentation**: `/docs/api/swagger.yaml`
- **External Resources**:
  - [Framework Documentation]
  - [Design Pattern References]
  - [Company Standards Guide]

---

## PHASE 5: Analysis Summary

### Strengths 💪
1. Clear separation of concerns
2. Comprehensive test coverage
3. Well-documented API endpoints

### Improvement Opportunities 🔧
1. Add caching layer for performance
2. Implement circuit breakers for external services
3. Enhance monitoring and observability

### Complexity Assessment
- **Overall Complexity**: Low/Medium/High
- **Onboarding Difficulty**: Easy/Moderate/Challenging
- **Maintenance Burden**: Low/Medium/High
- **Technical Debt Score**: Low/Medium/High

---

## Output Requirements

1. **Be SPECIFIC** - Use actual file names, folder paths, and code examples
2. **Be PRACTICAL** - Focus on what developers need to know
3. **Be VISUAL** - Include at least 2 Mermaid diagrams
4. **Be HONEST** - Acknowledge uncertainties and make educated guesses when needed
5. **Be CONCISE** - Each section should be comprehensive but scannable

**Note**: If any section cannot be determined from the codebase, state: 
> ⚠️ Not evident from codebase - requires clarification

---

## 💡 Usage Tips for Maximum Effectiveness

### 1. Pre-Processing Enhancement

Before using this prompt, provide additional context:

```markdown
Additional Context:
- Repository URL: [if available]
- Business Domain: [e.g., e-commerce, healthcare, fintech]
- Team Size: [helps understand organizational constraints]
- Documentation Priority: [what stakeholders need most]
- Special Requirements: [any specific focus areas]
```

### 2. Iterative Refinement Approach

After initial generation, follow up with:

```markdown
Based on the initial overview, please:
1. Expand on [specific section needing more detail]
2. Create a detailed component diagram for [specific module]
3. Document the data flow for [specific feature]
4. Explain the rationale behind [specific architectural decision]
5. Add more detail about [specific technology choice]
```

### 3. Stakeholder-Specific Views

Generate targeted documentation:

```markdown
Transform the system overview into a [stakeholder] perspective:
- For executives: Focus on business value, ROI, and strategic alignment
- For DevOps: Emphasize deployment, monitoring, and operational concerns
- For QA: Highlight testing strategies and quality gates
- For new developers: Create a step-by-step onboarding guide
- For security team: Detail security measures and compliance
```

### 4. Quality Validation Checklist

After generation, verify:
- ✅ All major components are identified
- ✅ Architectural decisions include rationale
- ✅ Diagrams accurately represent system structure
- ✅ Entry points and key files are correct
- ✅ Technology stack is completely documented
- ✅ Dependencies are properly listed
- ✅ Build and deployment processes are clear
- ✅ Testing approach is documented
- ✅ Performance considerations are addressed
- ✅ Security measures are outlined

### 5. Customization Examples

#### For Microservices Architecture
Add sections for:
- Service inventory and responsibilities
- Inter-service communication patterns
- Service discovery mechanism
- Distributed tracing setup

#### For Data-Heavy Applications
Emphasize:
- Data flow diagrams
- Schema documentation
- ETL processes
- Data governance policies

#### For Legacy System Modernization
Include:
- Current state vs target state
- Migration strategy
- Backward compatibility approach
- Deprecation timeline

### 6. Common Pitfalls to Avoid

- ❌ Don't skip the business context
- ❌ Don't focus only on code structure
- ❌ Don't ignore non-functional requirements
- ❌ Don't forget about deployment and operations
- ❌ Don't assume technical knowledge level

### 7. Documentation Maintenance

Establish a process for keeping documentation current:
1. **Trigger Updates**: Major releases, architecture changes
2. **Review Cycle**: Quarterly documentation review
3. **Ownership**: Assign documentation champions
4. **Automation**: Use CI/CD to flag outdated docs

---

## Template Version Information

- **Version**: 1.0.0
- **Last Updated**: 2024
- **Based On**: arc42, C4 Model, IEEE 42010
- **Optimized For**: AI-assisted documentation generation
- **License**: Open source - feel free to customize

---

## Feedback and Contributions

This template is designed to evolve. Consider:
- What sections were most/least useful?
- What additional information would help?
- How can the structure be improved?
- What worked well for your specific use case?

---

*This template synthesizes best practices from arc42, C4 model, and modern documentation standards while remaining practical and actionable. It's designed to work with any codebase and can be customized based on specific organizational needs or domain requirements.*