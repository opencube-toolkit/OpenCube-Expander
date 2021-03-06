OpenCube Expander
===============

The role of the OpenCube Expander component is:
+ to search for compatible cubes and 
+ to create a new expanded cube by merging two compatible cubes. 

###How it works

he OpenCube Expander is developed as a separate component of the OpenCube toolkit and is part of the �Data Expanding� lifecycle step. It supports the identification of compatible cubes stored either at the native triple store or at remote SPARQL end-points. The Expander can be initialized by creating a widget.

Widget configuration for use with the native triple store:

```
{{#widget: CubeSelection|asynch='true'}}
```

Widget configuration for use with the remote SPARQL end-point containing data for the 2011 Irish Census:

```
{{#widget:CubeSelection| sparqlService='<http://data.cso.ie/sparql>'| asynch='true' }}
```
 

###Functionality

The functionality of the OpenCube Expander is based:

+ On the links (dimensionValueCompatible and MeasureCompatible) created by the OpenCube Compatibility Explorer in order to detect external compatible cubes
+ On the aggregations (across a dimension and across a hierarchy) to detect compatible pre-computed aggregate cubes. The links enable the fast detection of the compatible cubes since no complex computations are made.
 

At the beginning the component presents the structure of the cube: i) the cube dimensions, ii) the values for each dimension and ii) the cube measures. Then the user can search for compatible cubes based on the following operations:

+ **Add measure**. This operation identifies and presents cubes that are compatible to add new measures to the original cubes i.e. associated cubes using the property MeasureCompatible.
+ **Add value to dimension**. In this case the user selects an expansion dimension and the operation identifies and presents compatible cubes that can be used to add new values to the selected dimension i.e. associated cubes using the property dimensionValueCompatible.
+ **Add hierarchy**. This operation identifies and presents cubes that are compatible to add a hierarchy to the original cube i.e. pre-computed aggregations across a hierarchy created by the OpenCube Aggregator (for simplicity reasons this functionality has been integrated to the OpenCube OLAP Browser).
+ **Add dimension**. This operation identifies and presents cubes that are compatible to add a dimension to the original cube i.e. pre-computed aggregations across a dimension created by the OpenCube Aggregator (for simplicity reasons this functionality has been integrated to the OpenCube OLAP Browser). 



