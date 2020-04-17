**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/FeatureTypeStyle

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependencies:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Description:** The FeatureTypeStyle extension defines the styling that is to be applied to a single feature type.

**Requirement ID:** http://www.opengis.net/spec/symbology/2.0/req/FeatureTypeStyleClass

**Requirement Txt:** Implementations shall support the encoding of all parameters of the FeatureTypeStyleClass and meet all of the tabulated constraints and notes.

This class extends the abstract Style class described in the core. It defines the ability to portray a Layer built of N instances of GML AbstractFeatureType (Portele, 2007) with the ability to access features according to Simple Feature SF-2 (Van den Brink et al., 2012).

The rendering engine is driven according to the following execution: all features are applied to each symbolizer in sequence as they appear nested in rule and following the “painters model” with the first item in a list being the first item plotted and hence being on the “bottom”.

| **Name**        | **Definition**                                               | **Data type and value** | **Multiplicity** |
| --------------- | ------------------------------------------------------------ | ----------------------- | ---------------- |
| featureTypeName | Identifies the specific feature type that the feature-type style is for | Literal data type       | zero or one      |

To define the access to the exact feature type geometry to style, the extension adds a geometry property to the PointSymbolizer, LineSymbolizer, AreaSymbolizer and TextSymbolizer classes with the related behaviours (described below for each requirement).



**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/PointSymbolizerClass/Geomerty
**Requirement Txt:** Implementations shall support the encoding of the below added property to the PointSymbolizer class and meet all of the tabulated constraints and notes.

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/LineSymbolizerClass/Geomerty](http://www.opengis.net/spec/symbology/2.0/req/LineSymbolizerClass/Geomerty)

**Requirement Txt:** Implementations shall support the encoding of the below added property to the LineSymbolizer class and meet all of the tabulated constraints and notes.

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/AreaSymbolizerClass/Geomerty](http://www.opengis.net/spec/symbology/2.0/req/AreaSymbolizerClass/Geomerty)

**Requirement Txt:** Implementations shall support the encoding of the below added property to the AreaSymbolizer class and meet all of the tabulated constraints and notes.

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/TextSymbolizerClass/Geomerty](http://www.opengis.net/spec/symbology/2.0/req/TextSymbolizerClass/Geomerty)

**Requirement Txt:** Implementations shall support the encoding of the below added property to the TextSymbolizer class and meet all of the tabulated constraints and notes.

| **Name** | **Definition**                                               | **Data type and value**               | **Multiplicity** |
| -------- | ------------------------------------------------------------ | ------------------------------------- | ---------------- |
| geometry | Geometry attribute or sub-element of a geometry attribute (a) added to the Symbolizer | ParameterValue data type Geometry (1) | one              |

(1) from OGC 06-103r4 / [http://www.opengis.net/doc/IS/SFA/6.1.2](http://portal.opengeospatial.org/files/?artifact_id=25355)



