# Aider Development Environment

This repository contains the development environment for Aider, an AI-powered coding assistant.

## Setup

### Prerequisites

- Python 3.12.0
- pyenv
- pip

### Virtual Environment

We use pyenv to manage Python versions and virtual environments. To set up the development environment:

1.  Create a new virtual environment:

```

pyenv virtualenv 3.12.0 aider\.venv
```

1.  Activate the virtual environment:

```

pyenv activate aider\.venv
```

1.  Install dependencies:

```

pip install -r requirements.txt
```

Note: If you encounter dependency conflicts, you may need to create a fresh virtual environment or use a constraints file.

## Development

### VS Code Configuration

This project includes VS Code debug configurations for easy development and debugging:

1.  **Python: aider.main**: Runs the `aider.main` module with specific arguments.
2.  **Python: Current File**: Runs the currently open Python file.

To use these configurations, ensure your `launch.json` file in the `.vscode` folder contains the following:

```
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python: aider.main",
      "type": "python",
      "args": ["--read", ".pre-commit-config.yaml"],
      "request": "launch",
      "module": "aider.main",
      "justMyCode": false,
      "cwd": "${workspaceFolder}",
      "env": {},
      "python": "/Users/karol/Projects/Personal/aider.venv/bin/python"
    },
    {
      "name": "Python: Current File",
      "type": "python",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal",
      "justMyCode": true,
      "python": "/Users/karol/Projects/Personal/aider.venv/bin/python"
    }
  ]
}
```

### Running Aider

To run Aider, use the following command:

```
python -m aider.main
```

You can add additional arguments as needed.

## Running Tests

This project uses pytest for running its test suite. Follow these steps to run the tests:

### Prerequisites

1. Ensure you have pytest installed. If not, you can install it using pip:

   ```
   pip install pytest
   ```

2. Make sure you're in the root directory of the aider project.

### Running the Tests

To run all tests, use the following command:

```
pytest
```

If you encounter a "ModuleNotFoundError: No module named 'aider'" error, try one of these alternatives:

1. Add the current directory to PYTHONPATH:

   ```
   PYTHONPATH=. pytest
   ```

2. Use the Python module runner:

   ```
   python -m pytest
   ```

3. Install the package in editable mode:

   ```
   pip install -e .
   pytest
   ```

### Running Specific Tests

To run tests in a specific file:

```
pytest tests/path/to/test_file.py
```

To run a specific test function:

```
pytest tests/path/to/test_file.py::test_function_name
```

### Test Coverage

To run tests with coverage reporting:

1. Install pytest-cov:

   ```
   pip install pytest-cov
   ```

2. Run pytest with coverage:

   ```
   pytest --cov=aider
   ```

This will display a coverage report after running the tests.

### Troubleshooting

If you're still having issues running the tests, ensure that:

- You're in the correct directory (the root of the aider project).
- Your virtual environment (if using one) is activated.
- The aider package is properly installed or the project root is in your PYTHONPATH.

For more detailed information about using pytest, refer to the [pytest documentation](https://docs.pytest.org/).

## Troubleshooting

If you encounter dependency conflicts, try the following:

Reinstall aider-chat:

Create a fresh virtual environment:

Use `pip check` to verify your environment's consistency:
