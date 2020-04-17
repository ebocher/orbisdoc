Two rule extensions are provided : ScaledRule and FilterRule.

## ScaledRule

**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/ScaledRule 

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/RuleClass/ScaleDenominator](http://www.opengis.net/spec/symbology/2.0/req/ScaledRuleExtension)

**Requirement Txt:** Implementations shall support the encoding of all properties of the ScaledRule extension and meet all of the tabulated constraints and notes.

The ScaledRule extension extends the Rule class with two properties (MinScaleDenominator and MaxScaleDenominator) defining the range of map-rendering scales for which the rule should be applied. See some more explanations about [Annexe A - ScaledRule](cartography/conceptual_model/annexe_a.md).

| **Name**            | **Definition**                                           | **Data type and value**                                      | **Multiplicity** |
| ------------------- | -------------------------------------------------------- | ------------------------------------------------------------ | ---------------- |
| minScaleDenominator | Minimum of map scale range for which a rule should apply | ParameterValue data type (Float)Value: (0;+∞)Default value: 0 | zero or one      |
| maxScaleDenominator | Maximum of map scale range for which a rule should apply | ParameterValue data type (Float)Value: (0;+∞)Default value: +∞ | zero or one      |



## FilteredRule

**Requirement Class:** http://www.opengis.net/spec/symbology/2.0/req/FilteredRule 

**Scope:** All requirements in this subsection relate to the above requirement class.

**Dependency:** http://www.opengis.net/spec/symbology/2.0/req/symcore

**Dependency:** Filter Encoding 2.0

**Requirement ID:** [http://www.opengis.net/spec/symbology/2.0/req/RuleClass/Filter](http://www.opengis.net/spec/symbology/2.0/req/ScaledRuleExtension)

**Requirement Txt:** Implementations shall support the encoding of all properties of the FilteredRule extension and meet all of the tabulated constraints and notes.

The FilteredRule extension extends the Rule class with a property (Filter) to specify a filter mechanism. It is "used to identify a subset of resources from a collection of resources whose property values satisfy a set of logically connected predicates. If the property values of a resource satisfy all the predicates in a filter then that resource is considered to be part of the resulting subset (1) such as a subset of features to style by applying a given Symbolizer. An encoding shall offer a mechanism to select features according to a where clause using comparison and logical operators and additional functions (see ParameterValue subclause). More explanations about the filtering mechanism in [Annexe A - FilteredRule](cartography/conceptual_model/annexe_a.md).

| **Name** | **Definition**      | **Data type and value**         | **Multiplicity** |
| -------- | ------------------- | ------------------------------- | ---------------- |
| filter   | Filtering mechanism | Filter ParameterValue data type | zero or one      |

(1)  from http://www.opengis.net/doc/IS/FES/2.0/clause/7.1