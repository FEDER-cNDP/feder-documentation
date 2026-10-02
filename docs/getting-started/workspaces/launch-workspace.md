# How to launch workspace

In this tutorial, you’ll learn how to work with a workspace in [JupyterHub](https://feder-jupyterhub.nrp-nautilus.io/hub/).

#### 1. Launch Your Workspace in JupyterHub


- Go to *Research Hub --> My Hub* and click the workspace you want to launch.
- Scroll down and click *Launch Options*.
- Select the compute resource that fits your workspace. This guide covers the [**NSF National Research Platform (NRP)**](https://nrp.ai/), the main compute resource available.

<img src="../images/jupyter-launch.png" style="border: 2px solid black;">

#### 2. Configure Your Resources

After you open JupyterHub, reserve the compute resources your workspace needs:

- **Workspaces copied from the public collection:** Reserve the resources listed in the workspace's instructions.
- **Your own workspaces, or if you're unsure what you need:** Start with the default configuration, then adjust as needed. Reserve only what your work requires, so resources stay available for other users.

After you confirm your selection, your server starts. This usually takes 1–5 minutes.

<img src="../images/jupyter-spawner.png" style="border: 2px solid black;">

#### 3. Troubleshooting Login Issues

If you encounter an error when launching the server:

<img src="../images/error.png" style="border: 2px solid black;">

- Click Logout (top-right corner).

- Log in again and repeat step 2.

#### 4. Navigate and Set Up Your Workspace

- On the left panel, locate the FEDER extension.

- Click the *Current Folder* window.

<img src="../images/current-folder.png" style="border: 2px solid black;">

- Notice the`User_Persistent_Storage`. This folder gives you 10 GB of permanent storage. Files saved anywhere else are deleted when your session ends. To keep your files between sessions, double-click the folder to open it and work there.

  You can skip this step for workspaces you'll run only once, such as demos or training workspaces.

- Return to the FEDER extension by clicking the *FEDER* button on the left panel.

<img src="../images/ndp-button.png" style="border: 2px solid black;">


- Open the *Select Workspace* dropdown and choose your workspace.

- Click *Clone into current folder* and wait for the repository to finish cloning.

<img src="../images/clone.png" style="border: 2px solid black;">

- Go back to *Current Folder* and open the cloned directory.

#### 5. Install Workspace Dependencies

- If the repository includes a `requirements.txt` file, return to the FEDER extension and click *Install requirements.txt*. When the installation log appears, the installation has started. Wait for it to finish before you run any code.

<img src="../images/requirements.png" style="border: 2px solid black;">

!!! info 
    If the .log file doesn't appear, click the button again. Sometimes, the installation completes but the log file isn’t generated on the first attempt.

#### 6.  Add the Dataset(s)

If the workspace instructions ask you to download datasets to the server:

- Under *Add Selected Files*, select the files listed in the instructions.
- If the instructions say to, select *Create Dataset Folder* to store the downloaded files in their own folder.
- Click *Add resources to current folder*. Depending on the size of the data, the download can take from a few seconds to several minutes.

<img src="../images/dataset.png" style="border: 2px solid black;">


**NOTE:** The download fails if:

- You're working in `User_Persistent_Storage` and the files are larger than the space remaining in the folder (10 GB total).
- The resource isn't a direct download URL.
- The dataset uses a Pelican URL (one that starts with `pelican://` or `osdf://`). In this scenario, download it with the *Pelican* tools at the bottom of the extension panel instead.

#### 7. Start your work

- Return to the *Current Folder* view and open your workspace directory. Then open the notebooks or files you need and begin your project.

<img src="../images/notebook.png" style="border: 2px solid black;">

#### 8. Stop Your Server When Finished

- Go to *File* (top left corner) → *Hub Control Panel* → *Stop Server* to shut down your environment when you're done.

<img src="../images/jhub-logout.png" style="border: 2px solid black;">
