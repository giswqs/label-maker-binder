# Using label-maker in an interactive notebook on the cloud

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/giswqs/label-maker-binder/master)

## Usage

* Launch [Binder](https://mybinder.org/v2/gh/giswqs/label-maker-binder/master) 
* On the Jupyter Notebook interface, click **New - Text File**
* Change the file name from untitled.txt to **config.json**
* Copy and paste the content from the [config.example.json](https://github.com/giswqs/label-maker/blob/master/config.example.json) and change the **ACCESS_TOKEN** to your mapbox token. 
* Save **config.json** (Menu - File - Save)
* Create a new Jupyter Notebook (New - Notebook - Python 3)
* Enter the following commands. See this [example](https://github.com/giswqs/label-maker-binder/blob/master/examples/label-maker-binder.ipynb)

```python
!label-maker download
!label-maker labels
!label-maker preview -n 10
!label-maker images
!label-maker package
```
