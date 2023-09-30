[![Github Actions CI status](https://github.com/mmartyn3/ci-python-example/actions/workflows/github_py_ci.yaml/badge.svg)](https://github.com/mmartyn3/ci-python-example/actions/workflows/github_py_ci.yaml)

# Flask Demo App with GitHub Actions CI
This repository contains a simple Flask app along with a GitHub Actions Continuous Integration (CI) script. The CI pipeline performs linting (flake8), runs tests (pytest), and formats (black) the code.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [CI Pipeline](#ci-pipeline)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. Clone the repository: ```git clone https://github.com/mmartyn3/ci-python-example.git```
2. Navigate to the project directory: ```cd ci-python-example```
3. Set up a virtual environment: ```python3 -m venv venv```
4. Activate virtual env: ```source venv/bin/activate```
5. Install required Python packages: ```pip install -r requirements.txt```

## Usage

1. Lint the Flask app locally: ```flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics```
2. Test the Flask app locally: `pytest`
3. Format the Flask app locally: `black --line-length 127 myapp.py`
4. Run the Flask app locally: ```python myapp.py``` then visit `http://127.0.0.1:5000/`

## CI Pipeline

The CI pipeline is defined in `.github/workflows/github_py_ci.yaml`. The pipeline is triggered on `push` and `pull_request` events to the `main` branch.

### Jobs

- **build**: Sets up the environment and runs the following steps:
  - Code checkout
  - Python 3.11 setup
  - Pip and dependencies installation
  - Linting with Flake8
  - Testing with PyTest
  - Code formatting with Black

### Flake8 Linting

The pipeline uses Flake8 for linting and is configured to:

- Stop the build if there are any critical errors
- Treat all other issues as warnings
- Limit complexity to 10
- Limit line length to 127

### PyTest

Tests are run using PyTest. Try to add some more tests to the test file `test_myapp.py`.

### Black Formatting

Code is auto-formatted using Black with a line length of 127.

## Contributing

1. Fork the repository
2. Create a new branch
3. Commit your changes
4. Create a Pull Request
5. Make sure all checks pass

## License

[MIT License](LICENSE)
