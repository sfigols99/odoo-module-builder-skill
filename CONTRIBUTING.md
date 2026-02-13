# Contributing to Odoo Module Builder Skill

Thank you for your interest in contributing! This document provides guidelines for contributing to this project.

## How to Contribute

### Reporting Issues

- Use the GitHub issue tracker to report bugs or suggest features
- Provide clear descriptions and examples
- Include relevant context (Odoo version, error messages, etc.)

### Suggesting Enhancements

- Check existing issues and pull requests first
- Clearly describe the enhancement and its benefits
- Provide examples of how it would be used

### Contributing Code

1. **Fork the repository** and create a new branch for your changes
2. **Make your changes** following the project conventions:
   - Reference files should be clear, concise, and include examples
   - Scripts should include docstrings and handle errors gracefully
   - Keep changes focused and minimal
3. **Test your changes**:
   - For reference docs: ensure accuracy and clarity
   - For scripts: test with various inputs and edge cases
4. **Commit your changes** with clear, descriptive commit messages
5. **Submit a pull request** with a description of what changed and why

## Reference Documentation Guidelines

When contributing to reference files (`references/*.md`):

- Use clear, practical examples from real Odoo usage
- Include both Odoo 16 and 17 syntax where they differ
- Organize content logically with clear headers
- Use code blocks with appropriate syntax highlighting
- Explain the "why" not just the "how"
- Keep examples minimal but complete

## Script Guidelines

When contributing to `scripts/scaffold_module.py`:

- Follow PEP 8 style guidelines
- Include docstrings for functions
- Handle edge cases and errors gracefully
- Maintain compatibility with both Odoo 16 and 17
- Test generated modules with actual Odoo installations when possible

## Documentation Standards

- Use clear, concise language
- Include practical examples
- Keep formatting consistent
- Update the main README.md if adding new features

## Code of Conduct

- Be respectful and inclusive
- Focus on constructive feedback
- Help create a welcoming environment for all contributors

## Questions?

Feel free to open an issue for questions or clarifications about contributing.
