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
In general, this data is available at four measurement heights: 25m, 46m, 72m, and 97m a.g.l. (acc. to measuring mast bottom).
We decided not to use the measurements taken at 25m, as they could be affected by the trees in the direction 
of the inflow. Unfortunately, measurements at the height of 97m have been unavailable for a certain period, 
so they cannot be used for deriving stability information.

.. math:: R_B = \frac{ \frac{g}{T_v} \Delta \Theta \Delta z}{(\Delta V)^2}

with 

- :math:`g` being the gravitational acceleration

- :math:`T_v` being the absolute virtual temperature (= mean value of virtual temperatures at 46m and 72m)

- :math:`\Delta \Theta` being the virtual potential temperature difference between 46m and 72m

- :math:`\Delta z` being the height difference between 46m and 72m

- :math:`\Delta V` being the change in horizontal wind speed between 46m and 72m

The classification into stability classes is based on the proposed limit values by Vanderwende and Lundquist (2012) 
[https://iopscience.iop.org/article/10.1088/1748-9326/7/3/034035/meta].
The stratification is assumed to be unstable if :math:`R_B<-0.17` and stable as :math:`R_B>0.06`.

Inflow data
-----------

After applying the data filtering described above, the various datasets are analyzed (see following table). 
For each dataset the number of 10-minute periods is calculated and a power-law curve is fitted to the data. 
Furthermore, the mean wind direction at an altitude of 768.8m (approx. hub height) is calculated. 

.. csv-table::
   :header: "LAI", "Atmospheric stability", "Number of 10-minute periods", "Power-law curve", "Mean wind direction at 768.8m a.s.l."

   "high", "unstable", "13", "v = 1.642 * (h-468.8)^0.227", "292.83"
   "",     "neutral", "80", "v = 1.033 * (h-468.8)^0.323", "292.84"
   "",     "stable", "34", "v = 0.105 * (h-468.8)^0.715", "292.71"
   "",     "all", "127", "v = 0.587 * (h-468.8)^0.418", "292.80"
   "low",  "unstable", "3", "v = 0.896 * (h-468.8)^0.341", "290.44"
   "",     "neutral", "33", "v = 0.423 * (h-468.8)^0.479", "292.14"
   "",     "stable", "37", "v = 0.160 * (h-468.8)^0.637", "292.89"
   "",     "all", "73", "v = 0.267 * (h-468.8)^0.553", "292.45"

For each data set, there is a separate file containing the inflow data from the lidar and a corresponding 
plot showing the profiles and the power-law fit. The file name indicates which LAI and stability class are included.

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
     - height above sea level [m]
   * - 3
     - wind_speed
     - wind speed [m/s]
   * - 4
     - wind_direction
     - wind from direction [deg]
   * - 5
     - stability_class
     - atmospheric stability based on the Bulk Richardson number

       option "all" includes all stability classes

In addition, we are providing the complete lidar data for the relevant time periods. 
This might be of interest for simulations that also use data from layers higher than 
400 meters (acc. to the lidar system in the valley, corresponding 868m a.s.l). 
There is a separate file for high and low LAI, each listing all timestamps along with 
their respective stability classes (all_timestamps_with_stability_classes_low_LAI.csv, 
all_timestamps_with_stability_classes_high_LAI.csv). This information can be used to 
identify the time periods of interest. The lidar data is available on a daily basis in a 
standardized data format (see https://zenodo.org/records/2478051). The file name indicates 
the corresponding day. 