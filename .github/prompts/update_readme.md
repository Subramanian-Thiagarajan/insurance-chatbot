# GitHub Copilot Documentation Generation Instructions

## Primary Objective

Generate comprehensive, maintainable documentation for project components with automated change tracking and high-level architectural overview maintenance.

## Context and Scope

This prompt is designed for multi-component projects containing backend, frontend, and other modular components. The goal is to maintain living documentation that evolves with the codebase while preserving historical context.

## Documentation Generation Guidelines

### 1. High-Level Overview Section

When updating documentation, always include or refresh the following sections:

#### Architecture Overview

- **System Architecture**: Describe the overall system design, component relationships, and data flow
- **Technology Stack**: List primary technologies, frameworks, and tools used in each component
- **Component Interaction**: Explain how different parts of the system communicate (APIs, messaging, shared databases)
- **Deployment Architecture**: Describe how components are deployed and their runtime environment

#### Project Structure

- **Repository Organization**: Explain the folder structure and purpose of each major directory
- **Component Boundaries**: Define what each component is responsible for and its interfaces
- **Shared Resources**: Document any shared libraries, configurations, or utilities

### 2. Change History Maintenance

Implement a structured change tracking system:

#### Change Log Format

For each significant update, add an entry with:

- **Date**: ISO format (YYYY-MM-DD)
- **Version/Commit**: Reference point for the change
- **Component(s) Affected**: Which parts of the system were modified
- **Change Type**: [FEATURE|BUGFIX|REFACTOR|BREAKING|SECURITY|PERFORMANCE]
- **Description**: Clear, non-technical summary of what changed
- **Technical Details**: Implementation specifics for developers
- **Impact Assessment**: How this change affects other components or users

#### Change History Template

```markdown
## Change History

### [Date] - [Version] - [Change Type]

**Components Affected**: [List components]
**Summary**: [Brief description]
**Details**:

- [Specific change 1]
- [Specific change 2]
  **Breaking Changes**: [If any]
  **Migration Notes**: [If required]

---
```

### 3. Documentation Standards

#### Writing Style Guidelines

- **Audience Awareness**: Write for both technical team members and stakeholders
- **Clarity Over Brevity**: Prioritize understanding over conciseness
- **Consistent Terminology**: Use the same terms throughout documentation
- **Active Voice**: Use active voice for clarity and directness

#### Structure Requirements

- **Executive Summary**: 2-3 sentence overview at the top
- **Table of Contents**: For documents longer than 500 words
- **Visual Aids**: Include diagrams, flowcharts, or architecture diagrams where helpful
- **Cross-References**: Link to related documentation, code, or external resources

### 4. Automated Content Generation Rules

#### Code Analysis Integration

When analyzing code changes:

- **Scan for API Changes**: Identify new endpoints, modified signatures, or deprecated functions
- **Dependency Updates**: Track new dependencies, version changes, or removals
- **Configuration Changes**: Document new environment variables, config files, or settings
- **Database Schema Changes**: Capture migrations, new tables, or structural modifications

#### Documentation Synchronization

- **Consistency Checks**: Ensure documentation matches current codebase state
- **Outdated Content Detection**: Flag sections that may be obsolete based on code changes
- **Cross-Component Impact**: Identify when changes in one component affect others

### 5. Specific Instructions for Copilot

#### When Updating Documentation:

1. **Analyze Recent Commits**: Review the last 10-20 commits for significant changes
2. **Identify Documentation Gaps**: Look for new features, components, or processes not yet documented
3. **Update Architecture Diagrams**: Modify or suggest updates to visual representations
4. **Refresh Getting Started Guides**: Ensure setup instructions remain current
5. **Validate External Links**: Check that referenced resources are still accessible

#### Content Generation Priorities:

1. **Security Implications**: Always document security-related changes prominently
2. **Performance Impact**: Highlight changes that affect system performance
3. **User-Facing Changes**: Emphasize modifications that affect end-user experience
4. **Developer Experience**: Document changes that affect development workflow

#### Quality Assurance Checks:

- **Grammar and Spelling**: Ensure professional writing quality
- **Technical Accuracy**: Verify all technical details are correct
- **Completeness**: Check that all necessary sections are included
- **Readability**: Ensure content is accessible to intended audience

### 6. Template Structure for Generated Documentation

```markdown
# [Component Name] Documentation

## Executive Summary

[2-3 sentences describing the component's purpose and role]

## Architecture Overview

[High-level description of component architecture]

## Technology Stack

[List of technologies, versions, and rationale]

## Getting Started

[Setup and development instructions]

## API Documentation

[If applicable - endpoints, schemas, examples]

## Configuration

[Environment variables, config files, deployment settings]

## Dependencies

[Internal and external dependencies with versions]

## Change History

[Structured change log as defined above]

## Troubleshooting

[Common issues and solutions]

## Contributing

[Development guidelines and processes]
```

## Implementation Notes

### File Naming Convention

Use descriptive, consistent naming: `[component-name]-documentation.md` or `README-[component-name].md`

### Maintenance Schedule

- **Weekly**: Update change history for recent commits
- **Sprint/Release**: Comprehensive documentation review
- **Major Releases**: Full architecture and overview refresh

### Integration Points

- **CI/CD Pipeline**: Trigger documentation updates on significant merges
- **Pull Request Templates**: Include documentation update checklist
- **Code Review Process**: Verify documentation changes accompany code changes

## Success Metrics

- Documentation covers all major system components
- Change history provides clear project evolution narrative
- New team members can understand system architecture from documentation alone
- Documentation remains current with less than 1-week lag from code changes
