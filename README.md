# Wave-Phenomena
## Simulating Waves
In this project, I simulate waves accroding to the classic wave equation. Because simulating PDE's across the time domain can be so computationally expensive, I use the parallelized computing capabilities of my own personal GPU and torch's CUDA support. Some things to note:
* The value of a wave function u may be calculated according to u at a previous time
* The time step calculation of u may be parallelized across spatial coordinates x and y, i.e. use u(x,y) at all x and y to calculate u(x,y) at t + dt
* The calculation of u may not be parallelized across time, meaning we must know u(t) to predict u(t+dt)
