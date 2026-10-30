# How to launch workspace

In this tutorial, you’ll learn how to work with a workspace in [JupyterHub](https://feder-jupyterhub.nrp-nautilus.io/hub/).

#### 1. Launch Your Workspace in JupyterHub


- Go to *Research Hub --> My Hub* and click the workspace you want to launch.
- Scroll down and click *Launch Options*.
- Select the compute resource that fits your workspace. This guide covers the [**NSF National Research Platform (NRP)**](https://nrp.ai/), the main compute resource available.

<img src="../images/jupyter-launch.png" style="border: 2px solid black;">

#### 2. Configure Your Resources

After you open JupyterHub, reserve the compute resources your workspace needs:
- **Use preset defaults:** Launch your workspace with the preset default resource values.
- **Workspaces copied from the public collection:** Reserve the resources listed in the workspace's instructions.
- Your own workspaces, or if you're unsure what you need:** Start with the default configuration, then adjust as needed. Reserve only what your work requires, so resources stay available for other users.


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

## How to execute a query in a workspace

!!! info
    The workspace used in this section is currently restricted, and access is granted only to approved users. If you'd like to try the workspace, please email `feder@nationaldataplatform.org` to request access.

**1.** Select the Workspace through the dropdown: *He-modified Tungsten Lifecycle Dataset*

<img src="../images/he-modified.png" style="border: 2px solid black;">

**2.** Clone Repository by clicking on the button Clone into Current Folder:

<img src="../images/clone-he-modified.png" style="border: 2px solid black;">


**3. To open the AI Agentic Notebook** - Click on folder icon on the left vertical navigation bar and open the notebook: `plasma-facing-materials-demo` --> `argus_feder_materials_he_effect_v4_jupyterhub.ipynb`

<img src="../images/argus-notebook.png" style="border: 2px solid black;">

**4. Configure LLM** - 

- **First-time users:** For instructions on applying for an AMSC LLM API key and FDP token,	email: `feder@nationaldataplatform.org`

- **Provide your AmSC LLM API key:** Create the file `~/work/_User-Persistent-Storage_CephBlock_/.env` with the following content:
`AMSC_LLM_KEY=Your Key`

**5. Run the AI Agentic Notebook or Run the `%%ask cell`:** Click the `Run` button in the top toolbar or to run individual code cells, press `Shift + Enter` on your keyboard. The output will appear right below the cells.

## How to review and audit agent-generated codes

FEDER provides multiple levels of transparency and validation to help researchers review agent activities, inspect generated code, and verify analytical results.

**Level 1: Review Agent Execution Steps** - The agent uses write_todos to display its planned tasks and execution progress directly below the notebook cell. You can follow these steps to understand what the agent is doing and monitor its progress.

<img src="../images/ask.png" style="border: 2px solid black;">

**Level 2: Audit Agent-Generated Code** - The agent provides file paths to its generated Python scripts. Open these files using the File Browser to inspect the code, data transformations, and analytical methods. This helps you verify that the scripts perform the intended operations and align with your research objectives.

<img src="../images/audit.png" style="border: 2px solid black;">

**Level 3: Independent AI-Assisted Validation** - Researchers can enable an additional review using the --review flag with %%ask. This invokes a separate AI agent to assess the completeness and correctness of the generated results, helping identify missing steps, inconsistencies, and potential errors.

To enable independent validation, run the following in a notebook cell:

```
%%ask --review
Your scientific question here
```

**Note:** Independent validation is disabled by default because it adds several minutes to execution time. Level 3 runs only when explicitly requested using `--review`.

These three levels provide visibility into agent execution, code-level auditability, and independent AI-assisted validation. You can review and verify the generated workflows and scientific results rather than relying solely on the agent's output.
