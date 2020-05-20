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
 > The unique values map is used to apply symbols to represent geometries with different values for an attribute. Unique value thematic map can be applied for point, line, or polygon layers. 
 > The above illustration is an example of a unique value thematic map based on highway types.


 ## Choropleth map 
> Choropleth map is the most common map representation.Based on of the subdivision of the attribute values into classes 
> or intervals, areal geometries are filled.


 ## Graduated symbol map 
> Graduated symbol map uses symbols of different sizes to represent differences in the magnitude of a discrete, 
> abruptly changing phenomenon. It's the way to visualize absolute numbers like population size, traffic volume... The sizes of the symbols corresponds to a set of classes. The following is an example of a Graduated Symbol map of 4 classes representing the number of building permits in Europe in 2014. 

## Proportional symbol map 
> Proportional symbol map uses symbols of different sizes to represent the numerical values of an attribute. 
> For a Graduated symbol map, the classed ones are known. This is similar to the choropleth map where values are broken into ranges . 
> While a Proportional symbol map, the area of the symbols is made proportional with the value to be displayed (scaled proportionately).

## Proportional symbol map with custom symbol
> To improve perceptual scaling and facilitate understanding of the map, Cartographer uses custom shape for a symbol (truetype, image). 
> The following is an example of a Proportional symbol map where the symbol is represented by a building.



## Label map
> Labels are used are for naming geographic features. Label depends on selecting text styles (font, color) and  positioning.


## Proportional label
> Proportional label map uses the same technique than proportional symbols, expected that the size of the font is scaled proportionately.


## Bi-variate proportional map with unique values
> Bivariate map is a technique in cartography to display two different thematic variables at the same time. The following map displays 
> a bivariate map applied on highway types and size. This king map combine a proportional line on the size of the roads and a unique values classification based on the road types.

## Bi-variate proportional opposing symbols
> Bivariate map is a technique in cartography to display two different thematic variables at the same time. 
> One of the most commun technique to create a bivariate map is to combine of visual variables. For most cartographers it may better support different map reading tasks. The following map uses the same visual variable to represent two variables (Half Circle). 
> It permits a cross-variable comparison between the number of permits in 2005 and 2014.

## Bi-variate proportional - Unified attributes
> The bivariate point symbol offers several alternatives to display multiple attributes at the same time. 
> The cartographer can turn to visual variables as the shape, the size, the hue. The following map considers that the width and height are made proportional to each attributes being mapped : number of building permits in 2014 for the width and number of building permits in 2005 for the height.

## Bi-variate with colored variable
>The Bivariate map proposes useful and number of techniques to display on the same map two attributes. The following map uses a separable visual variable combinations to 
> communicate two attributes about the number of accidents (proportional symbol) and the population density (choropleth map)

## Dot map
> A Dot map is used to create a visual impression of density by placing a dot or some other symbol in the approximate location of one or more instances 
> of the variable being mapped. Dot map could not be used with normalized data but only for raw data.

## Combined visual variables - hatch and graphic fill
> For a cartographer, the combinaison of visual variables serves as a fundamental graphic constituent of the map. There is no broadly accepted list of visual variables but several cartographic authors agree with a set of commons variables (Size, Shape, Hue-Color, Texture, Orientation, Saturation). 
> The following map shows assembled visual variables expressed with custom fills : GraphicFill and HatchedFill.

## Interpolate color range
> Interpolate color range is commonly used to display a raster with a continuous range of colors. However, as the following map shows it's easily to map continuous feature values using interpolate function. 
> Note : As Color is specified with the 3 elements Red, Green and Blue, 3 interpolations must be apply.

## Map with spatial expression predicates
