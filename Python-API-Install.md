# Google Earth Engine Demo 	

## Installing the Python API



#### 1. Create a new Conda environment and add packages

* At the Conda prompt: 
  * `conda create --name earthengine`
  * `activate earthengine`
  * `conda install -c conda-forge earthengine-api`
  * `conda install jupyter pandas matplotlib` (and other packages...)


####  2. Check earthengine configuration and authenticate

* Still at the Conda prompt:
  * `cd %CONDA_PREFIX%`       [navigates to the image's folder]
  * `python`                            [starts the Python command console]
  * \>>> `import ee`              [initializes earth engine; errors indicate installation issues]
  * \>>> `ee.Initialize()`   [*\*this should create an error that you need to authenticate\**]
  * \>>> `exit()`                    [quits Python]
  * `earthengine authenticate ` 
  * Log in to your Google Account
  * Copy the authorization code to the clipboard & paste at the command line

#### 3. Setting up Jupyter notebook

* Still at the Conda prompt:

  * `explorer scripts` [opens explorer to the "scripts" sub-directory of the Conda image folder]

* In Explorer:

  * Right-click and copy the `jupyter.exe` icon to the clipboard

  * Navigate to your workspace folder (e.g. a Git workspace)
  * Paste *as short cut*
  * Right-click the newly made shortcut and open its properties. 
    * Optional: rename the shortcut file
  * Clear the contents in the `Start in:` box; this will open the notebook in the current folder
  * Double click the Jupyter shortcut to open the Juptyer notebook console



## Using the Google Earth API

#### 1. Importing the ee module and activating it

```python
import ee
ee.Initialize()
```

