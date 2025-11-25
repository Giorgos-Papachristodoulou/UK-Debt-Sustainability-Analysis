# Contributing to UK Debt Sustainability Analysis

First off, thank you for considering contributing to this project! 🎉

This document provides guidelines for contributing to the UK Debt Sustainability Analysis repository. Following these guidelines helps communicate that you respect the time of the developers managing and developing this open source project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Style Guidelines](#style-guidelines)
- [Commit Messages](#commit-messages)
- [Pull Request Process](#pull-request-process)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Enhancements](#suggesting-enhancements)

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to [your.email@example.com].

## Getting Started

1. Fork the repository on GitHub
2. Clone your fork locally
3. Set up the development environment (see below)
4. Create a branch for your changes
5. Make your changes
6. Run tests and ensure they pass
7. Submit a pull request

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples** (code snippets, data files)
- **Describe the behavior you observed and what you expected**
- **Include your environment details** (OS, Python version, package versions)

### 💡 Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description of the proposed enhancement**
- **Explain why this enhancement would be useful**
- **List any alternatives you've considered**

### 📖 Improving Documentation

Documentation improvements are always welcome! This includes:

- Fixing typos or unclear explanations
- Adding examples or tutorials
- Improving API documentation
- Translating documentation

### 🔧 Code Contributions

We welcome code contributions for:

- Bug fixes
- New features
- Performance improvements
- Test coverage improvements
- Code refactoring

## Development Setup

### Prerequisites

- Python 3.8+
- Git
- Virtual environment tool (venv, conda, etc.)

### Setup Steps

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/uk-debt-sustainability.git
cd uk-debt-sustainability

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install development dependencies
pip install -r requirements-dev.txt

# Install package in development mode
pip install -e .

# Run tests to verify setup
pytest tests/
```

### Development Dependencies

```bash
pip install -r requirements-dev.txt
```

This includes:
- `pytest` - Testing framework
- `pytest-cov` - Coverage reporting
- `black` - Code formatting
- `flake8` - Linting
- `mypy` - Type checking
- `pre-commit` - Git hooks

### Setting Up Pre-commit Hooks

```bash
pre-commit install
```

This will run formatting and linting checks before each commit.

## Style Guidelines

### Python Code Style

We follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) with the following specifics:

- **Line length**: 88 characters (Black default)
- **Imports**: Use `isort` for sorting
- **Docstrings**: Google style
- **Type hints**: Required for public functions

#### Example

```python
def calculate_fiscal_space(
    current_debt: float,
    interest_rate: float,
    growth_rate: float,
    reaction_params: dict[str, float]
) -> dict[str, float]:
    """Calculate fiscal space using Ghosh et al. (2013) methodology.
    
    Args:
        current_debt: Current debt-to-GDP ratio (percentage).
        interest_rate: Effective interest rate on debt.
        growth_rate: Nominal GDP growth rate.
        reaction_params: Estimated fiscal reaction function parameters.
        
    Returns:
        Dictionary containing debt_limit and fiscal_space.
        
    Raises:
        ValueError: If parameters are outside valid ranges.
        
    Example:
        >>> params = {'alpha': 7.958, 'beta1': -34.067, 'beta2': 27.382, 'beta3': -2.517}
        >>> result = calculate_fiscal_space(96.0, 0.045, 0.035, params)
        >>> print(f"Fiscal space: {result['fiscal_space']:.1f} pp")
        Fiscal space: 18.0 pp
    """
    # Implementation...
```

### Code Formatting

Format your code using Black before committing:

```bash
black src/ tests/
```

### Linting

Run flake8 to check for issues:

```bash
flake8 src/ tests/
```

### Type Checking

Run mypy for type checking:

```bash
mypy src/
```

## Commit Messages

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### Examples

```
feat(monte-carlo): add support for Student's t-distribution

Implement fat-tailed Monte Carlo simulation using Student's t-distributions
with configurable degrees of freedom for GDP, inflation, and interest rate shocks.

Closes #42
```

```
fix(bohn-test): correct Newey-West bandwidth calculation

The HAC bandwidth was incorrectly set to n^(1/3) instead of n^(1/4).
This fix aligns with Newey & West (1987) recommendations.

Fixes #38
```

```
docs(readme): add installation instructions for Windows
```

## Pull Request Process

### Before Submitting

1. **Update documentation** for any changed functionality
2. **Add tests** for new features
3. **Run the full test suite** and ensure all tests pass
4. **Update the CHANGELOG.md** with your changes
5. **Ensure your code follows** our style guidelines

### PR Checklist

- [ ] I have read the CONTRIBUTING.md document
- [ ] My code follows the project's style guidelines
- [ ] I have added tests that prove my fix/feature works
- [ ] All new and existing tests pass
- [ ] I have updated the documentation accordingly
- [ ] I have added an entry to CHANGELOG.md

### Review Process

1. Submit your PR with a clear description
2. Maintainers will review your code
3. Address any requested changes
4. Once approved, your PR will be merged

### PR Title Format

Follow the same convention as commit messages:

```
feat(component): brief description
```

## Reporting Bugs

### Bug Report Template

When reporting bugs, please use the issue template and include:

```markdown
## Description
A clear description of the bug.

## Steps to Reproduce
1. Step one
2. Step two
3. ...

## Expected Behavior
What you expected to happen.

## Actual Behavior
What actually happened.

## Environment
- OS: [e.g., Windows 10, macOS 12, Ubuntu 22.04]
- Python version: [e.g., 3.10.4]
- Package version: [e.g., 1.0.0]

## Additional Context
Any other relevant information.
```

## Suggesting Enhancements

### Feature Request Template

```markdown
## Summary
Brief description of the feature.

## Motivation
Why is this feature needed? What problem does it solve?

## Proposed Solution
How do you envision this feature working?

## Alternatives Considered
What alternatives have you considered?

## Additional Context
Any other relevant information, mockups, or examples.
```

## Questions?

If you have questions about contributing, feel free to:

- Open a [Discussion](https://github.com/yourusername/uk-debt-sustainability/discussions)
- Email the maintainers at [your.email@example.com]

Thank you for contributing! 🙏
