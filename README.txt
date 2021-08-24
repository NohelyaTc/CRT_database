1. The "database_OSRM" folder contains the databases with information on the travel time estimate in OSRM. 

data set 0 = Contains information for the 4 months from January to April 2017 (2987 Emergency medical services). 
data set 1 = Contains information from January 2017. 
data set 2 = Contains information from February 2017.
data set 3 = Contains information from March 2017.
data set 4 = Contains information from April 2017.

No UNIDAD        : It allows to identify the ambulance providing the service. 
DIA              : Number that identifies the ambulance.
MES              : Month in which the emergency service was given.
HORA SALIDA      : The departure time of the ambulance to the incident.
TIEMPO DE VIAJE  : The estimated travel time in minutes, computed by OSRM.
DISTANCIA METROS : Travel time by OSRM, from the point of departure to the place of the incident.
LONGITUD SALIDA  : The longitude of the ambulance when it was dispatched.
LATITUD SALIDA   : The latitude of the ambulance when it was dispatched.
LONGITUD LLEGADA : The longitude of the EMS incident determined by the GPS.
LATITUD LLEGADA  : The latitude of the EMS incident determined by the GPS.
DT               : The time difference of TGPS-TOSRM. (TGPS: GPS time) (TOSRM: OSRM time).
SALIDA           : Output labels DM (Medium Decrement), DP (Small Decrement) and INCREMENT. 
SALIDA2          : Output labels; 3 (Medium Decrement), 2 (Small Decrement) and 1 (INCRMENT). 



-----------------------------------------------------------------------------------------------------

1. The "database_GoogleMaps" folder contains the databases with information on the travel time estimate in Google Mpas. 

data set 0 = Contains information for the 4 months from January to April 2017 (2978 Emergency medical services)

The data is ordered in the same way as for OSRM, in this case the columns:

TIEMPO DE VIAJE  : It is the estimate by Google Maps, from the point of departure to the place of the incident. 
DT               : The time difference of TGPS-TG. (TGPS: GPS time) (TG: Google Maps time).
						
----------------------------------------------------------------------------------------------------
The data used for the Machine Learning algorithm are: 
No UNIDAD, DIA, MES, HORA SALIDA, TIEMPO DE VIAJE, LONGITUD SALIDA, LATITUD SALIDA, LONGITUD LLEGADA, LATITUD LLEGADA, SALIDA. 
