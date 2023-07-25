# PHYQUS: <i>Automatic Unit Conversions Approach for Wikidata Physical Quantities</i>

## Description
PHYQUS is an approach to automatic unit conversion of Wikidata Physical Quantities. PHYQUS performs the conversions on demand taking into account the units of measurment that are neccesary to answer a query.

## Input parameters
PHYQUS program takes as inputs:

* --conf: A valid JSON with the execution information details below
* --unzip: A flag to indicate that the inference should be decompressed, compression is useful for big datasets 

### The config JSON file should contain the following values:
```javascript
{
  "experimentName": "Dependency ANRs Cities",
  "rootPath": "/home/",
  "graphPath": "my_graph.ttl",
  "shapePath": "my_shape.ttl",
  "queryPath" : "my_query.sparql",
  "outInferencePath" :"inference_graph.ttl",
  "outReportPath": "report.ttl",
  "outResultSet" : "results_set.csv",
  "outShape" : "rewrite_shape.ttl",
  "method" : options=["VIRTUAL"]
}
```

## Running PHYQUS in the command line
```
java  -jar PHYQUS-1.0.jar --config "myconf.json" --unzip
```
## Outputs 
PHYQUS provide three outputs:
* an inference graph in format RDF Turtle
* a rewritting of the graph shape containing the conversion rules
* query results in tabular CSV format
* a report containing the execution time and the sizes of the inputs along with further details.

## Experiments
For the experiments we use samplings from  wikidata:
* [Wikidata](https://www.wikidata.org/)  

This repository contains two folders: 

* area_test folder 
* bioling_point_test folder

Each test contains an example of how to run it.

## Used technologies
* Apache Jena version 4.3.2
* SHACL-API version 1.4.2
* QUDT Ontology


