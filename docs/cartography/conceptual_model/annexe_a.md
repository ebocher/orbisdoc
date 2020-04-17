# Annexe A: more explanations (normative)

## ScaledRule

The MinScaleDenominator and MaxScaleDenominator properties of a Rule define the range of map-rendering scales for which the rule should be applied. They are simply the minimum and maximum ranges of scale (denominators) of maps for which a rule should apply. The minimum scale is inclusive and the maximum scale is exclusive. So, for example, the following scale range:

MinScaleDenominator = 100e3

MaxScaleDenominator = 1e6

corresponds to the logical condition :

scale_denom >= 100e3 && scale_denom < 1e6

Both of the elements are optional. The absence of a MinScaleDenominator property means there is no minimum-scale term to the condition or logically that the default value is 0. The absence of a MaxScaleDenominator property means that there is no maximum scale term to the condition of logically that the default value is infinity. So, the following scale constraint :

MinScaleDenominator = 100e3

corresponds to the logical condition:

scale_denom >= 100e3

There is a similar correspondence for MaxScaleDenominator property. The absence of both scale elements in a Rule mean that there is no scale constraint and that the rule is applicable to maps of all scales.

To insure consistent behaviour, scales must be handled consistently between map rendering engines. Scale is the ratio of a length unit in the map and its equivalent on the ground. The concept of scale has nothing to do with viewer client resolution, though given the mapping from a rectangular ground area to an equivalent array of pixels, the size of a pixel is required to determine the scale.

## FilteredRule

The Filter elements of a Rule allow the selection of features in rules to be controlled by conditions. The Filter data type has a relatively straightforward meaning conceptually defined in the Filter Encoding 2.0 specification. It allows both attribute (property) and spatial filtering (geometry). As a simple example, a Filter could be applied on a numerical attribute named “num_lanes” gives from the FeatureTypeStyle “Roads_FT” to select only road features that have four or more lanes.

If a rule has no Filter element, the interpretation is that the rule condition is always true, i.e., all features are accepted and styled by the rule.