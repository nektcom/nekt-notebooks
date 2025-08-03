# Nekt - Notebook for Data Transformation

This guide will walk you through the steps to set up your environment and use this notebook to load multiple tables from your Lakehouse, perform data transformations and validate your code before executing it on production at Nekt.

You will be able to:
- [Run locally](https://github.com/nektcom/nekt-notebooks?tab=readme-ov-file#run-locally): Set up a local Python environment using uv for dependency management.
- [Run locally using Dev Container](https://github.com/nektcom/nekt-notebooks?tab=readme-ov-file#run-locally-using-dev-container): Use Dev Containers to create an isolated environment with all the dependencies required to run PySpark transformations, no additional setup required.
- [Run on GitHub Codespaces](https://github.com/nektcom/nekt-notebooks?tab=readme-ov-file#run-on-github-codespaces): GitHub Codespaces gets you up and coding faster with fully configured, secure cloud development environments native to GitHub.

## Run locally

### Prerequisites

- Python 3.9
- [uv](https://docs.astral.sh/uv/) - Modern Python package and project manager

### Setup

1. Open this repository in your preferred editor.
2. Run `uv sync` to create your virtual environment and download dependencies.
3. Open the notebook and select the kernel at `.venv/bin/python`.

## Run locally using Dev Container

### Prerequisites

- [Docker](https://www.docker.com/get-started/)
- [VS Code](https://code.visualstudio.com/download), [Cursor](https://www.cursor.com/), or any VS Code-based editor
- [VS Code extension - Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

### Setup

1. Open Docker desktop app and wait until the Docker engine is up and running.
2. Open this repository on VS Code on the root folder. This is what it should look like:
![image](https://github.com/user-attachments/assets/cf9adf68-4367-486e-8153-c0d222e0ae65)

3. Open VS Code command palette (Control+Shift+P on Windows or CMD+Shift+P on MacOS).
4. Run `Dev Containers: Reopen in Container`
![image](https://github.com/user-attachments/assets/1f3ab775-0f34-4ef9-bcfd-7d4e2e2e2c26)

5. The project will reopen on a new window of VS Code. You can click on `show log` on the bottom right corner to see the progress. Wait until the environment is set up and all dependencies are installed.
   ![image](https://github.com/user-attachments/assets/55b17002-bf87-456d-8519-9a9d1447cd1a)

## Run on GitHub Codespaces

### Prerequisites

- A GitHub account
- Access to GitHub Codespaces

### Setup

1. Click on **Code**.
2. Click on **Create codespace on main**.
![image](https://github.com/user-attachments/assets/2fcaefc3-eb01-4de7-82e3-8f824657e10c)

3. A new tab will open with a web version of VS Code. Wait until the environment is set up and all dependencies are installed.
![image](https://github.com/user-attachments/assets/9feb9888-c767-401b-9f2d-de109d95c840)

4. Once everything is ready, this README will show up in VS Code.
![image](https://github.com/user-attachments/assets/8366f425-685a-4de7-b681-c37b22164dce)

## Using the Notebook

The template notebook is pre-filled to help you load tables directly from your Lakehouse, perform the required data transformations, and guide you on the next steps to deploy your transformation code on our platform. Here's a quick overview of how to use it:

- **Load Data**: Follow the steps in the notebook to connect to your data sources and load the data into the notebook environment.
- **Transform Data**: Utilize the pre-built functions or add your own transformations as needed.
- **Deploy**: Instructions are provided within the notebook on how to deploy your code once your data operations are complete.

## Deployment

After testing your data transformations in the Jupyter notebook, it's time to deploy your code at Nekt:

1. Perform testing and validation of your Jupyter notebook script to ensure it's working as intended;
2. Go to [Add transformation](https://app.nekt.ai/transformations/add-transformation), select PySpark and add your code in the code section.
   - If you are using any custom Python dependencies, don't forget to add them in the `Dependencies` section.

## Best Practices

- **Isolate Environments**: Use uv or pip to manage dependencies. For local development with uv, add dependencies to `pyproject.toml`. For Dev Container environments, add new dependencies by updating [Dockerfile](.devcontainer/Dockerfile#L18).
- **Version Control**: Consider using version control (e.g., git) to manage and track changes to your notebook and related files. As your data evolves, you have to make sure your data transformations follow along.

## Support

If you encounter any issues or have questions about using the notebook, please message us on Slack or email <support@nekt.com>.
