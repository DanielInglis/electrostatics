# Electrostatics Solver

Third year Theoretical Physics group project to solve electrostatics problems.


### Folder Structure

##### bin
The bin directory is where the output executables are stored. It is listed in .gitignore so that it is not included in the git repository. (You generate it along with the compiled executables by running make.)

##### build
Like the bin directory, the build directory is not included in the git repository but is automatically generated by running make. It contains the compiled (but not linked) .o object files.

##### include
All header files should be in the include folder. 

##### src
The src folder is for all c++ source files. These should all have the file extension .cpp (so that that make can find them).

##### test
Contains a src folder which contains the tests for the program. Running make testAll also generates a build and bin directory here, with the test executable in the test/bin directory.

##### scripts
Contains useful scripts eg to plot data with gnuplot.



### Compiling and Running

To compile and run the program you must have g++, make and eigen installed. Eigen is the library used to provide matrices. To compile the unit tests you must install the Google Test framework. The installation commands below should work on Debian based linux distributions such as Ubuntu, Mint etc.

##### Installing g++ and make
```bash
sudo apt-get install g++ make
```

##### Installing Eigen
```bash
sudo apt-get install libeigen3-dev
```

##### Installing Google Test
```
sudo apt-get install cmake libgtest-dev
cd /usr/src/gtest
sudo cmake CMakeLists.txt
sudo make
sudo cp *.a /usr/lib
```

##### Compiling and running the tests
With google test installed as directed above the tests can be compiled by running
```bash
make testAll
```
in the project root directory. This also compiles any other source files required for running the tests.
The tests can then be executed by running
```bash
test/bin/testAll
```

##### Compiling
In the root directory of the project run make. This will generate the object files in the build directory, and the output executable in the bin directory
```bash
make
```

##### Running the Program
The main funtion of the program currently solves the second problem in the project description document and saves the output to a file called "electrostatics.out". To run the porgram and plot the output do the following:
```bash
cd bin
./electrostatics
gnuplot ../scripts/plot.plt
```

This will generate the plot as an eps file called plot that can then be opened with a program like gv. You will need gnuplot installed to generate the plot.
