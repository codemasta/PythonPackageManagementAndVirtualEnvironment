# Python Package Management And Virtual Environment

pip => Package management    
Virtual environments => projects and dependencies    
Virtualenvwrapper => making venv more convenient  

pip list => list all installed packages and their dependencies  
pip help => help   
pip help list => show help for list  
pip list -o => list outdate package  
pip show PackageName => displays more information or detailed information about a package

pip installs packages in a format called *wheels*

To install multiple packages at once => pip install [requests] [Django] [Keras]   
To uninstall multiple packages at once => pip uninstall [requests] [Django] [Keras] 

Virtual Environments : Isolated context for installing packages.

How to create virtual environment

virtualenv [NameOfEnvironment]  
virtualenv -p python3 rates_py3 => using specific version of python to create the virtualenv

Another kind of virtual environment we have is called :  *venv* which is included i.e comes in-built in python >= 3.3 : venv  while Virtual Env is an library you have to install with pip

python -m venv [NameOfEnvironment]
It is also activated the same way as virtualenv

Requirement File
___
``` 
python -m pip freeze > requirements.txt
```   
or
```
pip freeze > requirements.txt
``` 
Above writes the requirement into a file

To install this requirements on another machine where the code will run do this and remember to check-in this file :  
```
  python -m pip install -r requirements.txt
```
or
```
  pip install -r requirements.txt
```  

Versions and Pip
___
```
python -m pip install flask==0.9   
python -m pip install 'Django<2.0' # mind the quotes
```

##### upgrade to latest version
```
python -m pip install -U flask 
```

VIRTUALENVWRAPPER
___

Virtualenvwrapper : which makes working with virtualenv alot easier.     
1. A user-friendly wrapper around virtualenv
2. Easy creation and activation
3. Bind pprojects to virtualenvs
4. Great with large numbers of projects    

On mac linux => pip install virtualenvwrapper
On windows   => pip install virtualenvwrapper-win  

On windows sample :  
 1. mkvirtualenv [VirtualEnvironmentName] : it's created and activated automatically  
2. workon [VirtualEnvironmentName] : activates and switched to the already created virtual environment.  
3. lsvirtualenv OR workon : list all created virtual environment
4. de-activate : deactivates the currently active virtual environment
5. mkvirtualenv -p 2 [VirtualEnvironmentName] : creates virtual environment with python 2 
6. mkvirtualenv -p 3 [VirtualEnvironmentName] : creates virtual environment with python 2 
7. To work on existing project , do this :  
    workon [NameOfExistingVirtualEnv]   
    setprojectdir "[PathToProjectYouWantToWorkOn]"  
    workon [NameOfExistingVirtualEnv]   # this will redirect the path to the new set project directory
8. rmvirtualenv [VirtualEnvironmentName]
9. mkproject [ProjectName] => automatically create project in the set directory in the system variables eg PROJECT_HOME=C:\Users\Compiler\Project and also the virtual environment with the same name as the project and activates immediately
    
NOTE : if you create a project with *mkproject* switching to the virtualenv via *workon* automatically changes the directory to that project and also activates the virtualenv cos they are tied together.

NOTE :    
  **Installation**  
    - pip  
  **Dependency management**   
     - requirements.txt  
  **Project Isolation**  
     - virtualenv  
     - venv   
  **New projects**  
     - pipenv (hope to combine both pip and virtualenv in a single tool)  
     - poetry  
  


  PIPENV
  ___
 pip install pipenv : to install pipenv  
 
 To install packages :  eg the request package   
     ***pipenv install requests***

After the 1st dependencies download it create 2 files : Pipfile and Pipfile.lock where the Pipfile is more like a requirement file in virtualenv but it has more human readable properties in this case. Pipfile.lock is a computer generated file that stores the exact version of the dependencies and it uses this to make a dependencies tree deterministic. This ensures that when other devs have the same uniform dependencies. When there are new dependencies we can always regenerate a new Project.lock

To run the script with pipenv command : **pipenv run** python webRequest.py    
also you can start a new shell inside the active environment more like activate the environment.     

**pipenv shell** python webRequest.py     
**exit**  : to exit the shell  
**pipenv install --three** : to install all dependencies in the pipfile




