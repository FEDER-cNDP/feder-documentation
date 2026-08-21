# Launch with RStudio or VS Code

In addition to the default JupyterLab server, both RStudio and VS Code can be deployed through the JupyterHub service.

<img src="../images/r-studio-vscode.png" style="border: 2px solid black;">

Once your server is running, select RStudio or VS Code from the launcher window. This will open a new tab with the corresponding interface, ready for you to begin your work.

**Please note**: the FEDER extension is not available within the RStudio or VS Code environments. To continue using its features, keep your JupyterLab session open in a separate tab or window.

As with all Jupyter-launched servers, packages installed within RStudio are not persistent. Any packages you add during a session will be lost once the server is stopped. To ensure reproducibility and persistence:

- Maintain a list of required packages within your project (e.g., a `requirements.R` file or a project-specific script).
- For long-term use, consider creating a customized Docker image with all necessary R packages pre-installed.