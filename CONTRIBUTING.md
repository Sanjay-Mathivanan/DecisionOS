# Contributing to DecisionOS Civic

## Purpose
This document provides guidelines for contributors looking to extend the DecisionOS Civic platform.

## Content
### Development Workflow
1. **Fork the Repository**: Clone the project codebase.
2. **Implement Modules**: Create domain-specific plugins inside the `plugins/` directory following the Unified Input Schema.
3. **Write Unit Tests**: Validate optimization models using synthetic datasets before committing.
4. **Submit PRs**: Ensure all relative documentation links are updated.

### Code Style Guidelines
- Backend logic must follow PEP8 formatting standards.
- Database changes must be accompanied by updated PostgreSQL schema documentation in the `docs/10-database/` folder.

## Related Documents
- [Project Overview](docs/01-overview/01-project-overview.md)
- [Development Roadmap](docs/14-implementation/02-development-roadmap.md)
