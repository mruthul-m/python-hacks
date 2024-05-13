windows 10+
-----------

While you installing some packages using pip, you may get an error called SSLCertVerificationError.
This is normal when you are using company laptops.

There are several answers to solve this problem, 
 
    1. try to install using 
        pip install --trusted-host pypi.org 
                --trusted-host pypi.python.org --trusted-host files.pythonhosted.org <package name> 
     
    Here you need to provide your package name in the specified area. 
 
    But one of the main drawback of this command is you need to use this command for every installation 
    and its very tedious task. 
 
    So there is another simple way to solve this 
 
    2.  first find out your pip configuration paths using this command 
 
        pip config -v list 
 
        then you will get a list of paths where pip.ini (python configuration file) is looking for. 
        so you create a pip.ini file if it is not present there and add this 
         
        [global] 
        trusted-host = pypi.python.org 
                       pypi.org 
                       files.pythonhosted.org 
        
 
        and if you check the configuration of pip, then you can see this , if you successfully completed the  task 

        global.trusted-host='pypi.python.org\npypi.org\nfiles.pythonhosted.org' 

    Then you can install packages as usually does. 

        


        
