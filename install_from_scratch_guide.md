# The Full Process of installing vPython (by Rodo)


## On Ubuntu Desktop x RaspberryPi

    username: rodo  
    password: dand8222 (not real)

0. 

    sudo apt update  
    sudo apt upgrade  

1. 
Follow this link to enable SSH Server on RPi
https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-20-04/

Then, use PuTTy to connect to your RPi. 

2. 
Install essential packages for your Ubuntu

    sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev openssl pip

3. 
Check your Python version and what command to access them  
    
    E.g. python / python3 / python3.9 / python3.8 
    Mine is: python3 / python3.9 -> python3.9.7

These commands will be used for vPython afterwards. Note that vPython will overwrite python3.9 and should appear as `Python3.9.7+`


4.
Install necessary packages for Python 3.9 in advance so that after installing vPython, it will inherit those packages (I think...)   

    python3.9 -m pip install scikit-learn matplotlib jupyter pandas scipy seaborn numpy
    sudo reboot -h

Note: `tensorflow` is not in this list because it does not support above python3.8


5. 
Download vpython

    unzip vpython.zip (if applicable) OR git clone https://github.com/rodonguyen/vPython-rodo
    cd ./vPython-rodo (or whatever the dir name)
    ./configure
    make                  
    sudo make install 

6. 
Check vPython

    python3.9
    Python 3.9.7+ (heads/main-dirty:f1005f0, Apr 20 2022, 18:02:15)
    [GCC 11.2.0] on linux
    Type "help", "copyright", "credits" or "license" for more information.
    >>> import sklearn, matplotlib, jupyter, pandas, scipy, seaborn, math, numpy, time

If everything works just fine, no error is prompted. Otherwise, run the install command in step 4 and re-install vPython (./configure, make, sudo make install).

7. 
While you're in vPython, to check if vPython produces a trace as we wanted, create a function with quite a unique name, like this:

    >>> def hello_dr_rodo():
    >>>     print('$$$)
    >>> hello_dr_rodo()

Search for the function name in vpython.txt (the trace) in the current directory. If found, HUGE CONGRATS :)


9. 
If python3.8 is not installed, do it because we need it to do normal Python stuff.  
Follow instruction in the link and Replace python3.8.4 by python3.8.13 because we want the best of 3.8 :)   
    https://realpython.com/installing-python/

Install necessary packages for both Python 3.8

    python3.8 -m pip install scikit-learn matplotlib jupyter pandas tensorflow scipy seaborn

10. 
Celebrate !

11. 
Analyse vPython !


<br>
<br>

# Others

Uninstall a package  

    sudo apt-get clean
    sudo apt-get autoremove --purge
    sudo apt-get remove python3.9
    sudo apt-get autoremove
    sudo reboot -h

Remove folder / file:

    rm -rf file_name_or_folder

better histogram: https://stackoverflow.com/questions/23246125/how-to-center-labels-in-histogram-plot



<br>

# Mics notes 
search for tstate, check functions Gowri mentions
write_to_file
write_stack
frameobject.h?

read resources online about ceval cpython
struct in C
Objects/lnotab_notes.txt
https://swenson.github.io/python-xr/Python/ceval.c.html#line-243
C_TRACE


how to detect data input difference
the stack trace only recorded function calls order
stackframe contains the function’s local variables and the arguments passed to the function by its caller.
look into the CPython stack frame to see how it works and produces differences
put text file far away
try with different dataset, lib, code structure, 
Record everything you observe
getMicroTime: return 0



