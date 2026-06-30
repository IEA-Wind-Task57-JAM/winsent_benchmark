.. Description of the benchmark
.. ========

.. The WINSENT benchmark is designed as a JAM community benchmark campaign around a complex-terrain research site.
.. Basic campaign context
.. ----------------------
.. - The WINSENT test site is in complex terrain near the Albtrauf on the Swabian Alb.
.. - The site includes a research wind turbine (ZSW 750.54) and coordinated meteorological/LiDAR measurements.
.. - Research wind turbine: 73 m hub height, 50 m rotor diameter, 750 kW rated power.
.. - Field systems include four meteorological masts and multiple LiDAR systems for inflow and wake characterization.
.. - Terrain and land-cover data are intended to support high-resolution modeling workflows.
.. Why this benchmark
.. -------------------
.. Complex terrain introduces strong flow inclination, turbulence, and terrain-driven variability that are difficult to capture sistently across models.
.. This benchmark provides a common test case to evaluate model performance and improve confidence in simulation workflows.
.. Why WINSENT
.. -----------
.. WINSENT combines a research turbine, rich inflow and wake measurements, and an environment where topography and land-surface effects  relevant to model skill.
.. The benchmark is intended to support consistent cross-model comparison in complex terrain, including inflow-focused and turbine-coupled dies.
.. Timeline
.. --------
.. The WINSENT benchmark follows a structured timeline:
.. - **Sep 2025**: Working group formed
.. - **Oct 2025 – May 2026**: Data selection and curation
.. - **Jun 2026 – xxx**: Modelers simulate inflow-only conditions
.. - **xx**: Benchmark leads perform inflow analysis
.. - **xx**: Modelers perform any requested iterations
.. - **xx**: Additional benchmark phases and milestones

Description of the benchmark
============================

Objective
---------
The objective of this benchmark is to validate various numerical flow models that simulate both terrain flow and the flow around 
wind turbines in complex terrain. The WINSENT test site, with its four meteorological measuring masts fully equipped with measurement 
technology and its two research wind turbines, provides the ideal conditions for this. The validation will be conducted for two 
situations of the forested slope in the prevailing wind direction: with and without leaves. The wind turbines became fully operational 
in April 2025. The period covered by the benchmark ranges from June 2025 to March 2026. The benchmark is divided into two phases, 
which are described in the following chapters. 

Phase I
-------
The first phase of the benchmark focusses on the validation of the inflow data. Therefore, the entire time period can be used 
regardless of the availability of the wind turbine data. Situations involving inflow from the prevailing wind direction of 
west-northwest should be considered. The analysis should be conducted separately for the forest's leafy (high leaf area index) 
and leafless (low leaf area index) states in the direction of the inflow. In addition, a distinction is made based on atmospheric 
stability classes. The following list summarizes the setup for phase I. More details can be found in chapter :doc:`phase_I`. 

objective
    - validation of inflow data
conditions
    - wind from west-northwest
    - high and low leaf area index
time period
    - 06/2025 - 03/2026
input data
    - inflow data from the lidar in the valley
    - LAI values
    - information about atmospheric stability
    - locations of the lidar and the structures on the test site
    - terrain data
output data
    - 10-minute mean data at specified locations

Phase II
--------
Content will be added later