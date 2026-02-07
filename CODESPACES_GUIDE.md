# 🚀 GitHub Codespaces Setup for Photon

This repository now includes a **comprehensive GitHub Codespaces** configuration that provides a complete, production-ready development environment for the Photon OSINT web crawler.

## 🌟 What's Included

### Development Container Features

The devcontainer includes the following pre-installed tools and features:

#### Core Tools
- **Python 3** - Latest Python environment
- **Git** - Latest version with enhanced features
- **GitHub CLI** - Command-line interface for GitHub
- **Docker-in-Docker** - Build and run containers within the codespace
- **Node.js LTS** - For any web-based tooling needs
- **Zsh with Oh-My-Zsh** - Enhanced shell with beautiful themes and plugins

#### Python Development Tools
- **black** - Automatic code formatter
- **flake8** - Style guide enforcement
- **pylint** - Advanced code analysis
- **bandit** - Security vulnerability scanner
- **safety** - Dependency vulnerability checker
- **pytest** - Testing framework
- **pytest-cov** - Code coverage reporting
- **ipython** - Enhanced interactive Python shell
- **jupyter** - Notebook support for experimentation

### 40+ VS Code Extensions

The configuration includes 33 carefully selected extensions for:

#### Python Development
- Python language support with IntelliSense
- Pylance for advanced language features
- Black formatter integration
- Flake8 and Pylint linters
- Debugger support
- Test explorer

#### Code Quality & Security
- Security scanning tools
- Code coverage visualization
- TODO tree for task tracking
- Better comments for enhanced documentation
- Spell checker

#### Git & Version Control
- **GitLens** - Supercharged Git capabilities
- Git Graph - Visual commit history
- Git History explorer
- Pull Request support

#### Productivity
- IntelliCode - AI-assisted development
- Path IntelliSense
- REST Client - Test APIs directly in VS Code
- Regex helper - Perfect for web crawling patterns
- Docker extension
- Markdown support

### Pre-configured Settings

#### Editor
- Auto-save after 1 second
- Format on save (Black formatter)
- Auto-organize imports
- Line rulers at 79 and 120 characters
- Bracket pair colorization
- Word wrap enabled

#### Python
- Automatic linting with Flake8 and Pylint
- Security scanning with Bandit
- PyTest integration
- Type checking enabled
- Auto-import completions

#### Git
- Auto-fetch enabled
- Smart commit enabled
- GitLens code lens

## 🎯 Quick Start

