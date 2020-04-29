## Introduction



OrbisMap is a collection of tools to support the rendering of geospatial information using the [Java2D API](https://docs.oracle.com/javase/8/docs/technotes/guides/2d/spec/j2d-intro.html).

OrbisMap is a organized in modules.



- Symcore : API that implements the [SymCore](symcore.md) specification
- [Feature2DStyle ](./conceptual_model/feature2dstyle.md): A style extensions for 2D geometry features
- Feature2DStyle-io :  Methods to read and write a Feature2DStyle in XML or JSON file
- Map-api : API to define the Layer model used by the renderer
- Map : Renderer implementation



OrbisMap is under active development. Its architecture is not yet stabilized and changes according to the adaptations that are done on the style extensions.

OrbisMap is distributed under the LGPL 3 license.

See the [GitHub](https://github.com/orbisgis/orbismap)  repository to get involved, submit patches or issues.




## Rendering engine



The Map module contains the mechanism to parse style and draw it. It is divided into 12 sequences.

- (1) User interface event to draw a map.
- (2) The renderer engine gets the style file that contains the symbology instructions.
- (3, 4 and 5) The style file is read by the Feature2DStyle-io parsers to create the Java Style Object Model composed of rules and symbols.
- (6) The renderer engine starts to draw the style object looping over each rules.
- (7) Each rule is scanned to check if a filter must be applied. The filter  condition (e.g., select all values greater than…) is prepared for each  symbolizer of the rule. 
- (8) The renderer engine starts to draw all symbols available in the Java Style Object Model.
- (9) Each symbol reads the data source on which the style must be applied.
- (10) A set of features according to the potential filter constraint of the  symbolizer is returned (including geometries and data attributes).
- (11) The symbols are filled with the features properties to create the graphic elements and visual variables.
- (12) Finally, the renderer engine displays the style as a map image.



![Rendering engine](/home/ebocher/Autres/codes/orbisdoc/docs/cartography/images/se_rendering_engine.png)

<center>Figure 14: Main sequences of the rendering engine.</center>



It's important to note that the input data model used by the render implementation is based on the ISpatialTable interface provided by OrbisData library.

This means that only the data organized in the table form (rows-columns) with a SFS-2 geometry model is supported, a.k.a : 2D feature vector data.  A feature is described as an abstraction of real world  phenomena as defined by GML standard ([Portele, 2007](http://www.opengeospatial.org/standards/gml)).

The Style concept is in charge of the cartographic portrayal of a  collection of features organized within a Layer by applying at least one  symbology Rule.





## How to use it