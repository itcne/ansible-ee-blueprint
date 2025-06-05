# Ansible Execution Environment Blueprint

A simple template for building custom Ansible Execution Environments with `ansible-builder`.

## 📁 Files

| File | Purpose |
|------|---------|
| `execution-environment.yml` | Main ansible-builder configuration (UBI9 Python 3.12) |
| `requirements.txt` | Python dependencies (pip packages) |
| `requirements.yml` | Ansible Galaxy collections |
| `bindep.txt` | System packages (RPM/DEB) |

## 🚀 Quick Start

```bash
# Install tools
pip install ansible-builder ansible-navigator

# Build the execution environment
ansible-builder build -t my-ee:latest .

# Test it works
ansible-navigator exec --execution-environment-image my-ee:latest -- ansible --version
```

## 🧪 Testing

```bash
# Basic test - check collections
ansible-navigator exec --execution-environment-image my-ee:latest -- ansible-galaxy collection list

# Test with playbook
ansible-navigator run playbook.yml --execution-environment-image my-ee:latest

# Interactive mode to explore the environment
ansible-navigator exec --execution-environment-image my-ee:latest --mode interactive
```

## 🔧 CI/CD

**3 Automated Workflows:**

### 📦 **Build & Publish** (`main`/`develop` push, tags, manual)

1. **Build**: Uses `ansible-builder` with UBI9 Python 3.12 minimal base
2. **Test**: Validates Ansible functionality and collections  
3. **Scan**: Security vulnerability scanning with Trivy
4. **Publish**: Pushes to GitHub Container Registry (GHCR)
5. **Artifacts**: Generates SBOM for supply chain security

### ✅ **PR Validation** (Pull requests)

- Builds and tests without publishing
- Security scanning for early feedback
- Validates configuration files

### 🚀 **Release** (Git tags)

- Semantic versioning with conventional commits
- Automatic changelog generation
- Tagged releases to GHCR (`latest` + version tags)

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

## 📄 License

MIT License - see [LICENSE](LICENSE) for details.