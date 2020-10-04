**Symcc Tutorial**
===
SymCC is a compiler wrapper which embeds symbolic execution into the program during compilation, and an associated run-time support library.


# Symcc docker image preparation
Local installation failed many times, and I decided to use the docker. I build the docker image in Ubuntu 18.04 with any error, using the following steps:

Clone the symcc as mentioned [here](https://github.com/eurecom-s3/symcc):
```
git clone https://github.com/eurecom-s3/symcc.git
$ git submodule init
$ git submodule update
```

Now, we build a docker image and run it:
```
$ docker build -t symcc .
$ docker run -it --rm symcc
```
As mentioned in symcc README, we should try this simple example (check the symcc README for explanation):
```
ontainer$ cat sample.cpp
(Note that "root" is the input we're looking for.)
container$ sym++ -o sample sample.cpp
container$ echo test | ./sample
...
container$ cat /tmp/output/000008-optimistic
root
```

# Cmake installation
If you are using docker and want to build the examples using `cmake`, you need to install `cmake` manually inside the docker image; otherwise update docker file to include the cmake as a part of symcc.

For manual installation, just download the tar file and extract it. Use docker volume to make in available inside the container. Inside the container, change the current directory to ckame directory inside the docker volute, and set the path to cmake as:
```
export PATH=`pwd`/bin:$PATH
```

# Examples

First create a docker container using symcc image which is locally built earlier.
```
$ mkdir symcc-vol 
$ docker run -v `pwd`/symcc-vol/:/tmp/ -it --rm symcc
```

## Openjpeg

### Prepare build environment
```
$ whereis symcc
$ whereis sym++
$ export CC=/symcc_build/symcc
$ export CXX=/symcc_build/sym++ 
$ export SYMCC_NO_SYMBOLIC_INPUT=1
$ echo $CC
$ echo $CXX
$ echo SYMCC_NO_SYMBOLIC_INPUT
```

### Build Openjpeg
Download or clone the openjpeg [source](https://github.com/uclouvain/openjpeg), and then perform the following steps as mentioned [here](https://github.com/uclouvain/openjpeg/blob/master/INSTALL.md) (add -DBUILD_THIRDPARTY=ON as suggested [here](http://www.s3.eurecom.fr/tools/symbolic_execution/symcc.html)):
```
$ cd openjpeg/
$ cd build
$ cmake .. -DBUILD_THIRDPARTY=ON -DCMAKE_BUILD_TYPE=Release
$ make
```
If something go wrong, the clean the build using `make clean` and re-build. Once the Openjpeg is built with qsymcc, executables will be available in `./build/bin/`. Now, we are ready to start symbolic execution.


### Symbolic execution

Let's prepare the required setup:
1. Unset  SYMCC_NO_SYMBOLIC_INPUT
    ```
    $ unset   export SYMCC_NO_SYMBOLIC_INPUT
    ```
1. Set the input file location
I have a input file as recommended by symcc author [here](http://www.s3.eurecom.fr/tools/symbolic_execution/symcc.html).
    ```
    export SYMCC_INPUT_FILE=/tmp/file1.jp2
    ```
1. Create symcc default output directory
    ```
    mkdir /tmp/output
    ```
1. Run the program for symbolic execution
    ```
    sudo /tmp/openjpeg/build/bin/opj_decompress -i @@ -o /tmp/output/image.pgm
    ```

