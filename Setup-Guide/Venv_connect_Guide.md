# Virtual Environment Configuration Guide

This guide will help you create a virtual environment, activate it, and configure it with Jupyter Notebook extension in VSCode for your development environment.

## Step 1: Create a Virtual Environment
Run one of the following commands to create a virtual environment:

```bash
python -m venv my_env
```
**or**
```bash
py -m venv my_env
```

> **Note:** Replace `my_env` with your desired environment name.

## Step 2: Activate the Virtual Environment

### On Windows:
```bash
my_env\Scripts\activate
```

### On Linux/Mac:
```bash
source my_env/bin/activate
```

Once activated, you should see the environment name in the terminal prompt, indicating the environment is active.


## Step 3: Run Jupyter Notebook in Virtual Environment

In VSCode:

1. Click on File → New File.
    ![vscode](https://github.com/user-attachments/assets/411d0260-54ec-40a3-aea1-0a1ea741935e)

2. Select Jupyter Notebook as the file type.
    ![jupyer_notebook](https://github.com/user-attachments/assets/0a3c1bec-de30-4dd8-b010-6b8c1182c22e)
    
3. Click on the Kernel at the top-right corner of the notebook and select python Environment.
    ![kernel](https://github.com/user-attachments/assets/eabff026-c833-41b6-87a5-33352de6ce18)

4. Select Python (my_env) under Python Environments.
    ![gven](https://github.com/user-attachments/assets/9c9e5fc1-d68b-4614-91c4-f8e2b6d00214)

    ![gvp_evnv](https://github.com/user-attachments/assets/8053a0ff-d6df-44a0-ac18-a20e6cfe43f7)

> **Note:** If prompted for access permissions, click Allow to proceed.
    


## Step 5: Deactivate the Environment (Optional)
To exit the virtual environment, run:

```bash
deactivate
```

Your virtual environment is now set up and ready for development!

> **Note:** If Need more Info Use below Link.
 
[VS Code Jupyter Notebook Documentation](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)
