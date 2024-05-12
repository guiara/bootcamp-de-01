# bootcamp-de-01
## Data Engineer Development Environment Setup

In this guide, you will learn how to set up a suitable programming environment to start with data engineer. We will cover the installation and configuration of essential tools such as Python, VS Code, Git, and GitHub, as well as creating a virtual environment and using package managers like pip, pipx, and Poetry.


## Python

1. **Python Installation:**
   - Download and install the latest version of Python:
- **Windows**: Download the Python installer from [python.org](https://www.python.org/downloads/) and follow the installation instructions.
   - Add Python to PATH during installation for easy access via the command line.

- **macOS/Linux**: Python usually comes pre-installed. Verify by typing `python3 --version` in the terminal. If not installed, refer to specific instructions for your operating system.

## Visual Studio Code (VS Code)

1. **VS Code Installation:**
   - Download and install VS Code from [code.visualstudio.com](https://code.visualstudio.com/).
   - Useful extensions for Python: Python, GitLens, Pylance.

2. **VS Code Configuration:**
   - Personalize the editor according to your preferences.


##  Installing Git

Git is an essential version control system for collaboration on software projects. To install it:

- Download and install Git from [git-scm.com](https://git-scm.com/).
- Verify the installation by typing `git --version` in the terminal.

## Configuring GitHub

GitHub is a code hosting platform that enables collaboration and version control. Follow these steps to configure your account:

- Create an account on GitHub at [github.com](https://github.com/).

   1. **Open a Project in VS Code:**
   - Launch VS Code by clicking on its icon or searching for it in your applications folder.
   - Once VS Code is open, go to the "File" menu and select "Open Folder". Alternatively, you can use the keyboard shortcut `Ctrl + O` (Windows/Linux) or `Cmd + O` (Mac).
   - Navigate to the directory where your project is located and select it. Click "Open" to open the project in VS Code.

2. **Initialize Git Repository:**
   - If your project is not already a Git repository, you need to initialize it:
     - Open the integrated terminal in VS Code by selecting "View" > "Terminal" from the menu, or by using the keyboard shortcut `Ctrl + `` (Windows/Linux) or `Cmd + `` (Mac).
     - In the terminal, navigate to your project directory using the `cd` command.
     - Run the command `git init` to initialize a new Git repository for your project.

3. **Git Integration in VS Code:**
   - **Source Control View:**
     - Look for the Source Control icon in the Activity Bar on the side of the VS Code window. It looks like a square with a branch symbol.
     - Click on the Source Control icon to access Git features.
     - Here you'll see all the changes you've made to your project files, and you can stage, commit, and push changes directly from VS Code.

4. **Configure Git Settings:**
   - To configure your Git settings such as user name and email address:
     - Open the integrated terminal in VS Code as before.
     - Use the `git config` command to set your user name and email address. For example:
       ```
       git config --global user.name "Your Name"
       git config --global user.email "your-email@example.com"
       ```

5. **Connect to Remote Repositories:**
   - If your project is hosted on GitHub or another Git hosting service, you can connect your VS Code instance to the remote repository:
     - Click on the Source Control icon again to open the Source Control View.
     - At the top, there should be an option to "Publish to GitHub" or "Add Remote". Click on it and follow the prompts to connect your local repository to the remote one.
     - Once connected, you can push and pull changes directly from VS Code, making collaboration with others much easier.

## Virtual Environment

A virtual environment is a tool that allows you to create and isolate independent Python environments on the same system. This is useful for managing different versions of packages and avoiding conflicts between project dependencies. There are several options for creating virtual environments; let's cover one of them:

### pyenv

pyenv is a Python version management tool that allows you to install and switch between different Python versions on your system.

- **Installing pyenv:**
  - Follow the instructions on the official pyenv repository at [github.com/pyenv/pyenv](https://github.com/pyenv/pyenv#installation).

- **Using pyenv:**
  - Use pyenv to install and manage different Python versions as needed for your projects.

 - **pyenv documentation:** https://github.com/pyenv-win/pyenv-win/blob/master/docs/installation.md#git-commands

 - **pyenv basic comands:**
    - pyenv version  > show all python version you have
    - pyenv install > use to install any python version
    - pyenv globa #version > set up globally version (default)
    - pyenv local #version > set up locally version (folder)

### venv

`venv` is a built-in Python module that allows you to create virtual environments.

- **Creating a virtual environment:**
  - Navigate to your project directory in the terminal.
  - Run the following command to create a new virtual environment:
    ```
    python3 -m venv .venv
    ```
  - Activate the virtual environment:
    - **Windows:** `.venv\Scripts\activate`
    - **macOS/Linux:** `source .venv/bin/activate`
  - Use `ls -al` to list your virtual environment

## Package Managers

Package managers are essential tools for installing, updating, and removing Python packages. Let's cover two of the most popular ones: pip and pipx.

### pip

pip is the default package manager for Python.

[pip documentation](https://pip.pypa.io/en/stable/)
- **Installing packages:**
`pip install package_name`
>note to install any package inside your venv you will only need to activate your virtual environment then run `pip intall package_name`
- **Updating packages:**
`pip install --upgrade package_name`
- **list dependencies**
`pip list`
- **Uninstall packages**
`pip unistall packages`
> note: even after removing the package, dependencies still remain installed on your device. To ensure complete cleanupm run the command below:  
`pip freeze | grep -v "^-e" | xargs pip unistall -y `

### pipx

pipx is a tool that allows you to install and run Python packages in isolated virtual environments.

[pipx documentation](https://github.com/pypa/pipx)


- **Installing packages with pipx:**
`pipx install package_name`
>> Notice that `pipx` will probably be the only package that you will globally install in your environment.

### poetry
Poetry is a Python dependency management and packaging tool that simplifies the process of managing dependencies, packaging projects, and publishing packages. Here are some key features and aspects of Poetry:

- **Dependency Management**: Poetry simplifies dependency management by allowing you to declare project dependencies in a `pyproject.toml` file. You can specify package names, version constraints, and even include direct URL references or VCS dependencies.

- **Virtual Environments**: Poetry automatically manages virtual environments for your projects, isolating dependencies and ensuring consistent environments across different machines. This helps prevent dependency conflicts and makes it easier to share projects with others.

- **Package Building**: Poetry provides commands to build distributable packages (e.g., wheel or sdist) for your Python projects. It handles the packaging process, including resolving dependencies, compiling source files, and generating distribution archives.

- **Dependency Resolution**: Poetry uses a lock file (`poetry.lock`) to ensure deterministic dependency resolution. This means that every time you install dependencies, Poetry will use the exact versions specified in the lock file, ensuring consistent builds across different environments.

- **Project Initialization**: Poetry offers a convenient command-line interface to initialize new Python projects. It sets up the project structure, creates the necessary configuration files, and initializes the virtual environment automatically.

- **Dependency Resolution Algorithm**: Poetry uses a sophisticated dependency resolution algorithm that takes into account various factors such as version constraints, compatibility, and dependency hierarchy to determine the optimal set of package versions to install.

- **Integration with PyPI**: Poetry integrates seamlessly with the Python Package Index (PyPI) for package discovery and distribution. You can easily publish your packages to PyPI using Poetry's publishing commands.

- **Plugin System**: Poetry features a plugin system that allows extending its functionality through custom plugins. This enables developers to integrate Poetry with other tools or add new features as needed.
