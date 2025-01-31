# Setting Up a Virtual Environment for Machine Learning in Quantum Physics

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


## **2. Creating a Virtual Environment**
To create a *virtual environment*, run







# Creating a virtual environment

To manage your machine learning codes, it is a good practice to create a virtual environment using conda.
You can download the miniconda pkg file from https://docs.anaconda.com/miniconda/. Once miniconda is installed, python is also installed. You may need the following

- source ~/.zshrc
- conda --version
- conda list
- conda update conda
- conda create --name env_ml4quantum python=3.12
- conda activate env_ml4quantum
- conda deactivate
- conda env list
- conda remove --name env_name --all


# Installing essential packages

After activating the virtual environment, you can install some essential packages using pip

- pip install jupyter
- pip install numpy
- pip install matplotlib
- pip install pandas
- pip install seaborn
- pip install scipy
- pip install

# Using jupyter notebook

You can code with it or write project descriptions using markdown

