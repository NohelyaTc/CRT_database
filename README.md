# Abstrack

This paper addresses the problem of estimating the response time to a medical emergency, specifically from the Red Cross of Tijuana (RCT), which provides most of the emergency medical services (EMS) in the city of Tijuana, Mexico.
For institutions with low funding, such as the RCT, relying on free or open source mapping systems to estimate travel times is necessary but also error prone because these systems are not tuned for ambulance movements within a city.
Therefore, this work formulates a supervised machine learning problem where the goal is to predict the difference in travel time between the ground truth travel time provided by a GPS and the approximation offered by two mapping systems, Google Maps (GM) and Open Source Routing Machine (OSRM).
To this end, this work develops a new dataset based on the EMS logs of the RCT, considering calls from January 2017 to April 2017.
The posed learning problem is solved under different scenarios, including using an off-the-shelf default configuration of a Random Forest classifier, applying a hyper-parameter optimization process and using an Auto Machine Learning (AutoML) system.
Considering all of the dataset for GM, test accuracy was 69.6\% for the first two learning approaches and 71.6\% using AutoML.
For OSRM, performance was 64.6\%, 65.2\% and 66.4\% for each of the learning approaches.
Results show that it is possible to predict the level by which a mapping system over or under estimates the true travel time of an ambulance.
Finally, the impact of the model is demonstrated by using it to solve the ambulance location problem, with notable
differences in ambulance deployments and percentage of double coverage achieved relative to using the standard mapping system. The results shows that with no correction of the travel time the percentage of double coverage is 83.90\%; on the other hand, the double coverage when using travel time correction reaches 100\%.


## CRT_database

1. The "database_OSRM" folder contains the databases with information on the travel time estimate in OSRM. 

- data set 0 = Contains information for the 4 months from January to April 2017 (2987 Emergency medical services). 

- data set 1 = Contains information from January 2017. 

- data set 2 = Contains information from February 2017.

- data set 3 = Contains information from March 2017.

- data set 4 = Contains information from April 2017.




### The fields of the files are: 

- No UNIDAD        : It allows to identify the ambulance providing the service. 

- DIA              : Number that identifies the ambulance.

- MES              : Month in which the emergency service was given.

- HORA SALIDA      : The departure time of the ambulance to the incident.

- TIEMPO DE VIAJE  : The estimated travel time in minutes, computed by OSRM.

- DISTANCIA METROS : Travel time by OSRM, from the point of departure to the place of the incident.

- LONGITUD SALIDA  : The longitude of the ambulance when it was dispatched.

- LATITUD SALIDA   : The latitude of the ambulance when it was dispatched.

- LONGITUD LLEGADA : The longitude of the EMS incident determined by the GPS.

- LATITUD LLEGADA  : The latitude of the EMS incident determined by the GPS.

- DT               : The time difference of TGPS-TOSRM. (TGPS: GPS time) (TOSRM: OSRM time).

- SALIDA           : Output labels DM (Medium Decrement), DP (Small Decrement) and INCREMENT. 

- SALIDA2          : Output labels; 3 (Medium Decrement), 2 (Small Decrement) and 1 (INCRMENT). 




-----------------------------------------------------------------------------------------------------

2. The "database_GoogleMaps" folder contains the databases with information on the travel time estimate in Google Mpas. 

- data set 0 = Contains information for the 4 months from January to April 2017  (2978 Emergency medical services)

The data is ordered in the same way as for OSRM, in this case the columns:

- TIEMPO DE VIAJE  : It is the estimate by Google Maps, from the point of departure to the place of the incident. 

- DT               : The time difference of TGPS-TG. (TGPS: GPS time) (TG: Google Maps time).
						
----------------------------------------------------------------------------------------------------



The data used for the Machine Learning algorithm are: 

No UNIDAD, DIA, MES, HORA SALIDA, TIEMPO DE VIAJE, LONGITUD SALIDA,LATITUD SALIDA,LONGITUD LLEGADA, LATITUD LLEGADA, SALIDA. 


