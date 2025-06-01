# Quick Start Guide

This guide will help you get started with SmartPouch quickly and efficiently.

## System Requirements

### Hardware Requirements
- CPU: 2 GHz or faster processor
- RAM: 4 GB minimum (8 GB recommended)
- Storage: 1 GB free disk space
- Network: Stable internet connection

### Software Requirements
- Python 3.8 or higher
- Git
- pip (Python package manager)
- Virtual environment (recommended)

## Installation Steps

### 1. Clone the Repository
```bash
git clone https://github.com/movement-recognition/smartpouch.git
cd smartpouch
```

### 2. Set Up Virtual Environment (Recommended)
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On Unix or MacOS:
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure Environment
```bash
# Copy the example environment file
cp .env.example .env

# Edit the .env file with your configuration
# Required settings:
# - API_KEY: Your API key for external services
# - DATABASE_URL: Database connection string
# - LOG_LEVEL: Logging level (DEBUG, INFO, WARNING, ERROR)
```

## Verify Installation

Run the following command to verify the installation:
```bash
python -m smartpouch --version
```

You should see the current version of SmartPouch displayed.

## Troubleshooting

### Common Issues

1. **Dependencies Installation Fails**
   - Ensure you have the latest version of pip: `pip install --upgrade pip`
   - Try installing dependencies one by one to identify problematic packages

2. **Environment Configuration Issues**
   - Verify that all required environment variables are set
   - Check file permissions for the .env file

3. **Version Compatibility**
   - Ensure Python version meets requirements: `python --version`
   - Check compatibility of installed packages

### Getting Help

If you encounter any issues:
1. Check the [User Guide](usage.md) for detailed usage instructions
2. Visit our [GitHub Issues](https://github.com/movement-recognition/smartpouch/issues) page
3. Join our community forums for support

## Next Steps

After successful installation:
1. Review the [User Guide](usage.md) for detailed usage instructions
2. Check the [Data Specification](data.md) to understand data formats
3. Explore example configurations in the `examples` directory

## Updating SmartPouch

To update to the latest version:
```bash
git pull origin main
pip install -r requirements.txt
``` 