### Option 1: Open in Browser
1. Navigate to the [Photon repository](https://github.com/calebmills99/Photon)
2. Click the green **Code** button
3. Select **Codespaces** tab
4. Click **Create codespace on [branch]**
5. Wait for the container to build (first time takes 3-5 minutes)
6. Start developing!

### Option 2: Open in VS Code Desktop
1. Install [VS Code](https://code.visualstudio.com/)
2. Install the [GitHub Codespaces extension](https://marketplace.visualstudio.com/items?itemName=GitHub.codespaces)
3. Open Command Palette (Ctrl+Shift+P or Cmd+Shift+P)
4. Run "Codespaces: Create New Codespace"
5. Select this repository

## 📋 Common Tasks

### Running Photon

```bash
# Show help
python photon.py --help

# Basic crawl
python photon.py -u example.com

# Crawl with depth limit and thread count
python photon.py -u example.com -l 2 -t 10

# Use wayback machine
python photon.py -u example.com --wayback

# Use DNS dumper
python photon.py -u example.com --dns
```

### Code Quality

```bash
# Format code
black .

# Lint with flake8
flake8 . --max-line-length=120

# Advanced linting
pylint core plugins photon.py

# Security scan
bandit -r . -f screen

# Check for vulnerable dependencies
safety check
```

### Testing

```bash
# Run tests
pytest -v

# Run with coverage
pytest --cov=. --cov-report=html --cov-report=term

# View coverage report
# Open htmlcov/index.html in browser
```

### Docker

```bash
# Build Docker image
docker build -t photon:dev .

# Run in container
docker run -it --rm photon:dev -u example.com
```

## 🐛 Debugging

The configuration includes several debug configurations:

1. **Photon: Debug Current Site** - Debug with example.com
2. **Photon: Debug with Wayback** - Debug wayback plugin
3. **Photon: Debug with DNS Dumper** - Debug DNS plugin
4. **Python: Current File** - Debug any Python file

Access debugger: Press **F5** or go to Run and Debug panel (Ctrl+Shift+D)

## ⚡ VS Code Tasks

Pre-configured tasks (Ctrl+Shift+P → "Tasks: Run Task"):

- **Photon: Run Example** - Quick test run
- **Format Code (Black)** - Format entire codebase
- **Lint (Flake8/Pylint)** - Check code quality
- **Security Scan (Bandit)** - Find security issues
- **Run Tests** - Execute test suite
- **Build Docker Image** - Build container
- **Clean Python Cache** - Remove __pycache__ and .pyc files

## 📦 Code Snippets

Type these prefixes and press Tab:

- `photon-plugin` - Create new Photon plugin template
- `pymain` - Python main guard
- `pydoc` - Python docstring
- `try` - Try-except block
- `regex` - Regular expression pattern
- `requests` - HTTP request with error handling

## 🔧 Customization

### Add Your Own Extensions

Edit `.devcontainer/devcontainer.json` and add to the `extensions` array.

### Modify Python Packages

Add packages to `postCreateCommand` in `.devcontainer/devcontainer.json`.

### Change Settings

Edit `.vscode/settings.json` for workspace settings or modify the `settings` section in `devcontainer.json` for container-wide settings.

## 🌐 Port Forwarding

The following ports are automatically forwarded:
- **8000** - Web Server (with auto-forward notifications)
- **8080** - Alternative web port
- **5000** - Flask default port
- **3000** - Node.js default port

Access forwarded ports via the Ports panel in VS Code.

## 💡 Pro Tips

1. **Terminal** - Use the integrated terminal (Ctrl+`) which opens with Zsh
2. **GitLens** - Hover over any line to see who changed it and when
3. **TODO Tree** - View all TODOs in the project in the sidebar
4. **REST Client** - Create `.http` files to test web endpoints
5. **Coverage Gutters** - See test coverage inline in your code
6. **Git Graph** - Visualize your repository's commit history
7. **Regex Helper** - Press Ctrl+Alt+M on a regex to test it interactively

## 🔒 Security

- Container runs as non-root user (`vscode`)
- Bandit security scanner pre-installed
- Safety checks for vulnerable dependencies
- Git safe directory configured automatically

## 📚 Documentation

- [Devcontainer README](.devcontainer/README.md) - Detailed devcontainer documentation
- [VS Code Devcontainers](https://code.visualstudio.com/docs/devcontainers/containers)
- [GitHub Codespaces](https://docs.github.com/en/codespaces)
- [Photon Wiki](https://github.com/s0md3v/Photon/wiki)

## 🆘 Troubleshooting

### Container won't build
- Check that devcontainer.json is valid JSON with Comments
- Ensure all features are accessible
- Check the build logs in the Output panel

### Extensions not loading
- Wait for the container to fully initialize
- Check the Extensions panel for any errors
- Rebuild the container: Command Palette → "Codespaces: Rebuild Container"

### Python packages missing
- Run: `pip install -r requirements.txt`
- Or use the task: "Install/Update Dependencies"

## 🎉 What Makes This "The Biggest The Best"

This devcontainer configuration is comprehensive and includes:

✅ **33 carefully selected VS Code extensions**  
✅ **Complete Python development toolchain**  
✅ **Security and quality scanning tools**  
✅ **Git and GitHub integration**  
✅ **Docker-in-Docker support**  
✅ **Enhanced Zsh shell with Oh-My-Zsh**  
✅ **Multiple debugging configurations**  
✅ **Pre-configured tasks for common operations**  
✅ **Code snippets for faster development**  
✅ **Comprehensive settings optimized for Python**  
✅ **Automatic code formatting and linting**  
✅ **Test coverage visualization**  
✅ **Interactive tools (IPython, Jupyter)**  
✅ **Port forwarding for web development**  
✅ **Welcome message with quick reference**  
✅ **EditorConfig for consistent formatting**  
✅ **Documentation and guides**  

This is a **production-ready, enterprise-grade development environment** that provides everything you need to contribute to Photon efficiently and effectively! 🚀
