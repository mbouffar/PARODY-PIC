# PARODY-PIC
Tracers module of the code PARODY-PIC

Parody-PIC is an extended version of the code Parody-JA that includes a particle-in-cell (PIC) method for the treatment of composition and/or temperature. 

The principle of the method is briefly summarized below:

1) A large number of particles is initially spread across the spherical shell. These particles are also called "tracers". The tracers carry some information:
- their coordinates (r,theta,phi)
- the local value of temperature/composition/any other scalar field at the particle's position

2) Each time step, the tracers are advected with the flow by interpolating the velocity from the grid to the particles. Their coordinates are then updated. A scheme similar to a Runge-Kutta 2nd or 4th order is used in the code. 

3) It is possible to evaluate on the grid the field described by the particles. A weighted averaged is performed around each grid node using the nearby particles. 

The particles can be purely passive (no retroaction on the buoyancy term) or contribute to the buoyancy. Note that the buoyancy is not computed at the tracers positions but only on the grid.


A more detailed description of the method can be found in Bouffard et al., (2017) doi: 10.1016/j.jcp.2017.06.028 
and in my thesis.

Most of the complexities of the code arouse because of the spherical geometry. A special treatment is required at the poles and near the center of the sphere. For any question regarding the detailed treatment of the PIC method in the sphere, feel free to contact me at the following email address: bouffard.mathieu@gmail.com


Mathieu Bouffard
28/12/2017
