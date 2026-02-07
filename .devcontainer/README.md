# Photon Devcontainer Configuration

This comprehensive devcontainer configuration provides a complete development environment for Photon, the incredibly fast OSINT web crawler.

**Quick Stats:**
- 33 VS Code extensions
- 9+ Python development tools  
- 5 Devcontainer features
- 6 Debug configurations
- 13 Pre-configured tasks

## Features

### 🐍 Python Development
- Python 3 with latest packages
- Black formatter for code formatting
- Flake8, Pylint for linting
- Bandit for security scanning
- PyTest for testing with coverage support
- IPython and Jupyter for interactive development

### 🔧 Development Tools
- **Git**: Latest version with GitHub CLI
- **Docker**: Docker-in-Docker support for building and testing containers
- **Node.js**: Latest LTS version for any web-based tooling
- **Zsh with Oh My Zsh**: Enhanced shell experience

### 📝 VS Code Extensions

#### Python Development
- Python extension pack with IntelliSense
- Pylance for advanced Python language support
- Black, Flake8, and Pylint integrations
- Python debugger
- Test explorer for PyTest

#### Code Quality
- Security scanning tools
- Code coverage visualization
- TODO tree for tracking tasks
- Better comments for enhanced code documentation

#### Git & Version Control
- GitLens for advanced Git features
- Git Graph for visual commit history
- Git History explorer

#### Productivity
- Path IntelliSense
- REST Client for API testing
- Regex helper for pattern testing
- Code spell checker
- IntelliCode for AI-assisted development

### 🚀 Quick Start

1. **Open in GitHub Codespaces**: Click the "Code" button and select "Open with Codespaces"
2. **Wait for setup**: The container will automatically install all dependencies
3. **Start developing**: All tools are pre-configured and ready to use

### 📋 Common Commands

```bash
# Run Photon
python photon.py --help
python photon.py -u example.com

# Code quality
black .                    # Format all Python files
flake8 .                   # Lint all Python files
pylint core plugins        # Advanced linting
bandit -r .                # Security scanning

# Testing
pytest                     # Run all tests
pytest --cov               # Run tests with coverage

# Docker
docker build -t photon .   # Build Docker image
docker run -it photon      # Run in container
```

### 🛠️ Customization

The devcontainer includes:
- **Automatic formatting on save**
- **Python import organization**
- **Git auto-fetch**
- **Persistent VS Code server**
- **Port forwarding** for web development (8000, 8080, 5000, 3000)

### 🔐 Security

- Container runs as non-root user (`vscode`)
- Bandit security scanner pre-installed
- Safety for dependency vulnerability checking
- Git safe directory configured

### 📦 Pre-installed Python Packages

Core dependencies from `requirements.txt` plus:
- black - Code formatter
- pylint - Linter
- flake8 - Style checker
- pytest - Testing framework
- pytest-cov - Coverage plugin
- bandit - Security linter
- safety - Dependency checker
- ipython - Enhanced Python shell
- jupyter - Notebook support

### 🌐 Network Tools

The container has full network access for web crawling, including:
- HTTP/HTTPS requests
- SOCKS proxy support
- DNS lookups
- Archive.org access for wayback plugin

### 💡 Tips

1. **Use the integrated terminal** (Ctrl+\`) for running Photon commands
2. **Leverage GitLens** to see code authorship inline
3. **Use TODO Tree** to track tasks across the codebase
4. **REST Client extension** can test web endpoints before crawling
5. **Regex helper** aids in creating custom pattern matching

### 📚 Resources

- [Photon Wiki](https://github.com/s0md3v/Photon/wiki)
- [Usage Guide](https://github.com/s0md3v/Photon/wiki/Usage)
- [Devcontainer Documentation](https://code.visualstudio.com/docs/devcontainers/containers)
- [GitHub Codespaces](https://github.com/features/codespaces)

## Support

For issues with the devcontainer configuration, please open an issue in the repository.
For Photon-specific questions, refer to the [main documentation](https://github.com/s0md3v/Photon/wiki).
