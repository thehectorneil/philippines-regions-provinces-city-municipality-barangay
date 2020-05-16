# An SQL file of the Philippine's regions, provinces, cities, municipalities and barangays
This data is coming from the excel file published by the [Philippine Standard Geographic Code (PSGC)](https://psa.gov.ph/classification/psgc/). Since they are not releasing data into an SQL format, sharing to you this formatted file by regions, provinces, municipality, city and barangay that is linked with a foreign key. 

## Installation
You can copy the contents in the sql file and run on your active database sql editor. 

## Usage
NOTE: City and municipality are in one table named 'municipalicity'.

```sql
select * from regions
inner join provinces on regions.id = provinces.region_id
inner join municipalicity on provinces.id = municipalicity.province_id
inner join barangay on municipalicity.id = barangay.municipalicity_id
where barangay.barangay_name = 'Pembo'
```
## Technical Details
This sql is dumped from MySQL version 10.1.37-MariaDB

## Version
March 31, 2020 - current version

## Credits
[Philippine Standard Geographic Code (PSGC)](https://psa.gov.ph/classification/psgc/)

## Comments, Suggestions, Corrections
Please DM me in Twitter [thehectorneil](https://twitter.com/thehectorneil)
