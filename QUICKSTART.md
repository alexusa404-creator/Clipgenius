# ClipGenius Quick Start Guide

## For Users

### Installation (Development)

```bash
# Clone and install
git clone https://github.com/alexusa404-creator/Clipgenius.git
cd Clipgenius
pip install -e .

# Use the CLI
clipgenius --help
```

### Installation (Once Published to PyPI)

```bash
pip install clipgenius
clipgenius --help
```

## For Developers

### Setup Development Environment

```bash
# Clone repository
git clone https://github.com/alexusa404-creator/Clipgenius.git
cd Clipgenius

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install in editable mode
pip install -e .
```

### Building the Package

```bash
# Install build tools
pip install build wheel twine

# Clean previous builds
rm -rf dist/ build/ *.egg-info

# Build distribution files
python setup.py sdist bdist_wheel

# Check the build
ls -lh dist/
```

### Testing the Package

```bash
# Create test environment
python -m venv test_env
source test_env/bin/activate

# Install from wheel
pip install dist/clipgenius-1.0.0-py3-none-any.whl

# Test the CLI
clipgenius --help

# Check package info
pip show clipgenius
```

### Project Structure

```
Clipgenius/
├── clipgenius/              # Main package
│   ├── __init__.py         # Package initialization
│   ├── __main__.py         # python -m clipgenius entry
│   ├── cli.py              # CLI interface (main entry)
│   ├── ai_agent.py         # AI functionality
│   ├── downloader.py       # Video downloading
│   ├── batch.py            # Batch processing
│   └── utils.py            # Utilities
├── LICENSE                  # MIT License
├── MANIFEST.in             # Distribution manifest
├── pyproject.toml          # Modern packaging config
├── setup.py                # Setup configuration
├── requirements.txt        # Dependencies
├── README.md               # Main documentation
├── PUBLISHING.md           # Publishing guide
└── PACKAGING_SUMMARY.md    # Packaging overview
```

### Key Files Explained

- **setup.py**: Traditional setuptools configuration, defines package metadata and dependencies
- **pyproject.toml**: Modern packaging config (PEP 518/621), preferred by newer tools
- **MANIFEST.in**: Specifies additional files to include in source distributions
- **requirements.txt**: Lists all dependencies for easy installation during development
- **LICENSE**: MIT License file (required for distribution)

### Running ClipGenius

```bash
# Method 1: Using the installed command
clipgenius https://www.youtube.com/watch?v=example

# Method 2: Using Python module syntax
python -m clipgenius https://www.youtube.com/watch?v=example

# Method 3: Direct script execution (development)
python clipgenius/cli.py https://www.youtube.com/watch?v=example
```

### Common Commands

```bash
# Install in development mode
pip install -e .

# Build package
python setup.py sdist bdist_wheel

# Install from local build
pip install dist/clipgenius-1.0.0-py3-none-any.whl

# Uninstall
pip uninstall clipgenius

# Check installed version
pip show clipgenius

# List installed files
pip show -f clipgenius
```

## Publishing to PyPI

See [PUBLISHING.md](PUBLISHING.md) for detailed instructions on publishing to PyPI.

## Package Features

✅ **Easy Installation**: Simple `pip install clipgenius`  
✅ **Automatic Dependencies**: All dependencies installed automatically  
✅ **CLI Command**: `clipgenius` command available system-wide  
✅ **Virtual Environment Support**: Works with venv, virtualenv, conda  
✅ **Cross-Platform**: Windows, macOS, Linux  
✅ **Python 3.8+**: Compatible with Python 3.8 and newer  

## Dependencies

- yt-dlp >= 2023.10.13 - Video downloading backend
- openai >= 1.0.0 - AI assistant functionality
- click >= 8.0.0 - CLI framework
- colorama >= 0.4.6 - Colored terminal output
- requests >= 2.31.0 - HTTP requests
- beautifulsoup4 >= 4.12.0 - Web scraping

## Configuration

### OpenAI API Key (Optional)

For AI features:

```bash
# Linux/macOS
export OPENAI_API_KEY='your-api-key-here'

# Windows
set OPENAI_API_KEY=your-api-key-here

# Or create a .env file
echo "OPENAI_API_KEY=your-api-key-here" > .env
```

## Troubleshooting

### "clipgenius command not found"
- Ensure the package is installed: `pip show clipgenius`
- Check your PATH includes Python scripts directory
- Try: `python -m clipgenius` instead

### Import errors after installation
- Make sure all dependencies are installed: `pip install -r requirements.txt`
- Try reinstalling: `pip install --force-reinstall clipgenius`

### Building fails
- Update build tools: `pip install --upgrade pip setuptools wheel build`
- Clean old builds: `rm -rf dist/ build/ *.egg-info`

## Help & Support

- Read the main [README.md](README.md) for usage examples
- Check [PACKAGING_SUMMARY.md](PACKAGING_SUMMARY.md) for package details
- Open an issue on GitHub for bugs or questions
