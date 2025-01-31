# Machine Learning in Quantum Physics

To keep your machine learning projects organized, it's best to use a **virtual environment** with Conda.  
This helps manage dependencies and avoid conflicts between different projects.

---

## **1. Installing Miniconda**
You can download and install **Miniconda** from the official website:  
🔗 [Miniconda Download](https://docs.anaconda.com/miniconda/)

Once Miniconda is installed, Python will also be installed. You may need to run the following commands to ensure Conda is properly set up:

```bash
source ~/.zshrc   # Reload shell configuration (for macOS/Linux users)
conda --version    # Check Conda version
conda list         # List installed packages
conda update conda # Update Conda to the latest version
```

## **2. Creating a Virtual Environment**
To create a *virtual environment*, run
```bash
conda create --name env_ml4quantum physics=3.12
```
Then activate or deactivate the environment
```bash
conda activate env_ml4quantum # Activate the environment
conda deactivate              # Deactivate the environment
```
You can also list or remove environments:
```bash
conda env list                            # show all available environment
conda remove --name env_ml4quantum --all  # Delete the environment
```

## **3. Installing Essential Packages**
After activating the virtual environment, install the essential Python packages using pip:
```bash
pip install jupyter numpy matplotlib pandas seaborn scipy
```
You can add more packages later as needed for your project

### **4. Using Jupyter Notebook**

Jupyter Notebook allows you to write and execute code and add markdown descriptions to document your projects.

To start Jupyter Notebook, run:
```bash
jupyter notebook
```
This will open a browser where you can create and run .ipynb files for coding and documentation.
