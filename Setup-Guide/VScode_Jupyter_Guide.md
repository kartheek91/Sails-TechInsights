# Installing Visual Studio Code and Jupyter Notebook Extension

This guide will walk you through the process of downloading and installing Visual Studio Code (VS Code) and adding the Jupyter Notebook extension.

## Step 1: Download and Install Visual Studio Code
1. **Visit the VS Code Website:**
   - Go to the [Visual Studio Code website](https://code.visualstudio.com/).
2. **Download VS Code:**
   - Click on the download button for your operating system (Windows, macOS, or Linux).
3. **Install VS Code:**
   - Once the download is complete, open the installer.
   - Follow the installation instructions specific to your operating system:
     - **Windows:** Run the installer and follow the setup wizard.
     - **macOS:** Open the `.dmg` file and drag the Visual Studio Code icon to the Applications folder.
     - **Linux:** Follow the instructions provided on the website for your specific distribution.
4. **Launch VS Code:**
   - After installation, open Visual Studio Code.

## Step 2: Install the Jupyter Notebook Extension
1. **Open Extensions View:**
   - In VS Code, click on the **Extensions** icon in the Activity Bar on the side of the window or press `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (macOS).
2. **Search for Jupyter Extension:**
   - In the Extensions view search box, type **"Jupyter"** to find the Jupyter extension.
     ![image](https://github.com/user-attachments/assets/1f4e7703-d2c1-4143-8448-153de2e2ea7e)

3. **Install the Jupyter Extension:**
   - Click on the **"Install"** button next to the Jupyter extension by Microsoft.
4. **Verify Installation:**
   - Once installed, you can verify the installation by opening a Jupyter Notebook file (`.ipynb`) under the **File** tab in VS Code. The Jupyter extension should automatically activate and provide a rich notebook experience.

## Additional Tips
- **Updating Extensions:**
  - Keep your extensions up to date by checking for updates in the Extensions view.
- **Explore More Extensions:**
  - VS Code offers a wide range of extensions to enhance your development experience. Explore the Extensions Marketplace to find tools that suit your needs.

By following these steps, you will have Visual Studio Code installed with the Jupyter Notebook extension, enabling you to work with Jupyter Notebooks directly within VS Code.

#Issues


## Resolving `OSError: [Errno 2] No such file or directory` in Windows

![image](https://github.com/user-attachments/assets/096516b8-e3e7-4059-b9db-aaa7932997dd)

## **Issue Description**
While installing `ipykernel` or other packages in a Python virtual environment on Windows, the following error may occur:

```
ERROR: Could not install packages due to an OSError: [Errno 2] No such file or directory:
'C:\Users\<username>\<path>\requests\packages\urllib3\packages\ssl_match_hostname\_implementation.pyi'
```

### **Cause**
This issue occurs because **Windows Long Path support** is disabled, causing file paths longer than 260 characters to fail.

---

## **Solution**
### **Step 1: Enable Long Path Support in Windows Registry**
1. Press `Win + R`, type `regedit`, and press **Enter**.
2. Navigate to the following path:  
   ```HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem```
3. Find the entry called **LongPathsEnabled**.
4. If it doesn't exist:
   - Right-click anywhere in the right pane.
   - Select **New** → **DWORD (32-bit) Value**.
   - Name it **LongPathsEnabled**.
5. Double-click **LongPathsEnabled** and set its **Value data** to `1`.
6. Click **OK** and restart your computer.

### **Step 2: Enable Long Path Support in Group Policy (Optional)**
If you have Windows Professional or Enterprise:
1. Press `Win + R`, type `gpedit.msc`, and press **Enter**.
2. Navigate to:  
   ```Computer Configuration -> Administrative Templates -> System -> Filesystem```
3. Double-click **Enable Win32 long paths**.
4. Select **Enabled** and click **OK**.

### **Step 3: Reinstall the Required Packages**
1. Activate your virtual environment:
   ```bash
   .\venv\Scripts\activate    # For Windows
   source venv/bin/activate     # For Mac/Linux
   ```

2. Upgrade `pip` and install `ipykernel` again:
   ```bash
   python -m pip install --upgrade pip
   pip install ipykernel
   ```

---

### **Step 4: Restart VS Code**
After completing these steps, restart VS Code and rerun your notebook.

If you continue facing issues, feel free to ask for further assistance! 🚀


