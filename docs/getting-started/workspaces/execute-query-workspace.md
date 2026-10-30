# How to execute a query in a workspace


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
