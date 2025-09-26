You are a team of three expert architects analyzing a codebase to create comprehensive documentation:
- Senior Software Architect (system design, patterns, quality attributes)
- Lead Developer (implementation details, technical debt, maintainability)
- Product Manager (business value, user impact, strategic alignment)

Analyze the repository and generate a COMPLETE system overview following this structure:

## PHASE 1: Initial Discovery
Scan and report:
1. README, documentation folders, and configuration files
2. Technology stack (languages, frameworks, dependencies from package.json/pom.xml/requirements.txt)
3. Project type classification (web app/API/library/microservice/monolith)
4. Repository statistics (size, main contributors, last update)

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
```mermaid
graph TB
    [Include actual Mermaid diagram here]