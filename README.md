Python implementation for detecting coldfront from xray maps


Installing curvelops requires the following external components:

[FFTW](http://www.fftw.org/download.html) 2.1.5\
[CurveLab](http://curvelet.org/software.html) >= 2.0.2\
[curvelops](https://github.com/PyLops/curvelops)

Download FFTW and CurveLab from the given links into the directory of your choice, and expand it with
```
tar xvf CurveLab-2.1.3.tar.gz
tar xvf fftw-2.1.5.tar.gz
```


### FFTW
Go inside the fftw-2.1.5 directory and run the following one by one. Set --prefix as the target fftw-2.1.5 path where all the FFTW 2.1.5 packages will be installed:
```
./configure --with-pic --prefix=/home/user/opt/fftw-2.1.5 --with-gcc=/usr/bin/gcc
```
```
sudo make
```
```
sudo make install
```

### CurveLab
Go inside the CurveLab directory. In ```makefile.opt``` file, set FFTW_DIR to be the path in which FFTW 2.1.5 is installed. From above example:\
FFTW_DIR = 	/home/user/opt/fftw-2.1.5

Install CurveLab: 
```
make lib
```


### curvelops
Open bashrc to set these required environment variables:
```
nano ~/.bashrc
```
Copy and paste following ```export......``` lines and edit according to your FDCT and FFTW directory.\
FDCT: folder where your CurveLab installation is\
FFTW: folder where your fftw installation is
```
export FDCT="/home/user/opt/CurveLab-2.1.3"
export FFTW="/home/user/opt/fftw-2.1.5"
```
Then restart terminal or run ```source ~/.bashrc```

Install curvelops
```
python3 -m pip install git+https://github.com/PyLops/curvelops@0.21
```

### Getting Started

try [these](https://github.com/PyLops/curvelops/tree/main/examples) sample notebooks. If Jupyter kernal keeps dying, try running them in a seperate conda environment: 
```
conda create -n curve numpy matplotlib scipy 
```

Add your virtual environment to Jupyter lab/notebook:
```
python -m ipykernel install --user --name=curve
```
ref: [Installing the IPython kernel](https://ipython.readthedocs.io/en/stable/install/kernel_install.html#kernels-for-different-environments)

run notebooks by choosing created ```curve``` kernel 


