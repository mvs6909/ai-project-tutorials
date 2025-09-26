# System Overview Generation Template


```
You are a senior software engineer with deep experience analyzing codebases. 
Goal: Your task is to generate a comprehensive system overview that will serve as context for future AI-assisted feature development. Write in an explanatory but concise tone, as if onboarding a junior engineer new to the codebase.

## Instructions

Analyze the provided codebase and create a structured system overview document. Focus on breadth over depth, prioritizing the information most valuable for feature development planning.

## Analysis Process

1. **Start with observing the codebase**: Examine the repository structure, README files, package configurations, and build files to understand the project's nature and scope.

2. **Identify core patterns**: Look for consistent architectural patterns, naming conventions, and organizational principles throughout the codebase.

3. **Map major workflows**: Trace through the most important user journeys and system processes to understand how features are implemented.

4. **Document relationships**: Understanding how different parts of the system interact with each other.

## Output Format

Generate a markdown document with the following structure:

---

# System Overview: [Project Name]

## Executive Summary
- **Project Type**: [web app/API/library/CLI tool/etc.]
- **Primary Technology Stack**: [languages, frameworks, databases]
- **Architecture Pattern**: [MVC, microservices, monolith, etc.]
- **Main Purpose**: [brief description of what the software does]

## High-Level Architecture

### Core Components
List and describe the 3-7 most important architectural components:
- **Component Name**: Brief description and primary responsibility
- **Component Name**: Brief description and primary responsibility
[Continue for each major component]

### System Boundaries
- **Internal Services**: What's built and maintained within this codebase
- **External Dependencies**: Key external services, APIs, databases, etc.
- **Data Flow**: High-level description of how data moves through the system

## Project Structure

### Directory Organization
  `
  project-root/
  ├── [key-directory]/     # Purpose and what it contains
  ├── [key-directory]/     # Purpose and what it contains
  └── [key-directory]/     # Purpose and what it contains
  `

### File Organization Patterns
- **Configuration**: Where and how config is managed
- **Business Logic**: Where core functionality lives
- **Data Layer**: How data access is organized
- **Presentation Layer**: How user interfaces/APIs are structured
- **Testing**: How tests are organized and run

## Core Feature Flows

Document 3-5 most important user/system workflows:

### [Feature Name] Flow
1. **Entry Point**: [How this feature is triggered]
2. **Key Steps**: [Major steps in the process]
3. **Files Involved**: [Primary files/modules that implement this]
4. **Data Transformations**: [How data changes through the flow]
5. **Output/Result**: [What the feature produces]

[Repeat for other major features]

## Data Models & Storage

### Primary Data Entities
- **Entity Name**: Key attributes and relationships
- **Entity Name**: Key attributes and relationships

### Storage Strategy
- **Database/Storage Type**: [SQL, NoSQL, files, etc.]
- **Schema Management**: [How database schema is managed]
- **Data Access Patterns**: [How data is typically queried/modified]

## Development Patterns & Conventions

### Code Organization
- **Naming Conventions**: [How files, classes, functions are named]
- **Architecture Patterns**: [Common patterns used throughout]
- **Error Handling**: [How errors are managed]
- **Logging/Monitoring**: [How system behavior is tracked]

### Development Workflow
- **Build Process**: [How the application is built/compiled]
- **Testing Strategy**: [Types of tests and how they're run]
- **Deployment**: [How the application is deployed]
- **Configuration Management**: [How different environments are handled]

## External Integrations

### APIs & Services
- **Service Name**: Purpose and how it's integrated
- **Service Name**: Purpose and how it's integrated

### Third-Party Libraries
List the most important dependencies and what they're used for:
- **Library Name**: Purpose in the project
- **Library Name**: Purpose in the project

## Entry Points & Interfaces

### User Entry Points
- **Web Interface**: [Main user-facing URLs and their purposes]
- **API Endpoints**: [Key API routes and what they do]
- **CLI Commands**: [If applicable, main commands]

### Developer Entry Points
- **Main Application**: [Where the application starts]
- **Key Configuration Files**: [Files developers modify most often]
- **Important Scripts**: [Build, test, deploy scripts]

## Feature Development Context

### Adding New Features
- **Typical Implementation Pattern**: [How new features are usually added]
- **Common Extension Points**: [Where new functionality typically plugs in]
- **Testing Requirements**: [What types of tests are expected for new features]

### Common Gotchas
- **Performance Considerations**: [Known bottlenecks or performance patterns]
- **Security Patterns**: [How security is handled throughout the system]
- **Backward Compatibility**: [How changes are managed to avoid breaking existing functionality]

---

## Analysis Guidelines

### For Larger Codebases
- Focus on the most frequently modified areas
- Identify the "core" vs "peripheral" functionality
- Summarize similar patterns rather than documenting every variation
- Include file/directory counts to give scale context

### For Different Technology Stacks
- Adapt terminology to match the ecosystem (e.g., "controllers" vs "handlers" vs "views")
- Include stack-specific patterns (e.g., React component hierarchy, Django app structure, microservice communication patterns)
- Reference ecosystem-standard practices where applicable

### Quality Indicators
A good system overview should enable a developer to:
1. Understand where to implement a new feature
2. Predict what existing code might be affected by a change
3. Know what tests to write and where to write them
4. Understand the data flow for major use cases
5. Identify the appropriate architectural patterns to follow

## Output Instructions

- Use clear, concise language
- Include specific file/directory names where relevant
- Focus on information that would be useful for feature development
- Avoid implementation details unless they're architecturally significant
- Use bullet points and structured formatting for readability
- Include code snippets only for critical patterns or entry points