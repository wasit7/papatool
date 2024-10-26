# **Papatool**

`Papatool` is a simple Python command-line tool to automate the process of creating, building, and uploading Python packages to PyPI. It helps streamline the packaging and publishing workflow, making it easier for Python developers to manage their projects.

## **Features**

- **Create**: Automatically generate a new Python project with a predefined structure (including `setup.py`, `README.md`, and package folders).
- **Build**: Cleans up old build files and creates new distributions (source distribution and wheel).
- **Upload**: Upload the package to PyPI using `twine`.

## **Installation**

To install `Papatool` directly from GitHub, use `pip`:

### From PyPI:

```bash
pip install papatool
```

### From github

```bash
pip install git+https://github.com/wasit7/papatool.git
```

This will install `Papatool` globally, and you can run it from your terminal.

## **Usage**

### 1. **Create a New Project**

To create a new Python project with the necessary structure:

```bash
papatool create <project_name>
```

This will create a directory with the following structure:

```
<project_name>/
│
├── <project_name>/                # Package folder
│   └── __init__.py
│
├── setup.py                       # Package configuration
├── README.md                      # Project documentation
└── LICENSE                        # License file
```

### 2. **Build the Package**

To build your project (cleans up old builds and generates new distributions):

```bash
papatool build
```

This will:
- Remove existing `dist/`, `build/`, and `*.egg-info` directories.
- Create a source distribution (`.tar.gz`) and a wheel (`.whl`).

### 3. **Upload the Package to PyPI**

To upload the package to PyPI:

```bash
papatool upload
```

This command uses `twine` to upload the package to PyPI. Ensure you have your PyPI credentials ready when prompted.

## **Example Workflow**

```bash
# Create a new project
papatool create my_project

# Navigate to the project folder
cd my_project

# Build the package
papatool build

# Upload the package to PyPI
papatool upload
```

## **Dependencies**

`Papatool` depends on the following packages:

- `setuptools`: Used to manage the package configuration.
- `wheel`: Required for building a `.whl` distribution.
- `twine`: Used for securely uploading the package to PyPI.

These dependencies will be automatically installed when you install `Papatool`.

## **Setup PyPI Token**
1. Login to your PyPI account: Go to [PyPI](https://pypi.org/account/login/) and log in with your account.
2. Generate an API token:
- Navigate to your account settings.
- Under "API tokens", create a new API token by clicking on "Add API token".
3. Eet up your ~/.pypirc file like this:

```bash
[pypi]
repository: https://upload.pypi.org/legacy/
username: [your user]
password: pypi-[your-api-token]
```

## **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## **Contributing**

If you want to contribute to `Papatool`, feel free to fork the repository and submit a pull request with your changes.
