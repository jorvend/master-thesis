# Ground motion directionality for the design and assesment of structures

This repository cotains the OpenSees Code for my Master's Thesis: Ground motion directionality for the design and assesment of structures.

The project has been developed in the Department of Civil and Environmental Engineering at University of California Irvine under the superivion of Prof. Farzin Zareian, and it is evaluated at Universtiat Politècnica de Catalunya (UPC) as the master thesis.

<p align="center">
  <img src="./img/baixa.png" width="200" alt="UCI">
  <img src="./img/BCeater-right-768x416.png" width="350" title="Peter the Anteater">
</p>

<p align="center">
  <img src="./img/Etseib_logo.png" width="450" alt="UCI">
</p>

## Structure of the repo

The code is located under TFM folder, and it contains:

- **nga_west2_db** folder with the data extracted from NGA West 2 database for the selected earthquakes.
- **plots** folder with the plots generated.
- **split_files** folder with splitted files with the data recordings for the opensees analysis performed. The files are splittd as Github only allows uploads up to 100MB for each file.
- 3 jupyter notebooks:
  - **opensees_analysis.ipynb** contains code that performs the analysis over the building with opensees and it exports the recorded data to .txt files.  
  :warning: This notebook takes long to execute, it already took 2 days and 18h only for the time history analysis.
  - **opensees_plots.ipynb** contains the code to read the data in the .txt files and generate plots. Before using it, read how to prepare the .txt files in the following section.
  - **opensees_extra_plots.ipynb** contains extra plots.

## Join splitted .txt files with the analysis data

It can be done using, for example, the Git bash terminal.

The files were splitted in the following manner:
```
split -b 50M ./TFM/earthquakes_data.txt ./TFM/split_files/earthquakes_data.txt.
```

To work again with this repository, for each of the splitted files group you should execute the following:
```
cat ./TFM.split_files/earthquakes_data.txt.* > ./TFM/earthquakes_data.txt
```
# Working with git

## Create and clone a repo

- Create a repo on the github website inside jorvend user

- git clone https://github.com/jorvend/master-thesis.git (on the green button "code")

## Pull changes from github repo

- git pull

## Make changes from the github repo

- git status (to see what is changed)

- write in the gitignore file the files I don't want to push

- git add . (to add everything)

- git status (to see again if the changes are added)

- git commit -m "Update gitignore"

- git push (to push it to the github cloud)

# Working with this repo

## 1. Python virtual environment setup

Create a virtual environment with python version 3.9 (the maximum supported by OpenSeesPy latest version 3.4.0.2). From the working directory execute:

`py -3.9 -m venv tfm_env` (ONLY FIRST TIME)

Each time, previous to start working, execute:

`./tfm_env/Scripts/activate` (ALWAYS)

You'll see something like (in Windows):

`(tfm_env) PS C:\_\UCI\master-thesis> ` (ALWAYS)

## 2. Install OpenSeesPy and other dependencies

You can install all the dependencies from the requirements.txt file

`(tfm_env) PS C:\_\UCI\master-thesis> python -m pip install -r requirements.txt` (EACH TIME I ADD NEW LIBRARIES)

## 3. Start a Jupyter Notebook

### Option: From installed jupyter kernel

- From the activated python env install (ONLY FIRST TIME)

  `(tfm_env) PS C:\_\UCI\master-thesis> python -m pip install notebook`

  `ipython kernel install --user --name=tfm_env`

- Run:

  `jupyter notebook`

- Connect to a Jupyter Kernel with your venv.
