# ARPAoCALC

**ARPAoCALC** is a Python library written for ARPA calculations and computing **CPA** (Closest Point of Approach) & **TCPA** (Time to Closest Point of Approach) between two objects on the Earth.

* Longitude and latitude are in decimal degrees
* Object speed is expressed in knots
* Bearings and angles are expressed in degrees
* CPA result is expressed in nautical miles
* TCPA result is expressed in minutes

Use : 

```python
#------------------EXAMPLE n°1-------------------------------------
#Object A : Position (39.2°,2°) - Speed : 12 knots - Heading : 090°
#Object B : Position (39.4°,2.7°) - Speed : 20 knots - Heading : 190°


from arpaocalc import Ship, ARPA_calculations

objectA = Ship((39,2),12,80)
objectB = Ship((39.4,2.7),20,190)
results = ARPA_calculations(objectA, objectB)
print results

{'cpa': 12.867, 'tcpa': 86.67606616880957}

#------------------EXAMPLE n°2-------------------------------------
#Object A : Position (39.2°,2°) - Speed : 12 knots - Heading : 090°
#Object B : Position (39.4°,2.7°) - Speed : 20 knots - Heading : 190°


from arpaocalc import Ship, ARPA_calculations

objectA = Ship((39,2),12,80)
objectB = Ship((39.4,2.7),20,190)
results = ARPA_calculations(objectA, objectB,m=True, posAatcpa = True, posBatcpa= True)
print results

{'url': 'http://maps.google.com/maps/api/staticmap?size=600x600&maptype=hybrid&markers=color:green%7Clabel:A%7C39,2&markers=color:red%7Clabel:B%7C39.4,2.7&markers=color:green%7Clabel:1%7C39.0495647,2.3661337&markers=color:red%7Clabel:1%7C38.9260519,2.5925903&path=color:green|weight:5|39,2|39.0344323,2.2533951&path=color:red|weight:5|39.4,2.7|39.0719281,2.6254936&sensor=false', 'cpa': 12.867, 'tcpa': 86.67606616880957}

```

Options : 

- m : Display results on a map
- posAatcpa : Display the position of the first object at CPA
- posBatcpa : Display the position of the second object at CPA

![Static Map](https://github.com/nawre/arpaocalc/blob/master/staticmap.png?raw=true)
