Benchmark phase I
=================

Data processing
---------------

Since we are only considering the inflow in the first phase of the benchmark and are not including 
the wind turbines themselves, the period under review is June 2025 to March 2026.

For this period, we take the inflow data from the lidar system in the valley and filter for wind 
directions between 280° and 305° at all heights between 100m and 400m a.g.l.. This gives us 579 10-minute periods. 

Next, these time periods are assigned to a high or low LAI depending on the date (see above). 

Wind speed distributions, which are based on the wind speed measured at 300m a.g.l. (acc. to the lidar system) 
in the valley (~hub height of the turbines on the plateau), are analyzed and the bin with the largest amount 
of data is chosen. After the filtering for wind speeds between 5.5m/s and 7.5m/s 127 10-minute periods remain 
for high LAI and 73 10-minute periods for low LAI.

For classification into stability classes, the Bulk Richardson number is used (see formula below). 
Temperature and wind speed measurements from the northwestern measuring mast are used to calculate the metric. 
In general, this data is available at four measurement heights: 25m, 46m, 73m, and 97m a.g.l. (acc. to measuring mast bottom).
We decided not to use the measurements taken at 25m, as they could be affected by the trees in the direction 
of the inflow. Unfortunately, measurements at the height of 97m have been unavailable for a certain period, 
so they cannot be used for deriving stability information.

.. math:: R_B = \frac{ \frac{g}{T_v} \Delta \Theta \Delta z}{(\Delta V)^2}

with 

- :math:`g` being the gravitational acceleration

- :math:`T_v` being the absolute virtual temperature (= mean value of virtual temperatures at 46m and 73m)

- :math:`\Delta \Theta` being the virtual potential temperature difference between 46m and 73m

- :math:`\Delta z` being the height difference between 46m and 73m

- :math:`\Delta V` being the change in horizontal wind speed between 46m and 73m

The classification into stability classes is based on the proposed limit values by Vanderwende and Lundquist (2012) 
[https://iopscience.iop.org/article/10.1088/1748-9326/7/3/034035/meta].
The stratification is assumed to be unstable if :math:`R_B<-0.17` and stable as :math:`R_B>0.06`.

Inflow data
-----------

After applying the data filtering described above, the various datasets are analyzed (see following table). 
For each dataset the number of 10-minute periods is calculated and a power-law curve is fitted to the data. 
Furthermore, the mean wind direction at an altitude of 768.80m (elevation above NHN, approx. hub height) is calculated. 

.. csv-table::
   :header: "LAI", "Atmospheric stability", "Number of 10-minute periods", "Power-law curve", "Mean wind direction at 768.80m NHN"

   "high", "unstable", "13", "v = 1.642 * (h-468.8)^0.227", "292.83"
   "",     "neutral", "80", "v = 1.033 * (h-468.8)^0.323", "292.84"
   "",     "stable", "34", "v = 0.105 * (h-468.8)^0.715", "292.71"
   "",     "all", "127", "v = 0.587 * (h-468.8)^0.418", "292.80"
   "low",  "unstable", "3", "v = 0.896 * (h-468.8)^0.341", "290.44"
   "",     "neutral", "33", "v = 0.423 * (h-468.8)^0.479", "292.14"
   "",     "stable", "37", "v = 0.160 * (h-468.8)^0.637", "292.89"
   "",     "all", "73", "v = 0.267 * (h-468.8)^0.553", "292.45"

The folder structure of the inflow data is shown in the following figure. 

.. image:: images/input_files_phaseI.png

For each selected 10-minute period, there are two files: 

- one containing the inflow data from the lidar for the selected height range (100m - 400m a.g.l. :math:`\approx` 569m - 856m NHN) 

  ("...lidar_data.csv")

- one containing the inflow data from the lidar for all available heights 

  ("...lidar_data_all_heights.csv") 

  This might be of interest for simulations that also use data from layers higher than 400 meters (acc. to the lidar system in the valley). 

The CSV files contain the following information:

.. list-table:: 
   :header-rows: 1

   * - column
     - column name
     - description
   * - 1
     - time
     - timestamp in UTC

       the value indicates the start of the 10-minute period 

       e.g. a value of 15:20:00 includes data from 15:20:00 till 15:29:59
   * - 2
     - height
     - height [m NHN]
   * - 3
     - wind_speed
     - wind speed [m/s]
   * - 4
     - wind_direction
     - wind from direction [deg]

Additionally, each data set includes a file listing all corresponding 10-minute periods along with 
their respective stability classes ("all_timestamps_with_stability_classes_low_LAI.csv" and 
"all_timestamps_with_stability_classes_high_LAI.csv"), 
as well as a plot showing the corresponding profiles and the power-law fit (see example below). 
The file name indicates the associated LAI category and stability class.

.. image:: images/profiles_high_LAI_stable.png

Optional: Simulation using numerical weather prediction (NWP) data
------------------------------------------------------------------

Three specific days are selected for WRF simulations (or similar models). 
The selection is based on identifying days with the largest possible number of 10-minute intervals 
that fulfill the wind direction and wind speed criteria described above.

The selected days are:
- 8.7.25 (high LAI, predominantly neutral stratification during the analyzed 10-minute intervals)
- 17.11.25 (low LAI, predominantly neutral stratification during the analyzed 10-minute intervals)
- 14.3.26 (low LAI, stable + neutral stratification during the analyzed 10-minute intervals)

