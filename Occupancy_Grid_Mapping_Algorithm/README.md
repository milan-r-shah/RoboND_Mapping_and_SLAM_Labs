In this code, a robot equipped with eight sonar rangefinder sensors circulates in an environment to map it. This robot is provided with its exact poses at each timestamp. The code structure is as follows:

#### Data Files
1. ```measurement.txt```: The measurements from the sonar rangefinder sensors attached to the robot at each time stamp recorded over a period of 413 seconds. (timestamp, measurement 1:8).
2. ```poses.txt```: The exact robot poses at each timestamp recorded over a period of 413 seconds. (timestamp, x, y, ϴ).

#### Global Functions
1. ```inverseSensorModel()```
2. ```occupancyGridMapping()```

#### Main Function
1. ```File Scan```: Scanning both the measurement and poses files to retrieve the values. At each time stamp, the values are passed to the occupancy grid mapping function.
2. ```Display Map```: After processing all the measurements and poses, the map is displayed.

#### Summary of notations for the sonar rangefinder inverse sensor model:

- ```m```<sub>```i```</sub> : Map at instant i or current cell that is being processed
- ```x```<sub>```i```</sub>, ```y```<sub>```i```</sub> : Center of mass of the current cell mi
- ```r``` : Range of the center of mass computed with respect to robot pose and center of mass
- ```k``` : The sonar rangefinder cone that best aligns with the cell being considered computed with respect to the robot pose (x,y,\thetaθ), center of mass (xi,yi), and sensor angle.
- ```β``` : Opening angle of the conical region formed out of the measurement beams.
- ```α``` : Width of obstacles which is almost equal to the size of a cell. Please not that alpha is not the width of the conical region as the video mention but instead it's the width of a cell.


### How to use this Program
Before running this program, make sure you have **Python 2.7** as well as **matplotlib** library installed in your machine.

#### Compiling the Program
```sh
$ mkdir Images
$ g++ main.cpp -o app -std=c++11 -I/usr/include/python2.7 -lpython2.7
```

#### Running the Program
```sh
$ ./app
```
Wait for the program to generate the image.

The output image would be generated in ```Images``` directory.