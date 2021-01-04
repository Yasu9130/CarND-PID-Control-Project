# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Overview
This project shows PID controller for self-driving car.
By using simulator, you can check if the car is running correctly.


## PID Controller
* P(= Proportional)
P is proportional term. By controlling only P to decrease CTE(Cross Track Error), the trajectory will oscillate around the reference line(= overshoot). If the parameter tau_p is big, oscillation will be fast.

* D(= Differential)
D is differential term. To solve the above oscillation, we focus on not only CTE itself but also the difference of CTE. The trajectory will be stable around the reference line. If the parameter tau_d is big, the change of steering will be small.

* I(= Integral)
I is integral term. Systematic bias is in the real world. It will cause a big CTE. To correct bias, we also focus on the sum of CTE. If the parameter tau_i is big, the correction will be large.

## To realize self-driving
What I did for complete this project is tuning paramters, tau_p, tau_d and tau_i.
Mainly I focused on tau_p and tau_d.
By trying to run through the full course, final parameters are as follows.
* tau_p = 0.5
* tau_d = 13.0
* tau_i = 0.002

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1(mac, linux), 3.81(Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 
