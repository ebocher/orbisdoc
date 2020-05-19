Style elements are stored in an encoding. An encoding is a concrete implementation of a set of style elements  (information or an instruction) into a particular form : a structured language,  a data format... Depending the type of encoding the style model could be readable for a human or/and only understandable by the machine.

A style encoding contains all the grammar and rules that the machine can understand to render in the same way a style model.

Two encodings are provided for the Feature2DStyle model :  XML and JSON. 

The table below 

|                    | XML                                                          | JSON                                                         |
| ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Root element       | <Feature2DStyle>                                             | "Feature2DStyle"                                             |
| Style elements     | All style elements, symbol extensions and their properties are stored as an XML element. e.g <PointSymbolizer>, <WellKnownName>, <SolidFill>... | All style elements, symbol extensions and their properties are stored as an JSON element. e.g "PointSymbolizer", "WellKnownName", "SolidFill"... |
| Literal            | Literal value is stored using default xml data types and facets : string, decimal, boolean  (see https://www.w3.org/TR/1999/WD-xmlschema-2-19990924/#built-in-datatypes) . String literal is always normalized  (see https://www.w3.org/TR/xml/#AVNormalize).  Complex literal as Array of string is flattened to a string representation. | Literal value is stored as in the four json data type : string, number, boolean and null (see https://tools.ietf.org/html/rfc7159).  Complex literal as Array of string is flattened to a string representation. |
| Expression         | Expression is a normalized string representation. A expression is specified with: expression(). eg. expression(CASE WHEN value =1 then 'good' else 'bad' end) | Expression is a string representation specified with : expression(). eg. "expression(CASE WHEN value =1 then 'good' else 'bad' end)" |
| Color              | The color data type is specified with a normalized string representation for the keyword <color>. The string representation of the color depends on the color extension. | The color data type is specified with a  string representation for the keyword "color". The string representation of the color depends on the color extension. |
| WellknownNameColor | The WellknownNameColor is a list of  color keywords as defined by X11 : https://en.wikipedia.org/wiki/X11_color_names e.g <Color>purple</Color> . To use an expression uses the following form : <Color>expression(CASE WHEN value =1 then 'purple' else 'green' end) </Color>. The color names are case-insensitive | The WellknownNameColor is a list of  color keywords as defined by X11 : https://en.wikipedia.org/wiki/X11_color_names e.g "Color":"purple" . To use an expression uses the following form : "Color":"expression(CASE WHEN value =1 then 'purple' else 'green' end) ". The color names are case-insensitive |
| HexaColor          | The HexaColor is a hexadecimal notation specified by a ‘`#`’ immediately followed by  three or six   hexadecimal characters. e.g <Color>#ff0000</Color> . To set an expression uses the following form : <Color>expression(CASE WHEN value =1 then '#ff0000' else '#000000' end) </Color>. | The HexaColor is a hexadecimal notation specified by a ‘`#`’ immediately followed by  three or six   hexadecimal characters. e.g "Color":"#ff0000" . To set an expression uses the following form : "Color":"expression(CASE WHEN value =1 then '#ff0000' else '#000000' end) ". |
| RGBColor           | The RGBColor  is ‘`rgb(`’ followed by a comma-separated list of three   integer values. e.g <Color>rgb(0,0,0)</Color>. rgb element supports expression definition in the form  : <Color>rgb(expression(CASE WHEN value =1 then 10 else 255 end),0,0)</Color> | The RGBColor  is ‘`rgb(`’ followed by a comma-separated list of three   integer values. e.g "Color":rgb(0,0,0). rgb element supports expression definition in the form  : "Color":"rgb(expression(CASE WHEN value =1 then 10 else 255 end),0,0)" |



Here two examples in XML and JSON.



```xml
<Feature2DStyle>
  <Name>Apply a color according the area of the input geometries</Name>
  <Rule>
    <Name>Area color expression</Name>
    <MaxScaleDenominator>10000.0</MaxScaleDenominator>
    <MinScaleDenominator>1000.0</MinScaleDenominator>
    <AreaSymbolizer>
      <Name>Color according a type</Name>
      <Uom>PX</Uom>
      <Level>0</Level>
      <PenStroke>
        <SolidFill>
          <Color>#000000</Color>
          <Opacity>1.0</Opacity>
        </SolidFill>
        <Width>0.25</Width>
        <LineCap>BUTT</LineCap>
        <LineJoin>MITRE</LineJoin>
      </PenStroke>
      <SolidFill>
        <Color>rgb(expression(CASE WHEN ST_AREA(the_geom)&gt; 1000 then 12 else 0 end),expression(15),expression(120))</Color>
      </SolidFill>
    </AreaSymbolizer>
  </Rule>
</Feature2DStyle>
```



```json
{
  "Feature2DStyle": {
    "Name": "Apply a color according the area of the input geometries",
    "Rule": {
      "Name": "Area color expression",
      "MaxScaleDenominator": 10000,
      "MinScaleDenominator": 1000,
      "AreaSymbolizer": {
        "Name": "Color according a type",
        "Uom": "PX",
        "Level": 0,
        "PenStroke": {
          "SolidFill": {
            "Color": "#000000",
            "Opacity": 1
          },
          "Width": 0.25,
          "LineCap": "BUTT",
          "LineJoin": "MITRE"
        },
        "SolidFill": {
          "Color": "rgb(expression(CASE WHEN ST_AREA(the_geom)> 1000 then 12 else 0 end),expression(15),expression(120))"
        }
      }
    }
  }
}
```

