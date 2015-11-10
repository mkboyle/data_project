# Data Representation and Querying Project 2015
# Roscommon Sports Facilities
## Megan Boyle (G00312390)


## Introduction
This project provides the design and documentation for the dataset "Dataset title" which is available at [data.gov.ie](http://data.gov.ie)...

## About the data
This dataset was received in Comma Separated Values (CSV) format, and was downloaded from [*insert page name*](https://data.gov.ie/dataset/roscommon-sports-facilitiesbbc82/resource/fbe3f45a-5411-4279-b0ed-971679f5813b).
The CSV file contains 96 rows, the first being a header row with the names of each field.
There are twelve values on each line, which are as follows:
- **x**: the x co-ordinate.
- **y**: the y co-ordinate.
- **OBJECT_ID**: Unique id number.
- **Name**: Club Name.
- **Type**: sport type.
- **Address**: Address.
- **Telephone**: Telephone number.
- **Web**: Website Address.
- **Streetview_Link**: Google map Streetview.
- **WGS84 Longitude**: Telephone number.
- **WGS4 Latitude**: Telephone number.
- **Eircode**: Postal ID.
    
    
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
