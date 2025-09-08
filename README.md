# Django in a Dev Container

This repository demonstrates a basic Django application configured to run inside a Visual Studio Code Development Container. The main goal is to showcase the setup and benefits of a containerized development environment.

## Prerequisites

*   [Docker Desktop](https://www.docker.com/products/docker-desktop)
*   [Visual Studio Code](https://code.visualstudio.com/)
*   [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) for VS Code

## Getting Started

1.  **Clone the repository** and open the folder in Visual Studio Code.
    ```bash
    git clone <your-repository-url>
    cd Dev-Containers-Practice
    code .
    ```

2.  **Reopen in Container**:
    *   When you open the folder, VS Code will detect the `.devcontainer` configuration and prompt you to "Reopen in Container".
    *   Click that button.
    *   If you don't see the prompt, open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`) and run `Dev Containers: Re-open in Container`.

3.  **Wait for the build**:
    *   The first time, Docker will build the image, which may take a few minutes.
    *   The `postCreateCommand` in `.devcontainer/devcontainer.json` will automatically install all Python dependencies listed in `requirements.txt`.

4.  **Run the Django Server**:
    *   Once the container is running, open a new terminal in VS Code (`Ctrl+` or `Cmd+`).
    *   Run the database migrations and start the development server:
        ```bash
        python manage.py migrate
        python manage.py runserver 0.0.0.0:8000
        ```
    *   VS Code should automatically forward port 8000. You can now access the application in your browser at `http://localhost:8000`.

## Dev Container Configuration

*   `.devcontainer/devcontainer.json`: This is the core configuration file. It tells VS Code how to build and configure the container, what extensions to install, and what commands to run after creation.
*   `.devcontainer/setup.sh`: A shell script that is run by the `postCreateCommand`. It's used here to install Python packages.
*   `requirements.txt`: Lists the Python dependencies for the project, which are installed automatically when the container is created.

