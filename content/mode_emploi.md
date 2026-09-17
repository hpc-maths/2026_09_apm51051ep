# How to run the Jupyter notebooks

Three options are available to run the notebooks provided for the lectures and the petites classes:

## Use your own environment

For this mode, simply download the Jupyter notebooks from this site and run them on your own machine. To install the software environment required to run the notebooks of the course, follow the procedure below.
  
```{admonition} Procedure to install Jupyter Notebook

- Install the latest version of `miniforge` (available at https://github.com/conda-forge/miniforge).

- Create a new environment for the course:

`mamba create -n apm51051ep python=3`


- Activate the apm51051ep environment:

`mamba activate apm51051ep` 


-  Install the python packages required for the course:

`mamba install jupyter numpy scipy sympy plotly matplotlib`


-  Start the Jupyter server:

`jupyter notebook` or `jupyter lab`
```

## Use the JupyterHub of the school

For this mode, simply download the Jupyter notebooks from this site and copy them to the `JupyterHub` server of the school (see the procedure below).

```{admonition} Using the JupyterHub of the school

- In a browser, go to the [JupyterHub of the school](https://jupytercloud.idcs.polytechnique.fr), click on the `jupyter` link and then on the `Sign in with CNRS/INSMI/Mathrice OpenID-Connect Provider` button


- Select the institution Ecole Polytechnique Palaiseau, then use your polytechnique credentials to log in to the platform


- On the `Server Options` page, click in the `MAP412` box: this starts a `JupyterLab` with all the modules required for the course


- Click on the `Upload files` icon in the left sidebar menu to upload a notebook from your machine to the `JupyterLab`, then run it


- Download a notebook from the platform to your machine by right-clicking on the name of the notebook in the left sidebar and choosing `download`


- Note: move your notebooks to the `persistent` directory so that they are kept for a future session  
``` 
