# GNSS-R events over a swimming pool

This Matlab application simulates the bistatic scenario for a receiver in the proximities of a swimming pool capturing GPS reflected signals. It shows which reflections are being captured in a given time with multiple options to customize the scenario.

## Description

Using a rinex file with the GNSS ephemeris data, the application calculates the position of the satellites of the constellation at the time of observation. Then, using the position of the receiver, it calculates the specular reflection points for each satellite. As a result, the application shows two plots. A diagram of the antenna position, reflective surface and antenna beam to represent the scenario, and a skyplot with the positions of satellites in view and a bounding polygon showing which reflections are being captured by the receiver.

### Executing program

If running for the first time or after a long period of time, download a recent rinex GPS navigation file and edit the variable rinex_filename to the correct path.

The simulation scenario can be customized editing the start up function (startupFcn):
* Time zone offset: app.timezone_os - hour difference relative to UTC for the time zone to simulate.
* Receiver antenna position: app.rx_lla and app.az0 - Rx antenna position in lat, long and alt and azimuth value for the maximum gain direction (pointing direction).
* Antenna pattern; app.theta_x and app.theta_y - Aperture of the antenna beam in both dimensions [degrees].

Additionally, the reflective surface (pool) dimensions can be modified in the updateplot function with the variables pool_length and pool_width.

After configuration, run the app. The Rx position relative to the pool and time of day are initialized with default values, but can be modified as user inputs and the plots will be regenerated automatically.