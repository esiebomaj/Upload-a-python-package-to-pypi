<img src='https://miro.medium.com/max/2632/1*8Zh-mzLnVMDsbvXdKsU4lw.png' height='200px'>

# Minimalist guide to uploading a python package to pypi
Lets say you have a code-base that you feel would be helpful to the developer community 
you can package it and upload to pypi so that other develeopers can install it using pip and use 
<br>
this file shows exactly how to do this

## Directory structure

ensure your python packages and modules are arranged in the folder structure as shown below

![image showing package directory structure](https://user-images.githubusercontent.com/57163971/88475582-4d8e4680-cf29-11ea-9d69-f6d9fd966f1e.png)
![image showing package directory structure](https://user-images.githubusercontent.com/57163971/88475583-4e26dd00-cf29-11ea-90f5-2e3ede3bb4f7.png)

**Note** : your package should have a setup.py file, setup.cfg file, README.md file, and license.txt
as shown in the image above
<br>
**Note** : the name of your package name must be **_unique_**
<br>
**Note** : the folder containing your python modules should have a __init__.py file
<br>
**note** your setup.py and setup.cfg files should look like this

![setup.py image](https://user-images.githubusercontent.com/57163971/88475580-4c5d1980-cf29-11ea-8d4e-9ef3ade50975.png)
<br>
setup.cfg
<br>
<br>
![setup.cfg image](https://user-images.githubusercontent.com/57163971/88475581-4d8e4680-cf29-11ea-83e8-de681853ff7f.png)
<br>
setup.py
<br>


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
* run `pip install --index-url https://test.pypi.org/simple/ your_package_name` to install the test package


## Upload to main pypi site
while still in your package root dir
* run `twine upload dist/*`
	* this will prompt you for your pypi username and password
* after your file has been successfully uploaded you can login to the [pypi](https://pypi.org/) 
site to confirm that your package was uploaded successfully
* run `pip install your-package-name` to install the test package

### Contratulations :champagne:  :fireworks: :champagne: your package is live and anybody can use it by running `pip install your-package-name` on their machine

## contributing
I will be happy to accept any contributions you might have to this guide
do well to open an issue or even a PR 

<br>
<br>
<br>

**_Made with :heart: by JeremAIh_**
