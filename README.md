# GitHub Actions Automation Test Project

This is a project designed to test and demonstrate GitHub Actions functionality. It implements an automated weather monitoring system that weekly fetches weather information for Taipei and logs it to a file.

## Features

- Automated Execution: Weekly automated runs using GitHub Actions
- Weather Monitoring: Fetches weather information for Taipei
- Logging: Automatic logging of execution results and weather data
- Auto-commit: Automatically commits updated log files to the repository

## Tech Stack

- Python 3.12
- GitHub Actions
- requests library (for API requests)
- logging module (for log management)

## Setup Instructions

1. Clone the repository:

```bash
git clone [your-repository-url]
```

2. Set up virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# or
.\venv\Scripts\activate  # Windows
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

## GitHub Actions Configuration

This project includes a GitHub Actions workflow configured in `.github/workflows/actions.yml`:

- Automatically runs at 00:00 every day
- Uses Ubuntu latest as the runtime environment
- Automatically installs Python 3.12
- Automatically installs required dependencies
- Executes the `trigger_test.py` script
- Automatically commits updated log files

## Environment Variables

The following environment variables need to be set in your GitHub repository's Settings > Secrets:

- `SOME_SECRET`: Secret key for testing purposes

## Log Files

- Log files are saved in `status.log`
- Uses RotatingFileHandler for log rotation
- Maximum file size: 1MB
- Keeps 1 backup file

## Usage Instructions

1. Local Testing:

```bash
python trigger_test.py
```

2. Automated Execution:

- No manual intervention required, GitHub Actions will execute automatically
- Execution results can be viewed in the Actions tab

## Notes

- Ensure GitHub Secrets are properly configured
- Set up corresponding environment variables for local testing
- Log files will be automatically committed to the repository
