# Data Representation and Querying Project 2015
## Roscommon Sports Facilities - Megan Boyle (G00312390)

## Introduction
For this project I have chosen the API **Roscommon Sports Facilities**. It provides the design and documentation for the dataset which is available at [data.gov.ie](https://data.gov.ie/dataset/roscommon-sports-facilitiesbbc82/resource/fbe3f45a-5411-4279-b0ed-971679f5813b). This dataset allows the front end user to get information on Sports Facilities in County Roscommon for various different sports.

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
**WGS84Longitude** | World Geodetic System co-ordinate.
**WGS4Latitude** | World Geodetic System co-ordinate.
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
      "WGS84Longitude" : "-8.24353211",
      "WGS4Latitude" : "53.929607",
      "Eircode" : " "
    }
]
```

##Sample Searches##

If the user wanted to restrict the data they wanted to a specific field the would use something like the following:

http://www.sportsfacilities.com/Roscommon/[field]

[field] should be replaced with the field they want to see e.g name, type, address etc.
The user could refine there search even more by adding another parameter. For example the user wants the get just gaa facilities in Roscommon, They would use:

http://www.sportsfacilities.com/Roscommon/type/gaa

The same can be done with adresses and id's etc. If there isn't a found address then an empty array will be returned 
An example of a response would be:

```json
[
    {
      "x" : "-8.020513103923442.",
      "y" : "53.368749653859169",
      "OBJECT_ID" : "4",
      "Name" : "Clan na Gael",
      "Type" : "GAA",
      "Address" : "Johnstown, Cornafulla, Athlone, Co Roscommon",
      "Telephone" : "NA",
      "Web" : " ",
      "Streetview_Link" : "http://apps.roscommoncoco.ie/GoogleStreetView/GoogleMapStreetView.html?Lat=53.3687496550367&amp;Lng=-8.02051310386946",
      "WGS84Longitude" : "-8.0205131",
      "WGS4Latitude" : "53.3687496",
      "Eircode" : " "
    }
]
```

To search for Ballinameen Gaa club :

http://www.sportsfacilities.com/Roscommon/Name=Ballinameen+GAA/

```json
[
    {
      "x" : "-8.301219921755429",
      "y" : "53.907989099298348",
      "OBJECT_ID" : "2",
      "Name" : "Ballinameen GAA",
      "Type" : "GAA",
      "Address" : "St Attractas GAA Club, Ballinameen, Co Roscommon",
      "Telephone" : "NA",
      "Web" : " ",
      "Streetview_Link" : "http://apps.roscommoncoco.ie/GoogleStreetView/GoogleMapStreetView.html?Lat=53.9079891002022&amp;Lng=-8.30121992154989",
      "WGS84 Longitude" : "-8.301219",
      "WGS4 Latitude" : "53.9079891",
      "Eircode" : " "
    }
]
```
