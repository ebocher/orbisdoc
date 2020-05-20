To illustrate the capabilities of the Feature2DStyle extension, we present some use cases.

For each use case, we provide  :
- the rendering result
- two encodings in JSON and XML


## Single symbol map

> Single symbol map is used to apply the same symbol to all geometries in a layer. This map is usefull for drawing a layer with just one category such as county boundaries or buildings as above. Single symbol can be applied for point, line, or polygon layers. 

     

<table>
  <tr>
    <td rowspan="2"><img src="cartography/images/single_symbol_map.png" width="300"></td>
    <td><a href="https://raw.githubusercontent.com/orbisgis/orbismap/master/map/src/test/resources/org/orbisgis/orbismap/map/renderer/featureStyle/styles/single_symbol/single_symbol_map.json">JSON encoding</a></td>    
  </tr>
  <tr>
    <td><a href="https://raw.githubusercontent.com/orbisgis/orbismap/master/map/src/test/resources/org/orbisgis/orbismap/map/renderer/featureStyle/styles/single_symbol/single_symbol_map.se">XML encoding</a></td>
  </tr>
</table>

 ## Unique values map
 
 > The unique values map is used to apply symbols to represent geometries with different values for an attribute. Unique value thematic map can be applied for point, line, or polygon layers. The above illustration is an example of a unique value thematic map based on highway types.


 ## Choropleth map
 
> Choropleth map is the most common map representation.Based on of the subdivision of the attribute values into classes or intervals, areal geometries are filled.