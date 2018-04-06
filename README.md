## Udacity - Self Driving Car Nanodegree (Term 2) - Unscented Kalman Filter
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Background
---
In this project, my goal is to build an unscented kalman filter in C++ that will work with the provided radar and lidar dataset to estimate the correct position of a vehicle in a simulation.

Overview of Repository
---
This repository contains the following source files that I have forked from the [main repository](https://github.com/udacity/CarND-Unscented-Kalman-Filter-Project) and subsequently modified for the extended Kalman filter project:

1.  [ukf.cpp](https://github.com/MartinKan/CarND-Unscented-Kalman-Filter-Project/blob/master/src/ukf.cpp)
2.  [ukf.h](https://github.com/MartinKan/CarND-Unscented-Kalman-Filter-Project/blob/master/src/ukf.h)
3.  [tools.cpp](https://github.com/MartinKan/CarND-Unscented-Kalman-Filter-Project/blob/master/src/tools.cpp)

The FusionEKF class initializes the Kalman filter and the variables that are used by the filter.  It calls functions in the Kalman filter that implement the prediction step or update step.  Depending on the type of sensor information it received, it will either call the standard Kalman filter update step (lidar) or the extended Kalman filter update step (radar).  

The ukf class initializes the Unscented Kalman filter and the variables that are used by the filter.  It implements the functions for the prediction step as well as the update step (lidar and radar update steps are implemented in separate functions). When the ukf class is called for the first time by main, it will try to initialize the object's location (contained inside the state vector x) with the sensor measurement.

The tool class is a helper class that implements functions to calculate the root mean squared error.

To run the code, first compile the code in the build directory by running the following command:

	cmake .. && make

Then run the code by executing the following command:

	./UnscentedKF
