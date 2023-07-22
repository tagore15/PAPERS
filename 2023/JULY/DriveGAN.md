DriveGAN: Towards a Controllable High Quality Neural Simulation
---------------------------------------------------------------
Realistic simulators are critical for training/verifying robotics systems. Scalable way to build simulators is to use maching learning to learn how env behaves in response to an action, directly from data. Here we learn to simulate dynamic env directly in pixel space. by watching unanntoated seq of frames and their associated action. DriveGAN:-
- steering controls
- weather
- location of non-player objects.
Fully differentiable simulator, allows for re-simulation of a given video sequence.

Grand Theft Auto took several years so data-driven simulation is better.   
LidarSim used a catalog of annotated 3D scenes to sample layouts into which reconstructed objects obtained from large number of recorded drives are placed, in quest to acheive diversity.      
Recent work attempted to create neural simulators that learn to simulate the env in response to agent's actions.

$$L_{VAE} = E_{z\sim{q(z|x)}}[log(p(x|z)] + \beta KL(q(z|x)||p(z)) $$
