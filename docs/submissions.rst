Submissions
===========

Phase I
-------

For submission, please use the template files provided on Zenodo.  
The simulation results are to be submitted at the :ref:`MMNW position <coordinates>` at defined sensor heights.

If you are not able to simulate all cases (high/low LAI and atmospheric stability), please submit at least results for 
both LAI and neutral stability.

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


The variables are to be submitted at the following **heights** in m a.g.l.:

- velocity, TKE: 11, 25, 35, 46, 47, 59, 74, 87, 98
- temperature, pressure, humidity:  3, 5, 25, 46, 73, 96, 97
- precipitation: 2

Please interpolate to the defined location and heights if they are not directly represented in your simulation.

**Time resolution:**

- One representative value for each of the six cases (high/low LAI and stratification), see :ref:`inflow-data`.
- For weather based transient simulations 10 min steps or your full time resolution over the whole day, see :ref:`nwpdays`.

**Format:**

- One NetCDF file for each case. Naming: *WINSENTbench_PhaseI_<name>_<institution>_LAI<h|l>_STRAT<u|n|s>.nc*, example: *WINSENTbench_PhaseI_Example_EU_LAIl_STRATn.nc*, for the low (l) LAI, neutral (n) case, if your name is "Example" from "Example University (EU)".
- For transient simulations, one file for each of the three days, which includes all defined timesteps of the specific day.
  Naming: *WINSENTbench_PhaseI_<name>_<institution>_<date>.nc*, example: *WINSENTbench_PhaseI_Example_EU_20260314.nc* 

Simulation setup (meta data)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
We need some information about your simulation type and setup to classify and compare the results properly.
Requested parameters:

-   Names of Participants with affiliation
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
Please fill out the template_phase1_setup.md Markdown text file, provided on Zenodo (see  submission_phase1_templates.zip), with all the information you have and can share.
You may change, add or remove specific points so that it fits to your setup.
Naming: same as for the variables but different extension (*.md*).

Upload
^^^^^^
A file share upload link will be sent via E-Mail to all participants.
Please upload your files for Phase I in a ZIP archive, named like described for the nc file.

.. Instructions
.. ------------

.. Submission instructions will be posted by phase.

.. Submission format
.. -----------------

.. To be updated with templates, variable naming conventions, and upload locations.
