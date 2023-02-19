# PIP

MS Windows Python installer already includes PIP, you may have to install it on Linux. Uses the PyPI repository.

-	```pip --version```: See what version of PIP is running

-	```pip3 --version```: See what version of PIP is running

-	```pip help```: Produces summarized list of all available operations

    -	```operation```: Detailed description of chosen operation
  
-	```pip list```: Produces list of currently installed python packages

-	```pip show *package_name*```: Produces detailed list describing specific installed packages 

-	```pip search *anystring*```: Search for desired package in PyPI

-	```pip install```:

    -	```package_name```: Installs latest version of package
    -	```package_name==package_version```: Installs desired version of package
    -	```--user package_name```: Install package only in your users directory
    -	```-U package_name```: Update package

-	```pip uninstall *package_name*```: Uninstall package
