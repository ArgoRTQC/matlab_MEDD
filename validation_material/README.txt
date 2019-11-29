In this directory, you will find ascii files giving the inputs and corresponding outputs of the matlab routine QTRT_spike_check_MEDD_main:
[SPIKE_T,SPIKE_S,BO_T,BO_S,TEMP_med,TEMP_medm,TEMP_medp,PSAL_med,PSAL_medm,PSAL_medp,DENS_med,DENS_medm,DENS_medp] = ...
    QTRT_spike_check_MEDD_main(PRES,TEMP,PSAL,DENS,LAT);

One ascii file contains only one cycle and there is a random subset of {platform; cycle} to perform some validation.

The validation ascci files are space separated values for the following fields (this is the header line of the files):
#PRES TEMP PSAL DENS TEMP_med TEMP_medm TEMP_medp PSAL_med PSAL_medm PSAL_medp DENS_med DENS_medm DENS_medp SPIKE_T SPIKE_S
There is also the corresponding plot to help.

The latitude input is given in the validation file name, for instance, if the file name ends with xxxx_3.4S.txt, 
then LAT=-3.4  and if it ends with www_24.2N.txt, then LAT=24.2.

BO_T and BO_S are not loggued but in the validation subset cases, they are always equal to 0.

