# Package for sypexgeo.net
----------
This package is intended for obtaining information about the IP address using the service database https://sypexgeo.net

## Installation

```bash
composer require "manzadey/sypexgeo"
```

## How used

Create an instance of the class and specify the path to the file and operation mode flags as arguments (optional):

```php
use Manzadey\SypexGeo\SxGeo;

$sxGeo = new SxGeo('sxGeo.dat');
```

Defining the country:

```php
$country = $sxGeo->getCountry($ip); // returns a two-digit ISO country code
$sxGeo->getCountryId($ip);          // returns the country number
```

Defining the city:

```php
$sxGeo->getCity($ip);                 // returns brief information, without the name of the region, country and time zone
$sxGeo->getCityFull($ip);             // returns full information about the city, region and country
$city = $sxGeo->get($ip);             // executes getCountry or getCity depending on the type of database
$cityName = $sxGeo->getCityName($ip); // returns the name of the city
```
