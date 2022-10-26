# The vPython installation guide (by Rodo)


## On Ubuntu Desktop x RaspberryPi

<!-- username: rodo  
password: dand8222 (not real) -->

0. House-keeping

        sudo apt update  
        sudo apt upgrade  

1. Follow this link to enable SSH Server on Raspberry Pi https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-20-04/ . Then, use PuTTy to connect to your RPi. 

2. Install essential packages for your Ubuntu

        sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev openssl pip

3. Note that vPython will overwrite python3.9 if it is available on your machine and should appear as `Python3.9.7+`. Now, check your available Python version and what command to access them  
    
        For example: Mine is `python3` / `python3.8` -> python3.8. So, vPython will not overwrite anything in my case.

4. Download vpython

        git clone https://github.com/rodonguyen/vPython-rodo # OR unzip vPython-rodo.zip (if you already downloaded the zip file)

        cd ./vPython-rodo
        ./configure
        make                  
        sudo make install 

5.  While you're in vPython, to check if vPython produces a trace as we wanted, create a function with quite a unique name, like this:

        >>> def hello_dr_rodo():
        >>>     print('$$$)
        >>> hello_dr_rodo()

    Search for the function name in vpython.txt (the trace) in the current directory. If found, HUGE CONGRATS, it works as planned :)

6. Install necessary packages for Python 3.9 

        python3.9 -m pip install sklearn pytorch pandas scipy numpy torch matplotlib
        sudo reboot -h

    Note: `tensorflow` is not in this list because it caused error on my device (it does not support >python3.8?)

7. Check vPython libraries

        python3.9
        Python 3.9.7+ (heads/main-dirty:f1005f0, Apr 20 2022, 18:02:15)
        [GCC 11.2.0] on linux
        Type "help", "copyright", "credits" or "license" for more information.
        >>> import sklearn, pytorch, pandas, scipy, numpy, torch, matplotlib

<!-- If everything works just fine, no error is prompted. Otherwise, run the install command in step 4 and re-install vPython (./configure, make, sudo make install). -->


8. Remember to remove vpython.txt (this time and everytime after you've finished with it) to clear some room for you RPi

        rm vpython.txt


9. If python3.8 is not installed, do it because we need it to do normal Python stuff.  
Follow instruction in the link and I recommend replace `python3.8.4` with `python3.8.13` because we want the best of 3.8   
        
        https://realpython.com/installing-python/

    Install the same packages in vPython for Python 3.8

        python3.8 -m pip install sklearn pytorch pandas scipy numpy torch matplotlib

10. Celebrate! vPython is ready.

<br>
<br>

# My other notes

Uninstall python. BE CAREFUL. PYTHON IS ESSENTIAL FOR LINUX! 
    https://codeigo.com/python/uninstall-python

Remove folder / file: `rm -rf file_name_or_folder`

Better histogram: https://stackoverflow.com/questions/23246125/how-to-center-labels-in-histogram-plot



<!-- <br>

# Mics notes 
Keywords in /Python/ceval.c
tstate
write_to_file
write_stack
frameobject.h

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
getMicroTime: return 0 -->



