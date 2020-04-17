<p align="left">
  <img alt="OGC" width="70px" src="./assets/images/ogc_new_logo.png" />
</p>

The SWG work that led to SymCore (Symbology conceptual core standard) proposal has been done in the continuation of the [Symbology Encoding standard](https://www.ogc.org/standards/se) (SE 1.1). 
While ​portrayal ​concerns the complete picture of what can be called a“cartographic ecosystem”, the description of ​
symbology ​rules rather concerns the subpart of it about the instructions to be applied by a rendering engine 
to symbolize geodata. That’s why this proposal has a focus on symbology versus concerns close to [Web Map Service](https://www.ogc.org/standards/wms) (WMS) 
[Style Layer Descriptor profile](https://www.ogc.org/standards/sld) (SLD) considerations. In other words, while a set of “layer ​style​” describe the links 
between some geodata and some styles to build a map, each of these styles are built of a set of symbology rules 
in accordance with SymCore.The overall motivation that lead to this proposal is related to 
the issue “​how to make richer the symbology abilities​”. 

**The first** answer is modularity which comes with extensibility. SE 1.1 is not modular per se, while this proposal 
is designed to be so with a core model extensible to host the diversity of such abilities in relation to various data models. 
It means that the core model is somewhat abstract and does not define concrete visualisations 
(e.g. red dashed line of wide thickness to draw features of type cable car).

**The second** answer that follows from the first is about extensions. As soon as the conceptual basis is set out in a 
specification document (this proposal), then extensions have to document the concrete symbology concepts to portray 
geodata structured according to a given data model. It is worth to notice that conceptually the core model is not related 
to any specific underlying data model to represent. It is up to an extension to define styling abilities in relation to 
a specific data model(e.g 2DFeatureTypeStyle).

**Third** answer is about encodings. As soon as the conceptual basis is set out, extensions packaged,then it is to define 
encodings to format the concrete conceptual symbology abilities.

In summary, SymCore concerns the first answer with a consistent approach to:

   - provide the flexibility required to achieve adequate symbology rules for a variety ofinformation communities; 
    e.g. aviation symbols, weather symbols, thematic maps, etc, and;
   - achieve a high level styling interoperability without encoding dependencies. 
    
As a consequence, SymCore follows the same motivation that split up SLD 1.0 (SLD 1.1 andSE 1.1). It is to put 
together parts that are not specific to any service (e.g. WMS), that is to be independent, and to allow the concepts 
to be reused by other standards willing to address aspects related to cartography. 
So a more general and portable symbology model is proposed for use across the broad OGC standards baseline, to be applied 
to geospatial datasets as well as online geospatial data and mapping services.
 
 Potential implementations of SymCore are expected to enhance OGC standards such as the [Web Map Service](https://www.ogc.org/standards/wms), 
 [Web Feature Service](https://www.ogc.org/standards/wfs), [GeoPackage](https://www.ogc.org/standards/geopackage), and others. By sharing a common core, and using an extension mechanism, integration of 
 these standards for the purposes of cartographic representation could be greatly simplified.
 
 Check the SymCore document [here](https://portal.opengeospatial.org/files/89616)
 
 > Olivier Ertz, [Media Engineering Institute](https://heig-vd.ch/rad/instituts/mei) and Erwan Bocher, LAB-STICC - [CNRS](https://www.cnrs.fr), october 2019