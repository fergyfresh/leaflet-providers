Leaflet-providers
=================
An extension to [Leaflet](http://leafletjs.com/) that contains configurations for various free tile providers.

# Usage
```Javascript
// add Stamen Watercolor to map.
L.tileLayer.provider('Stamen.Watercolor').addTo(map);
```

# Providers

Leaflet-providers provides tile layers from diffent providers, including *OpenStreetMap*, *MapQuestOpen*, *Stamen*, *Esri* and *OpenWeatherMap*. The full listing of free to use maps can be [previewed](preview/index.html). The page will show you the name to use with `leaflet-providers.js` and the code to use it without dependencies.

## Providers requiring registration

In addition the the

### Nokia.

In order to use Nokia basemaps, you must [register](https://developer.here.com/web/guest/myapps). With your `devID` and `appID` specified in the options, the available layers are:

* Nokia.normalDay
* Nokia.normalGreyDay
* Nokia.satelliteNoLabelsDay
* Nokia.satelliteYesLabelsDay
* Nokia.terrainDay

For example:
```Javascript
L.tileLayer.provider('Nokia.terrainDay', {
    devID: 'insert ID here',
    appId: 'insert ID here'
}).addTo(map);
```

### Mapbox

In order to use Mapbox maps, you must [register](https://tiles.mapbox.com/signup). If your user name is `YourName` and your map is called `MyMap` you can add it with
```JavaScript
L.tileLayer.provider('Mapbox.YourName.MyMap');
```

### CloudMade

In order to use CloudMade maps, you must [register](http://account.cloudmade.com/register). You may use it with your `apiKey` and `styleID` specified in the options like this:
```JavaScript
L.tileLayer.provider('CloudMade', {
    apiKey: 'MyAPIKey',
    styleID: '123'
}).addTo(map);
```

# Goodies

An other little goodie this library provides is a prefilled layer control, so you can just provide an array of strings:

```JavaScript
var baseLayers = ['Stamen.Watercolor', 'OpenStreetMap.Mapnik'],
	overlays = ['OpenWeatherMap.Clouds'];

var layerControl = L.control.layers.provided(baseLayers, overlays).addTo(map);

// you can still add your own afterwards with
layerControl.addBaseLayer(layer, name);
```

This work was inspired from <https://gist.github.com/1804938>, and originally created by [Stefan Seelmann](https://github.com/seelmann).