# Wave-Phenomena
## Simulating the Classic Wave Equation
In this project, I simulate dimensional waves as a function of 2 dimensional coordinates according to the classic wave equation. Because simulating partial differential equations (PDE)'s across multiple dimensions can be so computationally expensive, I use the parallelized computing capabilities of my own personal GPU and torch's CUDA support. Some things to note:
* The value of a wave function u may be calculated according to u at a previous time
* The time step calculation of u may be parallelized across spatial coordinates x and y, i.e. use u(x,y) at all x and y to calculate u(x,y) at t + dt
* The calculation of u may not be parallelized across time, meaning we must know u(t) to predict u(t+dt)
Furthermore, this framework supports the customization of wave sources:
* Multiple wave sources may be passed as function arguments eg two sine waves of varying frequencies

## Code Structure
The code is structured in the following files:
* 'wavetorch.py' - module consisting of functions to simulate wave phenomena
* 'Generate Data.ipynb' - Jupyter Notebook file showcasing how wavetorch.py can be used to generate a 2d video of wave phenomena, and the wave signal at different locations
* 'Signal Processing.ipynb' - Jupyter Notebook file showcasing how generated signals may be spectrally decomposed

The raw tensor file generated in this project has been ommited from the repository, due to its enourmous file size.

## Images

Wave Simulation at specific frame
![image](https://user-images.githubusercontent.com/16550043/231630331-3ed1d167-52bb-420a-b51c-b1338fc7af14.png)

Spectrograms of wave at different locations:
![image](https://user-images.githubusercontent.com/16550043/231630458-17f9f537-a24a-4f34-bbad-80b1d7e8311c.png)

![image](https://user-images.githubusercontent.com/16550043/231630427-5962ce73-c9e8-421e-b1cb-537d448355ca.png)



## Wave Simulation Video
Link to video of simulation of 2d waves over time:

https://www.youtube.com/watch?v=UdjUCrevOd0

## Special Thanks
I referenced Hans Petter Langtangen's works to understand computational physics as applied to partial differential equations. Please see the following link for more details:

http://hplgit.github.io/wavebc/doc/pub/._wavebc_cyborg004.html#sec:app:numerical
