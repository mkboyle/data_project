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
**WGS84Longitude** | World Geodetic System Longitude co-ordinate.
**WGS4Latitude** | World Geodetic System Latitude co-ordinate.
**Eircode** | Postal ID of the facility

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

#Sample Searches#

##Get a List of facilities for a certain Sport Type##

The list of facilities can be filtered for a certain sport type using the GET method. An example of a url to get this would be:

        http://www.sportsfacilities.com/Roscommon/type/[type]

In this case [type] should be replaced with the sports type facility the front end user wants e.g GAA, tennis, Golf etc.
An example of a reponse to http://www.sportsfacilities.com/Roscommon/type/gaa in JSON format would be something like the following:

```json
[
    {
      "Type" : "GAA",
      "x" : "-8.020513103923442.",
      "y" : "53.368749653859169",
      "OBJECT_ID" : "4",
      "Name" : "Clan na Gael",
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

##Get a List of Sport facilities for a certain Club##

The list of facilities can be further broken down for a certain Club name also using the GET method. An example of a url to get this would be:

        http://www.sportsfacilities.com/Roscommon/Name/[Name]

In this case [Name] should be replaced with the name of the club the front end user wants e.g Ballinameen Gaa club.
An example of a reponse to http://www.sportsfacilities.com/Roscommon/Name=Ballinameen+GAA/ in JSON format would be something like the following:

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

##List of Sport facilities closet to users location##

The list of facilities can be restricted to what is closet to the users location using the longitude and latitude co-ordinates. This can be achieved by using the POST method. An example of a url to get this would be:

        http://www.sportsfacilities.com/Roscommon/closetFaciliites

The users longitude and latitude co-ordinates would be compared to the facilities longitude and latitude co-ordinates to return the closet facilities to the user.nAn example of a reponse in JSON format would be something like the following:

```json
[
    {
      "WGS84 Longitude" : "-8.191536",
      "WGS4 Latitude" : "53.848704",
      "x" : "-8.191536529577093",
      "y" : "53.848704411775131",
      "OBJECT_ID" : "6",
      "Name" : "Elphin GAA Club",
      "Type" : "GAA",
      "Address" : "Orchard Park, Elphin, Co Roscommon",
      "Telephone" : "NA",
      "Web" : " ",
      "Streetview_Link" : "http://apps.roscommoncoco.ie/GoogleStreetView/GoogleMapStreetView.html?Lat=53.848704412512&amp;Lng=-8.19153653015078",
      "Eircode" : " "
    }
]
```
