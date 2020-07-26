# Minimalist guide to uploading a python package to pypi
Lets say you have a code-base that you feel would be helpful to the developer community 
you can package it and upload to pypi so that other develeopers can install it using pip and use 
<br>
this file shows exactly how to do this

## Directory structure

ensure your python packages and modules are arranged in the folder structure as shown below

![image showing package directory structure]('dir1.png')
![image showing package directory structure]('dir2.png')

**Note** : your package should have a setup.py file, setup.cfg file, README.md file, and license.txt
as shown in the image above
**Note** : the name of your package name must be **_unique_**
**Note** : the folder containing your python modules should have a __init__.py file
**note** your setup.py and setup.cfg files should look like this

![setup.py image]('setupCFG.png')
![setup.cfg image]('setupPY.png')


## Pypi accounts

You will need to create create an account on [test-pypi](https://test.pypi.org/) and [pypi](https://pypi.org/)
remember to keep your passwords safe
You will need them moving forward

* open your teminal
* change directory to the root folder of your package (folder containing setup.py)
* run `python setup.py sdist`
* run `pip install twine` 

## Upload to test-pypi site

* run `twine upload --repository-url https://test.pypi.org/legacy/ dist/*`
	* this will prompt you for your testpypi username and password
* after your file has been successfully uploaded you can login to the [test-pypi](https://test.pypi.org/) 
site to confirm that your package was uploaded successfully
* run `pip install --index-url https://test.pypi.org/simple/ distributions` to install the test package


## Upload to main pypi site
while still in your package root dir
* run `twine upload dist/*`
	* this will prompt you for your pypi username and password
* after your file has been successfully uploaded you can login to the [pypi](https://pypi.org/) 
site to confirm that your package was uploaded successfully
* run `pip install your-package-name` to install the test package

### Contratulations your package is live and anybody can use it by running `pip install your-package-name` on their machine


<marque>Made with :heart: by JeremAIh</marque>