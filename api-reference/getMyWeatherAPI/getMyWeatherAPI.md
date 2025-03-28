---
id: getmyweather-api
title: GetMyWeather API
sidebar_label: GetMyWeather API
description: API documentation for a fictional weather API.
toc_max_heading_level: 4
tags: [Developer, Reference, API]
---

## About this article

A sample API document written for a fake weather application, GetMyWeather. GetMyWeather is a forecast service that shows forecast information at a time and place. This application is unique because it allows users to get the weather at different levels, from a state to an individual address, with the `specificity` parameter. This document describes what the API is and how it can be used.

<hr></hr>

## GetMyWeather API

### What is the GetMyWeather API? 

GetMyWeather, published by GetMyWeather, Inc., is a micro forecast service that shows detailed forecast information for a given time and place. GetMyWeather is unique because it can be used to find the weather of an entire state to the weather exactly at your home address using its **specificity** parameter. This capability is 
why GetMyWeather is referred to as a “micro forecast” service. Thus, GetMyWeather is ideal for sites that feature outdoor activity, such as camping or hiking sites. 

GetMyWeather, Inc. offers a GetMyWeather API, which allows you to call and access the GetMyWeather service and embed it in your own website. This document details how you can connect to and implement the API.

### Registering for a GetMyWeather API Key

You must have an authentication key to use the GetMyWeather API. To get a key: 

1. Go to [GetMyWeather.com](https://getmyweather.com).
2. Follow the instructions to register for a key.

Costs are subject to usage, with further details on our site. A free key is available for application development and testing. 

### Initializing the GetMyWeather API

The GetMyWeather API must only be initialized once per web session. To initialize the API, insert the following code into your webpage:

```js
<script type="text/javascript"> 
    var weatherForecast; 
    function init() { 
    weatherForecast = new getWeather(document.getElementById('forecast')} 
</script>
```

### Calling the GetMyWeather API

To call the API:

1. Insert the following into your webpage: 

```html
<script async defer src="https://www.getmyweather.com/getWeather?key=<YOUR_KEY>&callback=init&location=<LATITUDE>:<LONGITUDE>&specificity=<SPECIFICITY>&time=<TIME>"></script> 
```

2. Provide appropriate values for the parameters above. For more information on GetMyWeather's parameters, see [Providing GetMyWeather API Values](#providing-getmyweather-api-values).

### Providing GetMyWeather API Values

The GetMyWeather API has various parameters that **must** be provided per API call. For more information on calling the API, see [Calling the GetMyWeatherAPI](#calling-the-getmyweather-api). 

The required parameters are: 

| Parameter | Description | Units | Other | 
| --------- | ----------- | ----- | ----- |
| `key` | The API authentication key provided by GetMyWeather, Inc. upon registration. | | See [Registering for a GetMyWeather API Key](#registering-for-a-getmyweather-api-key) for more information. |
| `location` | The geographical location for the forecast. | Latitude and longitude | ISO 6709 |
| `specificity` | The radius of the area for the forecast, centered on the `location`. | Meters | Minimum: 10 meters<br /> Maximum: 100,000 meters | 
| `time` | What time in the future at which to request the forecast. | Hours | Decimals allowed |

### Interpreting the Return Package

GetMyWeather will return an HTML package on a successful call. Below is a sample repsonse.

```html
<div class="forecast"> 
    <div class="temperature">78</div> 
    <div class="windspeed">15</div> 
    <div class="chanceRain">30</div> 
    <div class="trust">80</div> 
</div>
```

The return parameters are: 

:::info[Note]
The return package is static. To change the return parameters, you must call the API again with new input parameters.
:::

| Parameter | Description | Units | Other | 
| --------- | ----------- | ----- | ----- |
| `temperature` | The predicted degrees of the forecast. | Fahrenheit | | 
| `windspeed` | The predicted wind speed of the forecast. | Miles per hour | | 
| `chanceRain` | The predicted chance of rain of the forecast. |  A percentage value between 0-100. | | 
| `trust` | The degree of confidence the API has in its forecast prediction. |  A percentage value between 0-100. | 0 is very unreliable and 100 is absolutely reliable. See [Trust](#trust) for more information. |

#### Trust

`trust` is a return parameter unique to GetMyWeather, and it can be affected by `specificity` and `time`. Large values for `specificity` and `time` will return a **low** `trust` value and vice versa. 

`trust` is useful for displaying how reliable the forecast is to your website's users. For example, using `trust`, you'll be abel to show users that this morning's forecast at the office has a 90% chance of occurring. On the other hand, a forecast two weeks from now over the entire state of California may only have a 10% chance of occurring. 

### Inserting the Return Package

To insert the return package, include the empty element `div id="forecast"></div>` in your HTML wherever you want your package to appear. Your browser will then replace the empty element with the return package. 

### Troubleshooting and Errors

If GetMyWeather cannot provide a forecast, it will return one of the following messages for troubleshooting purposes. 

* "Invalid key"
* "Invalid parameter format"
* "Parameter out of range"
* "Server unavailable"