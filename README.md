# Data Representation and Querying Project 2015
## Roscommon Sports Facilities - Megan Boyle (G00312390)

## Introduction
For this project I have chosen the API **Roscommon Sports Facilities**. It provides the design and documentation for the dataset which is available at [data.gov.ie](https://data.gov.ie/dataset/roscommon-sports-facilitiesbbc82/resource/fbe3f45a-5411-4279-b0ed-971679f5813b). This dataset contains information on Sports Facilities in County Roscommon for various different sports.

## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from [data.gov.ie](https://data.gov.ie/dataset/roscommon-sports-facilitiesbbc82/resource/fbe3f45a-5411-4279-b0ed-971679f5813b).
The CSV file contains 96 rows. Each row has 12 fields/columns.
The column and column description are as follows:

Column | Description
------ | -----------
**x** | the x co-ordinate.
**y** | the y co-ordinate.
**OBJECT_ID** | Unique ID number for each facility.
**Name** | Sport Club Name.
**Type** | Facilities sport type.
**Address** | Address of facility.
**Telephone** | Telephone number.
**Web** | Website Address.
**Streetview_Link** | Google map Streetview of facility.
**WGS84 Longitude** | World Geodetic System co-ordinate.
**WGS4 Latitude** | World Geodetic System co-ordinate.
**Eircode** | Postal ID of facility

Below is an example of information taken from the dataset in JSON format, using the columns above.

```json
[
    {
      "x" : "-8.24353211404425",
      "y" : "53.929607066314382",
      "OBJECT_ID" : "71",
      "Name" : "Cavetown Tennis Club",
      "Type" : "Tennis",
      "Address" : "Croghan, Boyle, Co Roscommon",
      "Telephone" : "NA",
      "Web" : " ",
      "Streetview_Link" : "http://apps.roscommoncoco.ie/GoogleStreetView/GoogleMapStreetView.html?Lat=53.929607067645&amp;Lng=-8.24353211344334",
      "WGS84 Longitude" : "-8.24353211",
      "WGS4 Latitude" : "53.929607",
      "Eircode" : " "
    }
]
```
    
    
    ## List of cars for a given year
You can get a list of cars purchased in a given year using the GET method at the following URL:
*http://carsapi.com/year/[year]*
where you replace [year] with the year.
For example, the URL:
*http://carsapi.com/year/2005*
will return a list of cars purchased in 2005.
The data will be returned in JSON format, with the following properties for each car:
    - *price*: the price of the car.
    - *model*: the model of the car.
    ...
An example of a response would be:
    ```json
    [ {"price": 20000, "model": "Skoda", ...}, {...}, ...]
    ```
