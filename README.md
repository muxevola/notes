# HOW TO: venv with  VSC for Jupyter

myenv = id0

Setting up a virtual environment in Visual Studio Code (VS Code) for Jupyter Notebooks ensures an isolated Python environment for your project. Follow these steps to create and configure it:

Step 1: Install the Python Extension

Open VS Code.
* Go to the Extensions view (Ctrl+Shift+X or Cmd+Shift+X on Mac).
* Search for Python and install the official extension.

Step 2: Create a Virtual Environment
* Open the terminal in VS Code (`Ctrl+`).
* Navigate to your project directory:
* `cd /path/to/your/project`
* Create a virtual environment:
* `python -m venv myenv`

Step 3: Activate the Virtual Environment
* Windows:
* `myenv\Scripts\activate`
* Mac/Linux:
* `source myenv/bin/activate`
* You should see the virtual environment name in your terminal prompt.
* You might have to remove PS limitations
* `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned`

Step 4: Install Jupyter Notebook
* With the virtual environment activated, install Jupyter:
* `pip install jupyter ipykernel`

Step 5: Add Virtual Environment to Jupyter
* Register your virtual environment as a Jupyter kernel:
* Replace myenv with your virtual environment name.
* `python -m ipykernel install --user --name=myenv --display-name "Python (myenv)"`

Step 6: Configure VS Code to Use the Virtual Environment
* Open the Command Palette (Ctrl+Shift+P or Cmd+Shift+P on Mac).
* Select Python: Select Interpreter.
* Choose the interpreter from your virtual environment (e.g., /path/to/myenv/bin/python).

Step 7: Select Kernel in Jupyter Notebook
* Open or create a .ipynb file in VS Code.
* Click on the kernel picker in the top-right corner of the notebook editor.
* Select the kernel associated with your virtual environment.

Step 8: checks
* VSC Terminal
* `Get-Command python`
* Jupyter Notebook
```
import os
print(os.environ.get('VIRTUAL_ENV'))
import sys
print(sys.prefix)
```


By following these steps, you can ensure that your Jupyter Notebook runs within an isolated and properly configured Python environment in VS Code
