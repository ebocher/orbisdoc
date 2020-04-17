### AreaSymbolizer extension

**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/AreaSymbolizer

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/AreaSymbolizerClass](http://www.opengis.net/spec/symbology/2.0/req/style/AreaSymbolizerExtension)

**Requirement Txt:** Implementations shall support the encoding of all properties of the AreaSymbolizer extension and meet all of the tabulated constraints and notes.

An AreaSymbolizer is used to symbolize a geometry into an area including filling its interior and stroking its outline. It is typically used for a 2-dimensional geometry (e.g. Polygon).

| **Name** | **Definition**                          | **Data type and value** | **Multiplicity** |
| -------- | --------------------------------------- | ----------------------- | ---------------- |
| fill     | Filling style to draw the interior area | Fill data type          | Zero or one      |
| stroke   | Stroke style to draw the outline        | Stroke data type        | Zero or one      |

1. If a geometry has “holes,” then they are not filled, but the borders around the holes are stroked in the usual way if a Stroke parameter is mentioned. “Islands” within holes are filled and stroked, and so on. If a point is used, then a small, square, orthogonal-normal area should be constructed for rendering. If a line is used, then the line (string) is closed for filling (only) by connecting its end point to its start point, any line crossings are corrected in some way, and only the original line is stroked.
2. A missing Fill property means that the geometry will not be filled. A missing Stroke property means that the geometry will not be stroked. When both are used, the filling is rendered first and then the stroking rendered on top of the filling.

### LineSymbolizer extension

**Requirement class:** [http://www.opengis.net/spec/symbology/2.0/req/LineSymbolizer](http://www.opengis.net/spec/symbology/2.0/req/AreaSymbolizer)

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req//LineSymbolizerClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the LineSymbolizer extension and meet all of the tabulated constraints and notes.

The LineSymbolizer extension is used to symbolize a geometry into a stroke, typically along an 1-dimensional geometry, such as a LineString.   

| **Name** | **Definition**                | **Data type and value** | **Multiplicity** |
| -------- | ----------------------------- | ----------------------- | ---------------- |
| stroke   | Stroke style to draw the line | Stroke data type        | one              |

1. For a 0-dimensional geometry (e.g. point) the stroke is applied on a line of “epsilon” length (arbitrarily small) with a horizontal orientation centered on the rendered geometry with two end caps. For a 2-dimensional geometry (e.g. polygon) the stroke is applied on its closed outline as the line rendered with no end caps.

### PointSymbolizer extension

**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/PointSymbolizer

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/PointSymbolizerClass](http://www.opengis.net/spec/symbology/2.0/req/PointSymbolizerClass)

**Requirement Txt:** Implementations shall support the encoding of all properties of the PointSymbolizer extension and meet all of the tabulated constraints and notes.

The PointSymbolizer extension is used to symbolize a geometry into a point at which a graphic is placed.

| **Name** | **Definition**               | **Data type and value** | **Multiplicity** |
| -------- | ---------------------------- | ----------------------- | ---------------- |
| graphic  | Graphic to draw at the point | Graphic data type       | One or many      |

1. For a geometry type other than 0-dimensional (e.g. a line, polygon) the semantic is to compute and use a representative interior central point as the point placement (i.e. guaranteed to lie on the line or the surface interior).

### TextSymbolizer extension

**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/TextSymbolizer

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/TextSymbolizerClass

**Requirement Txt:** Implementations shall support the encoding of all properties of the TextSymbolizer extension and meet all of the tabulated constraints and notes.

The TextSymbolizer extension is used to symbolize a geometry into text labels, whatever is the geometry type.

| **Name** | **Definition**                 | **Data type and value** | **Multiplicity** |
| -------- | ------------------------------ | ----------------------- | ---------------- |
| label    | Label text and styling details | Label data type         | One              |