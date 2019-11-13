# Matlab MEDD spike test

## Purpose

The MEDD test is a spike detection test.
Its aim is to detect simple spikes and vertically short burst of spiky points.
MEDD stands for MEDian with a Distance.

## Short description

The test is based on three main steps:
- first the computation of a sliding median with some customizations
- then limits are computed that are at relative 2-dimensional distance d from the median
- finally this limits are also computed for the density profile
There is a spike if both the density profile and the (temperature or salinity) profile are out of limits. If there is no conductivity sensors, then the spikes in temperature are evaluated using a bigger d value.

## Scripts

This is composed of three routines:
 - The main call QTRT_spike_check_medd_main.m that includes the configuration, launches the other routines, and compute final compound spike detection (density + physical parameter)
 - QTRT_spike_check_medd.m that computes the median, call the relative_2D_distance routine and computes unitary spikes suspicions
 - relative_2D_distance.m that computes the limits located at relative 2-dimensional distance d from a curve

## Documentation

See the specification in the doc folder for a more detailed explanation of the algorithms.

## Inputs (in the call of routine QTRT_spike_check_medd_main.m) :
 - PRES: pressure values
 - TEMP: temperature values
 - PSAL: salinity values (should be NaN(size(PRES)) if not available)
 - DENS: density values (should be NaN(size(PRES)) if not available)
 - LAT: latitude of the profiles in degrees

## Outputs:
 - SPIKE_T: array of size(PRES) with a 1 on temperature spikes, It is set to NaN if the computation could not be made
 - SPIKE_S: array of size(PRES) with a 1 on salinity spikes, It is set to NaN if the computation could not be made
