## Fill extensions

### SolidFill

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/SolidFill

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/SolidFillClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the SolidFill class and meet all of the tabulated constraints and notes.

The SolidFill class is a concrete implementation of the Fill class and allows to formulate a filling of an area (e.g. a polygon geometry or any kind of symbol).

| **Name** | **Definition**             | **Data type and value**                                      | **Multiplicity** |
| -------- | -------------------------- | ------------------------------------------------------------ | ---------------- |
| color    | The color to fill the area | Color data type                                              | zero or one      |
| opacity  | Opacity of the Color       | ParameterValue type (Float) Value: [0;1] (1 means 100% opaque)Default value: 0 | zero or one      |

### GraphicFill 

**Requirement class:** [http://www.opengis.net/spec/symbology/2.0/req/GraphicFill](http://www.opengis.net/spec/symbology/2.0/req/SolidFill)

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/GraphicFillClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the GraphicFill class and meet all of the tabulated constraints and notes.

The GraphicFill extension is a concrete implementation of the Fill class. It repeats a rectangular tiling pattern over an area (i.e. mosaïc). A graphic can be defined very informally as “a little picture”. The appearance of the graphic is defined with the embedded Graphic class parameter.

The graphic fill repeats the Graphic in a rectangular tiling pattern with a TileGap between tiles. The TileGap parameter allows to define vertical and horizontal gaps between tiles. 

| **Name** | **Definition**                                               | **Data type and value** | **Multiplicity** |
| -------- | ------------------------------------------------------------ | ----------------------- | ---------------- |
| graphic  | The graphic to repeat within the area                        | Graphic data type       | one              |
| tileGap  | Allow to define a empty space to put between two consecutive tile (i.e. graphic) | TileGap data type       | zero or one      |



TileGap is introduced as an extension. It shall meet all of the tabulated constraints and notes.

| **Name** | **Definition**                   | **Data type and value**                                      | **Multiplicity** |
| -------- | -------------------------------- | ------------------------------------------------------------ | ---------------- |
| x        | Horizontal gap between two tiles | Double ParameterValue data type, see Value range is [0:+∞[. Default is 0. | zero or one      |
| y        | Vertical gap between two tiles   | Double ParameterValue data type, Value range is [0:+∞[. Default is 0. | zero or one      |

1. The X parameter indicates the horizontal gap between two consecutive tiles. This value is a non-negative real number. 
2. The Y parameter has the same definition as the X one, but for the vertical gap. The default gap size is zero units in each direction.

The graphicFill mechanism is illustrated in [Annexe B - GraphicFill](https://docs.google.com/document/d/1_hQHFQOvlUkUBtjHR4FtDRPpd9Rl0Xdc1bOilJE27L8/edit#heading=h.z186k8oiqz0b).

### HatchedFill

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/HatchedFill

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/HatchedFillClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the HatchedFill class and meet all of the tabulated constraints and notes.

The HatchedFill extension is a concrete implementation of Fill class. It offers simple parameters which allows to control a hatching easily in a way conventional in cartography.

| **Name** | **Definition**                                               | **Data type and value**                                      | **Multiplicity** |
| -------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------- |
| stroke   | The stroke to use to style hatches                           | Stroke data type                                             | zero or one      |
| angle    | Hatches orientation, clockwise degree                        | Double ParameterValue data type, Value range is ]-∞;+∞[. Default is 45. | zero or one      |
| distance | Distance between geometry bases of two consecutive hatches   | Double ParameterValue data type, Value range is [0;+∞[. Default is equivalent to 2mm. | zero or one      |
| offset   | Allow to define a empty space to put between two consecutive tile (i.e. graphic) | Double, ParameterValue data type, Value range is [0;+∞[. Default is 0. | zero or one      |

1. Hatching is defined by a juxtaposed hatches. A hatch is rendered by a Stroke and oriented given an Angle. The Distance parameter defines the perpendicular space between two consecutive hatches. 
   Hatches are organized according to a reference line which is defined as the line that crosses a system-dependent anchor point and is oriented given the provided Angle. Also, the complementary Offset parameter allows to move the anchor point according to a displacement in the direction of value Angle+90° (see [Annexe B - GraphicFill](https://docs.google.com/document/d/1_hQHFQOvlUkUBtjHR4FtDRPpd9Rl0Xdc1bOilJE27L8/edit#heading=h.z186k8oiqz0b)).        
2. Clockwise is the rotation of Angle because of the coordinate system of the view box with X axis advancing to the right of the origin and the Y axis advancing downward.



## Stroke extension

### PenStroke

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/PenStroke

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/PenStrokeClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the PenStroke class and meet all of the tabulated constraints and notes.

The PenStroke extension is a concrete implementation of the Stroke class. It allows to draw a line (e.g. a 1-dimensional geometry, the outline of a marker, etc) analogously to how a pen is used with ink, that is to say by filling the area formed by the thickness of the line.

| **Name** | **Definition**                                               | **Data type and value**                                      | **Multiplicity** |
| -------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------- |
| width    | Thickness of the line which gives form to an area to fill (a) | ParameterValue data type (Float) Value: [0;+∞)Default value: 1px | zero or one      |
| fill     | The filling style to draw the linear area                    | Fill data type                                               | zero or one      |

1. The Width parameter is in the context of a UnitOfMeasure code (that may be inherited from a parent element).

### GraphicStroke 

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/GraphicStroke

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/GraphicStrokeClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the GraphicStroke class and meet all of the tabulated constraints and notes.

The GraphicStroke extension is a concrete implementation of the Stroke class. It is about one graphic repeated along a line. A renderer may apply some aesthetic embellishments like trying to bend a graphic around corners or avoid a graphic to be cut at the start or at the end.

| **Name** | **Definition**                                               | **Data type and value**                                      | **Multiplicity** |
| -------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------- |
| graphic  | The graphic to plot                                          | Graphic data type                                            | one              |
| length   | Linear length to reserve along the line to plot a single graphic (a) | ParameterValue data type (Float)Value: [0;+∞)Default: graphic natural length | zero or one      |

1. The Length property specifies the linear length to reserve along the line for one of the repeated graphics to plot. By default, the linear length is equal to the Graphic natural length (which depends on the view box of the graphic). It has the effect to perfectly juxtapose the repeated graphics all along the line. Zero length value means the graphic is not repeated within all the available linear space. Notice that a single graphic is not plotted if the size of the available linear space smaller than the Length.

### TextStroke

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/TextStroke

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/TextStrokeClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the TextStroke class and meet all of the tabulated constraints and notes.

The TextStroke extension is a concrete implementation of the Stroke class. It is about the repetition of a text label along a line in a similar way GraphicStroke does by repeating a graphic. The text glyphs are plotted as integral rotated units following the line.

| **Name**  | **Definition**                                               | **Data type and value**                                      | **Multiplicity** |
| --------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------- |
| lineLabel | The label configuration                                      | LineLabel data type                                          | one              |
| length    | Linear length to reserve along the line to plot the label (a) | ParameterValue data type (Float)Value: [0;+∞)Default: label natural length | zero or one      |

1. The Length parameter specifies the linear length to reserve along the line for one of the repeated labels to plot. By default, the linear length is equal to the label natural length (which depends on the LalbelText and Font configurations extensions). It has the effect to perfectly juxtapose the repeated labels all along the line. Zero length value means the label is not repeated.



## Color extensions



### HexaColor

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/HexaColor

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/HexaColorClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the HexaColor extension and meet all of the tabulated constraints and notes.

The HexaColor extension is a concrete implementation of the Color class to expressed a RGB color model.  The format of the color is in hexadecimal notation. It is a ‘`#`’ immediately followed by either three or six   hexadecimal characters.

| **Name** | **Definition**                | **Data type and value**                                      | **Multiplicity** |
| -------- | ----------------------------- | ------------------------------------------------------------ | ---------------- |
| color      | The hexadecimal notation of the color    | ParameterValue data type (String) Default value: #000000  | one              |


### RGBColor

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/RGBColor

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/RGBColorClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the RGBColor extension and meet all of the tabulated constraints and notes.

The RGBColor extension is a concrete implementation of the Color class where the color is expressed as three integer properties in conformance with the sRGB standardized color space.

| **Name** | **Definition**                | **Data type and value**                                      | **Multiplicity** |
| -------- | ----------------------------- | ------------------------------------------------------------ | ---------------- |
| red      | The red value of the color    | ParameterValue data type (Integer) Value: (0;255)Default value: 0 | one              |
| green    | The green value of the colorR | ParameterValue data type (Integer) Value: (0;255)Default value: 0 | one              |
| blue     | The blue value of the color   | ParameterValue data type (Integer) Value: (0;255)Default value: 0 | one              |



### WellKnownNameColor

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/WellKnownNameColorClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the WellKnownNameColor and meet all of the tabulated constraints and notes.

WellKnownNameColor is a codeList element that provides a list of color names to define a Color. The color names are case-insensitive.
The list is based of the [X11 colors](https://en.wikipedia.org/wiki/X11_color_names).




## ExternalGraphic extension

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/ExternalGraphic

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/ExternalGraphicClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the ExternalGraphic extension and meet all of the tabulated constraints and notes.

The ExternalGraphic extension extends the abstract Graphic type. It allows to reference a graphic resource to use as a graphic symbolizer (e.g. PNG bitmap graphic, SVG vector graphic, ...).

| **Name**       | **Definition**                                               | **Data type and value**                                      | **Multiplicity**                    |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ----------------------------------- |
| onlineResource | Reference to on-line resource from which a graphic can be obtained (a) | ParameterValue data type (CharacterString)Value: an URL identifier | one (exclusive with InlineContent)  |
| inlineContent  | Inline content of a graphic object (a,b)                     | Literal data type                                            | one (exclusive with OnlineResource) |
| encoding       | Expected inline content encoding (b)                         | Literal data type                                            | one (exclusive with OnlineResource) |
| format         | Expected content format of a successful fetch (a)            | Literal data typeValue: a MIME type identifier               | one                                 |
| opacity        | Opacity of the graphic                                       | ParameterValue data type (Float) Value: [0;1] (1 means 100% opaque)Default values: 0 | zero or one                         |

1. There are two ways to define an external format graphic, either using OnlineResource or InlineContent. They can't be defined together. The external Format of the graphic shall be mentioned as the expected content MIME type of a successful fetch.
2. When using the alternative InlineContent parameter to include in-line the content of an external graphic object, then the inline encoding shall be mentioned. The two choices for encoding are XML and Base-64-encoded binary.

## MarkGraphic extension

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/MarkGraphic

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/MarkGraphicClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the MarkGraphic extension and meet all of the tabulated constraints and notes.

The MarkGraphic extension extends the abstract Graphic type. It allows a graphic to be created by stroking and filling a shape.

| **Name**       | **Definition**                                        | **Data type and value**                                      | **Multiplicity**                                      |
| -------------- | ----------------------------------------------------- | ------------------------------------------------------------ | ----------------------------------------------------- |
| wellKnownName  | Name of the shape to stroke and fill (a,b)            | WellKnownName code                                           | one (exclusive with OnlineResource and InlineContent) |
| onlineResource | Online location of a mark objects archive (a,c)       | ParameterValue data type (CharacterString)Value: an URL identifier | One (exclusive with WellKnownName and InlineContent)  |
| inlineContent  | Inline content of a mark objects archive (a,c)        | Literal data type                                            | One (exclusive with OnlineResource and WellKnownName) |
| encoding       | Expected inline content encoding (c)                  | Literal data typeValue: XML \| base64                        | One (exclusive with OnlineResource and WellKnownName) |
| format         | Expected content format of a successful fetch (c)     | Literal data typeValue: a MIME type identifier               | One (exclusive with WellKnownName)                    |
| markIndex      | Index of a mark from a mark objects archive (c)       | ParameterValue data type (Integer)Value: [0;+∞)              | One (exclusive with WellKnownName)                    |
| fill           | The filling style to fill the shape (d)               | Fill data type                                               | Zero or one                                           |
| stroke         | The stroke style to draw the outline of the shape (d) | Stroke data type                                             | Zero or one                                           |

1. There are three ways to define a mark shape, either using WellKnownName, OnlineResource or InlineContent. They can't be defined together.
2. WellKnownName is used to draw predefined internal marks. The center of the view box is the default anchor point, except for star and triangle.
3. OnlineResource and InlineContent are two ways to select a mark from an external mark archive (e.g. glyph from TrueType or SVG font). The MarkIndex property represents a numeric identifier which allows an individual mark in a mark archive to be selected. The default anchor point is format-dependent, while the center of the view box shall be used if no information is available.
4. A missing Fill parameter means that the geometry will not be filled. A missing Stroke parameter means that the geometry will not be stroked. When both are used, the filling is rendered first and then the stroking rendered on top of the filling. A missing Halo parameter means no halo is drawn.
5. The encoding must describe the order in which transformations are executed.

The extension introduces also WellKnownName code list extension, used to draw predefined shape of mark graphics. It includes the following codes : square, circle, triangle, star, cross, x.

| **Name**      | **Definition**                                               | **Data type and value** | **Multiplicity** |
| ------------- | ------------------------------------------------------------ | ----------------------- | ---------------- |
| wellKnownName | Shall support an optional codelist parameter.                | Literal data type       | one              |
| extension     | Any encoding should allow the user to extend the codelist to include custom items | Any                     | zero or more     |

## Halo extension

**Requirement class:** http://www.opengis.net/spec/symbology/2.0/req/Halo

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** None.

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/HaloClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the Halo extension and meet all of the tabulated constraints and notes.

The Halo extension may be used to improve the visibility of shapes like font glyphs or graphics by drawing an extended area surrounding the shapes. 

- the extension adds a new class Halo: the halo is calculated according to a radius (in context of an UnitOfMeasure) and then filled adequately so as to highlight the shapes.

| **Name**      | **Definition**                                               | **Data type and value**                                      | **Multiplicity** |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------- |
| unitOfMeasure | Unit of measure to apply to all graphical properties inside a Halo | UnitOfMeasure code                                           | zero or one      |
| radius        | Span size of the surrounding halo area (a)                   | ParameterValue data type (Float)Value: [0;+∞)Default value: 1px | zero or one      |
| fill          | Fill style to fill the halo area                             | Fill data type                                               | zero or one      |
| extension     | Any encoding should allow the user to extend the halo to include custom items | Any                                                          | zero or more     |

1. To calculate the halo area, the radius is taken from the outside edge of a shape (and the inside edge of “holes” in the shape)

- the extension adds a property to the classes MarkGraphic, ExternalGraphic, PointLabel and LineLabel. 

| **Name** | **Definition**               | **Data type and value** | **Multiplicity** |
| -------- | ---------------------------- | ----------------------- | ---------------- |
| halo     | Fill a halo around the shape | Halo data type          | zero or one      |

## PerpendicularOffset extension

**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/PerpendicularOffset 

**Scope:** All requirements in this subsection relate to the above requirement class.



**Description:** The extension allows to construct parallel lines around a geometry. It adds a property to the classes LineSymbolizer, AreaSymbolizer and TextSymbolizer with related behaviours (described below for each requirement).

| **Name**            | **Definition**                                           | **Data type and value**                        | **Multiplicity** |
| ------------------- | -------------------------------------------------------- | ---------------------------------------------- | ---------------- |
| perpendicularOffset | Construct parallel lines around of the original geometry | ParameterValue data type (Float)Value: (-∞;+∞) | zero or one      |



**Requirement ID:****
**[http://www.opengis.net/spec/symbology/2.0/req/LineSymbolizerClass](http://www.opengis.net/spec/symbology/2.0/req/style/LineSymbolizerExtension)[/PerpendicularOffset
](http://www.opengis.net/spec/symbology/2.0/req/LinePerpendicularOffset)**Requirement Txt:** Implementations shall support the encoding of the added property of the LineSymbolizer extension and meet all of the tabulated constraints and notes.

For a LineSymbolizer, the distance between original geometry and drawn line stays equal. This construction can result in drawn lines that are actually smaller or longer than the original geometry. The distance is in the context of the UnitOfMeasure property and is positive to the left-hand side of the line string. Negative numbers mean right (see [Annexe B - PerpendicularOffset](https://docs.google.com/document/d/1_hQHFQOvlUkUBtjHR4FtDRPpd9Rl0Xdc1bOilJE27L8/edit#heading=h.pkauxqlap12e)).

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/AreaSymbolizerClass](http://www.opengis.net/spec/symbology/2.0/req/style/LineSymbolizerExtension)[/PerpendicularOffset
](http://www.opengis.net/spec/symbology/2.0/req/LinePerpendicularOffset)**Requirement Txt:** Implementations shall support the encoding of the added property of the AreaSymbolizer extension and meet all of the tabulated constraints and notes.

For a AreaSymbolizer, the extension allows to shrink or grow the area impacting both the stroking of the outline and the filling of the area. The distance is in the context of the UnitOfMeasure parameter and is positive to the outside of the polygon. Negative numbers mean drawing the polygon smaller (see [Annexe B - PerpendicularOffset](https://docs.google.com/document/d/1_hQHFQOvlUkUBtjHR4FtDRPpd9Rl0Xdc1bOilJE27L8/edit#heading=h.pkauxqlap12e)).

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/TextSymbolizerClass](http://www.opengis.net/spec/symbology/2.0/req/style/LineSymbolizerExtension)[/PerpendicularOffset**
**](http://www.opengis.net/spec/symbology/2.0/req/LinePerpendicularOffset)**Requirement Txt:** Implementations shall support the encoding of the added property of the TextSymbolizer extension and meet all of the tabulated constraints and notes.

For a TextSymbolizer, the extension  has the same meaning as for LineSymbolizer and for AreaSymbolizer, but can be ignored for punctual geometry. Before symbolizing the geometry into a text label, the geometry is transformed according to a perpendicular offset which produces a parallel line. The text label is then drawn according to that parallel line. 

## Property extensions

### LineProperties

**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/LineProperties 

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore



**Description:** The extension extends the PenStroke class with two properties LineJoin and LineCap used to define the the line style. 



| **Name** | **Definition**                                               | **Data type and value** | **Multiplicity** |
| -------- | ------------------------------------------------------------ | ----------------------- | ---------------- |
| lineJoin | Type of joining at the corners between the line segments (c) | LineJoin code           | zero or one      |
| lineCap  | Type of cap to be used at the two ends of an open line (c)   | LineCap code            | zero or one      |



**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/PenStrokeClass/LineJoinProperty 

**Requirement Txt:** Implementations shall support the encoding of all properties of the LineJoinProperty extension and meet all of the tabulated constraints and notes.

The extension introduces a code list used to define the the line style. The semantic of LineJoin is similar to their SVG equivalents. It includes the following codes : mitre, round and level.

| **Name**  | **Definition**                                               | **Data type and value**               | **Multiplicity** |
| --------- | ------------------------------------------------------------ | ------------------------------------- | ---------------- |
| lineJoin  | Type of joining at the corners between the line segments (c) | Literal data typeDefault value: mitre | one              |
| extension | Any encoding should allow the user to extend the codelist to include custom items | Any                                   | zero or more     |



**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/PenStrokeClass/LineCapProperty 

**Requirement Txt:** Implementations shall support the encoding of all properties of the LineCapProperty extension and meet all of the tabulated constraints and notes.

The extension introduces a code list used to define the the line style. The semantic of LineCap is similar to their SVG equivalents. It includes the following codes : butt, round and square.

| **Name**  | **Definition**                                               | **Data type and value**              | **Multiplicity** |
| --------- | ------------------------------------------------------------ | ------------------------------------ | ---------------- |
| lineCap   | Type of cap to be used at the two ends of an open line (c)   | Literal data typeDefault value: butt | one              |
| extension | Any encoding should allow the user to extend the codelist to include custom items | Any                                  | zero or more     |



### DashProperties

**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/DashProperties 

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Description:** The extension extends the PenStroke class with two properties DashArray and DashOffset used to manage dash values on a line.



**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/PenStrokeClass/DashArrayProperties

**Requirement Txt:** Implementations shall support the encoding of all properties of the DashArrayProperty extension and meet all of the tabulated constraints and notes.

| **Name**  | **Definition**                | **Data type and value**                                      | **Multiplicity** |
| --------- | ----------------------------- | ------------------------------------------------------------ | ---------------- |
| dashArray | Dash pattern to repeat (a)(b) | ParameterValue data type (Float) Value: ]0;+∞)Default value: unbroken line | zero or more     |

1. DashArray property is in the context of a UnitOfMeasure code (that may be inherited from a parent element).
2. The Dasharray property specifies a dash pattern as a sequence of floating values strictly positive. The first number gives the length of dash to draw, the second gives the amount of space to leave, and this pattern repeats. If an odd number of values is given, then the pattern is expanded by repeating it twice to give an even number of values.

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/PenStrokeClass/DashOffsetProperties

**Requirement Txt:** Implementations shall support the encoding of all properties of the DashOffsetProperty extension and meet all of the tabulated constraints and notes.

| **Name**   | **Definition**                                           | **Data type and value**                                      | **Multiplicity** |
| ---------- | -------------------------------------------------------- | ------------------------------------------------------------ | ---------------- |
| dashOffset | Offset into a dash pattern at which to start drawing (a) | ParameterValue data type (Float)Value: (∞;+∞)Default value: 0 | zero or one      |

1. DashOffset property is in the context of a UnitOfMeasure code (that may be inherited from a parent element).