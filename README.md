Indian Railway PNR Status API
=================

To fetch the PNR status from Indian railway using PHP and cURL

API to fetch the PNR status

##USAGE

The API support Both POST and GET Parameter.

example to get the data in XML format is 

~~http://www.kirant400.com/irctc/pnr.php?pnrno=4565206151&rtype=XML~~

| KEY     | Datatype          | Mandatory     | Description
|---------|-------------------|---------------|------------
| pnrno   | Integer(10)       | true          | PNR number to be fetched 10 digit
| rtype   | String(XML/JSON)  | false         | Return type format 
| callback| String 			      | false         | Support for JSONP only supported for GET

The result format supported are XML,JSON and JSONP

JSON is the default return type. If callback is provided in the GET parameter then JSONP is returned 

##RESULT XML

Example 
```
<?xml version="1.0"?>
<result>
<status>OK</status>
<data>
  <pnr>4565206151</pnr>
  <train_name>TRAIN EXP</train_name>
  <train_number>26536</train_number>
  <from>SRC</from>
  <to>DES</to>
  <reservedto>DES</reservedto>
  <board>SRC</board>
  <class>SL</class>
  <travel_date>18- 7-2033</travel_date>
  <passenger>
    <seat_number>W/L 41,GNWL</seat_number> <!-- passenger 1 -->
    <status>W/L 6</status>
    
    <seat_number>W/L 42,GNWL</seat_number> <!-- passenger 2 -->
    <status>W/L 7</status>
  </passenger>
  </data>
</result> 
```
##RESULT JSON

Example
```
{"status":"OK",
  "data":
        {"pnr":"4565206151",
          "train_name":"TRAIN EXP",
          "train_number":"26536",
          "from":"SRC",
          "to":"DES",
          "reservedto":"DES",
          "board":"SRC",
          "class":" SL",
          "travel_date":"18- 7-2033",
          "passenger":
            [{"seat_number":"W\/L   41,GNWL",
                "status":"W\/L    6"},
             {"seat_number":"W\/L   42,GNWL",
                "status":"W\/L    7"}
            ]
       }
}
```
##More Details

Latest Blog post can be found [here](http://revealdtech.blogspot.com/2014/06/using-php-curl-get-pnr-status-of-indian.html "Data with captcha").

Initial Reading from [here](http://revealdtech.blogspot.in/2013/07/using-php-curl-get-contents-of-site.html "Basic").
