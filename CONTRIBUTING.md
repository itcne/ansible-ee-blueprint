# Contributing to Ansible Execution Environment Blueprint

We love your input! We want to make contributing to this Ansible Execution Environment (EE) blueprint as easy and transparent as possible, whether it's:

- Reporting a bug
- Discussing the current state of the configuration
- Submitting a fix
- Proposing new features or dependencies
- Becoming a maintainer

## We Develop with Github
We use github to host code, to track issues and feature requests, as well as accept pull requests.

## We Use [Github Flow](https://guides.github.com/introduction/flow/index.html), So All Code Changes Happen Through Pull Requests
Pull requests are the best way to propose changes to the codebase (we use [Github Flow](https://guides.github.com/introduction/flow/index.html)). We actively welcome your pull requests:

1. Fork the repo and create your branch from `main`.
2. If you've added code that should be tested, add tests.
3. If you've changed APIs, update the documentation.
4. Ensure the test suite passes.
5. Make sure your code lints.
6. **Use conventional commit messages** (see below).
7. Issue that pull request!

## Commit Message Convention

**REQUIRED:** This project uses [Conventional Commits](https://www.conventionalcommits.org/) for automated changelog generation and semantic versioning.

All commit messages must follow this format:
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Commit Types

- `feat:` - New features or dependencies
- `fix:` - Bug fixes
- `docs:` - Documentation changes
- `deps:` - Dependency updates (Python packages, Ansible collections, system packages)
- `ci:` - CI/CD pipeline changes
- `refactor:` - Code refactoring without feature changes
- `chore:` - Maintenance tasks

### Examples

```bash
feat: add community.docker collection for container management
fix: resolve ansible-core version conflict in requirements.txt
docs: update README with new collection examples
deps: bump ansible-core to 2.16.0
ci: add security scanning with Trivy
```

### Breaking Changes

For breaking changes, add `!` after the type:
```bash
feat!: upgrade to ansible-core 3.0 (breaking change)
```

## Any contributions you make will be under the MIT Software License
In short, when you submit code changes, your submissions are understood to be under the same [MIT License](https://opensource.org/licenses/MIT) that covers the project. Feel free to contact the maintainers if that's a concern.

## Report bugs using Github's issues

We use GitHub issues to track public bugs. Report a bug by [opening a new issue](../../issues); it's that easy!

**Great Bug Reports** tend to have:

- A quick summary and/or background
- Steps to reproduce
  - Be specific!
  - Include your `execution-environment.yml` if relevant
  - Include build commands you ran
  - What you expected would happen
- What actually happens
- Notes (possibly including why you think this might be happening, or stuff you tried that didn't work)

People *love* thorough bug reports. I'm not even kidding.

## Use a Consistent Style

- Use 2 spaces for indentation in YAML files
- Follow Ansible best practices for `requirements.yml`
- Pin major versions in `requirements.txt`: `ansible-core>=2.15.0,<2.16.0`
- Use platform selectors in `bindep.txt`: `[platform:rpm platform:deb]`
- Test your changes with `ansible-builder build -t test-ee .`

## License
By contributing, you agree that your contributions will be licensed under its MIT License.
[MIT License](https://opensource.org/licenses/MIT). See the [LICENSE](LICENSE) file for details.