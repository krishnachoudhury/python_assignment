Create an API end point for looking up postcode info. The output should return
the coordinates and any associated information.

* Use the file postcodes.csv in the data directory for postcode lookup.

* The endpoint URL you need to create 
```
http://<server ip address>/geocode?postcode=<postcode>
e.g 
http://<server ip address>/geocode?postcode=SE1 2ES
```

The API should output postcode info in JSON format as below

```
{'Altitude': '10',
 'Built up area': 'Greater London',
 'Built up sub-division': 'Southwark',
 'Constituency': 'Bermondsey and Old Southwark',
 'Country': 'England',
 'County': 'Greater London',
 'CountyCode': 'E11000009',
 'District': 'Southwark',
 'DistrictCode': ' E09000028',
 'Easting': '532277',
 'GridRef': 'TQ322800',
 'Households': '',
 'In Use?': 'Yes',
 'Introduced': '1994-12-01',
 'Latitude': '51.504038',
 'Longitude': '-0.095542',
 'Lower layer super output area': 'Southwark 002B',
 'NationalPark': '',
 'Northing': '180064',
 'Parish': '',
 'Population': '',
 'Postcode': 'SE1 0AB',
 'Region': 'London',
 'Rural/urban': 'Urban major conurbation',
 'Terminated': '',
 'Ward': 'Cathedrals',
 'WardCode': 'E05000536'}
 ```
 


* On every 10th request, along with the results the API should return previous
results too in the below format(response from 10th request plus response sent
for the last 9 requests).

Here first element of the list is current result and second element is a list
containing previoous 9 results.

Previous results should appear in the list in the order they were called.

```
[{'Altitude': '9',
  'Built up area': 'Greater London',
  'Built up sub-division': 'Southwark',
  'Constituency': 'Bermondsey and Old Southwark',
  'Country': 'England',
  'County': 'Greater London',
  'CountyCode': 'E11000009',
  'District': 'Southwark',
  'DistrictCode': ' E09000028',
  'Easting': '532060',
  'GridRef': 'TQ320797',
  'Households': '69',
  'In Use?': 'Yes',
  'Introduced': '2007-01-01',
  'Latitude': '51.501249',
  'Longitude': '-0.098785',
  'Lower layer super output area': 'Southwark 002A',
  'NationalPark': '',
  'Northing': '179748',
  'Parish': '',
  'Population': '130',
  'Postcode': 'SE1 0BQ',
  'Region': 'London',
  'Rural/urban': 'Urban major conurbation',
  'Terminated': '',
  'Ward': 'Cathedrals',
  'WardCode': 'E05000536'},
 [{'Altitude': '7',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531896',
   'GridRef': 'TQ318798',
   'Households': '6',
   'In Use?': 'Yes',
   'Introduced': '2007-08-01',
   'Latitude': '51.502474',
   'Longitude': '-0.101097',
   'Lower layer super output area': 'Southwark 002A',
   'NationalPark': '',
   'Northing': '179880',
   'Parish': '',
   'Population': '12',
   'Postcode': 'SE1 0BD',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '7',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531916',
   'GridRef': 'TQ319797',
   'Households': '',
   'In Use?': 'Yes',
   'Introduced': '1980-01-01',
   'Latitude': '51.501741',
   'Longitude': '-0.10084',
   'Lower layer super output area': 'Southwark 034D',
   'NationalPark': '',
   'Northing': '179799',
   'Parish': '',
   'Population': '',
   'Postcode': 'SE1 0BE',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '7',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531896',
   'GridRef': 'TQ318798',
   'Households': '18',
   'In Use?': 'Yes',
   'Introduced': '2006-11-01',
   'Latitude': '51.502474',
   'Longitude': '-0.101097',
   'Lower layer super output area': 'Southwark 002A',
   'NationalPark': '',
   'Northing': '179880',
   'Parish': '',
   'Population': '35',
   'Postcode': 'SE1 0BF',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '7',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531900',
   'GridRef': 'TQ319798',
   'Households': '',
   'In Use?': 'No',
   'Introduced': '1985-04-01',
   'Latitude': '51.501754',
   'Longitude': '-0.10107',
   'Lower layer super output area': 'Southwark 034D',
   'NationalPark': '',
   'Northing': '179800',
   'Parish': '',
   'Population': '',
   'Postcode': 'SE1 0BG',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '1996-06-01',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '11',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531794',
   'GridRef': 'TQ317798',
   'Households': '55',
   'In Use?': 'Yes',
   'Introduced': '1980-01-01',
   'Latitude': '51.502282',
   'Longitude': '-0.102575',
   'Lower layer super output area': 'Southwark 034D',
   'NationalPark': '',
   'Northing': '179856',
   'Parish': '',
   'Population': '118',
   'Postcode': 'SE1 0BH',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '10',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531773',
   'GridRef': 'TQ317798',
   'Households': '3',
   'In Use?': 'Yes',
   'Introduced': '1980-01-01',
   'Latitude': '51.501945',
   'Longitude': '-0.102892',
   'Lower layer super output area': 'Southwark 034D',
   'NationalPark': '',
   'Northing': '179818',
   'Parish': '',
   'Population': '14',
   'Postcode': 'SE1 0BJ',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '9',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531860',
   'GridRef': 'TQ318799',
   'Households': '3',
   'In Use?': 'Yes',
   'Introduced': '1980-01-01',
   'Latitude': '51.503102',
   'Longitude': '-0.10159',
   'Lower layer super output area': 'Southwark 002C',
   'NationalPark': '',
   'Northing': '179949',
   'Parish': '',
   'Population': '4',
   'Postcode': 'SE1 0BL',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '12',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531800',
   'GridRef': 'TQ318799',
   'Households': '',
   'In Use?': 'No',
   'Introduced': '1980-01-01',
   'Latitude': '51.502676',
   'Longitude': '-0.102472',
   'Lower layer super output area': 'Southwark 034D',
   'NationalPark': '',
   'Northing': '179900',
   'Parish': '',
   'Population': '',
   'Postcode': 'SE1 0BN',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '1995-07-01',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '7',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '531790',
   'GridRef': 'TQ317794',
   'Households': '16',
   'In Use?': 'Yes',
   'Introduced': '1994-05-01',
   'Latitude': '51.498365',
   'Longitude': '-0.102795',
   'Lower layer super output area': 'Southwark 034A',
   'NationalPark': '',
   'Northing': '179420',
   'Parish': '',
   'Population': '28',
   'Postcode': 'SE1 0BP',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'},
  {'Altitude': '9',
   'Built up area': 'Greater London',
   'Built up sub-division': 'Southwark',
   'Constituency': 'Bermondsey and Old Southwark',
   'Country': 'England',
   'County': 'Greater London',
   'CountyCode': 'E11000009',
   'District': 'Southwark',
   'DistrictCode': ' E09000028',
   'Easting': '532060',
   'GridRef': 'TQ320797',
   'Households': '69',
   'In Use?': 'Yes',
   'Introduced': '2007-01-01',
   'Latitude': '51.501249',
   'Longitude': '-0.098785',
   'Lower layer super output area': 'Southwark 002A',
   'NationalPark': '',
   'Northing': '179748',
   'Parish': '',
   'Population': '130',
   'Postcode': 'SE1 0BQ',
   'Region': 'London',
   'Rural/urban': 'Urban major conurbation',
   'Terminated': '',
   'Ward': 'Cathedrals',
   'WardCode': 'E05000536'}]]
   ```

