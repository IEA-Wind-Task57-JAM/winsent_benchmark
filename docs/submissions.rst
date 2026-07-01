Submissions
===========

Phase I
-------

For submission, please use the template files provided on Zenodo.
The simulation results are to be submitted at the :ref:`MMNW position <coordinates>` at defined sensor heights.

Variables to submit
^^^^^^^^^^^^^^^^^^^

- Velocity components (u, v, w) in lat, lon system
- horizontal wind speed and direction
- TKE

optional:

- potential temperature
- pressure 
- humidity 
- precipitation 


The results are to be submitted at the following **heights** in m a.g.l.:

- velocity, TKE: 11, 25, 35, 46, 47, 59, 74, 87, 98
- temperature, pressure, humidity:  3, 5, 25, 46, 73, 96, 97
- precipitation: 2

Please interpolate to the defined location and heights if they are not directly represented in your simulation.

**Format:**
One NetCDF file for each case (heigh/low LAI and stratification) with mean/statistical values
For transient simulations, e.g. NWP/WRF, tool chains, one file for each of the three days.
Where one file includes all defined timesteps of the specific day.

Simulation setup (meta data)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
We need some information about your simulation type and setup to classify and compare the results properly.
Requested parameters:

-   domain extent (size, shape and position), for all domains in case of nesting
-   3D grid resolution
-   Which geodata (data source resolution or which provided dataset) is used including LAI values
-   temporal resolution (and specify if results are being submitted as averages or instantaneous values)
-   model type and simulation software, ideally with references
    - type: NWP global, NWP local, CFD, potential flow model
    - software: e.g. WRF, OpenFOAM, Flower, WAsP 
    - model: (including turbulence): e.g. URANS k-epsilon, RSM, LES, DES; incompressible, anelastic approximation; ideally with reference 
-   other model setup choices (e.g. PBL scheme in WRF)
-   any assumed constants used to run the model (e.g. roughness, viscosity)
-   boundary conditions (types, e.g. Dirichlet, Neumann, coupling, Davies relaxation, and constants of all boundaries)
-   turbulence model: how your model calculates TKE, calculation method, direct output or time average, ideally with references
-   interpolation methods (to result points and boundaries)

**Format:**
Please fill out the setup_template text file, provided on Zenodo, with all the information you have and can share.
You may change, add or remove specific points so that it fits to your setup.

Upload
^^^^^^
tbd

.. Instructions
.. ------------

.. Submission instructions will be posted by phase.

.. Submission format
.. -----------------

.. To be updated with templates, variable naming conventions, and upload locations.
