# MoTTL transcriptor

This repository is only for review purposed at the EC3 conference, it has been anonymized (apparently, but it is not impossible to deanonymize if you are willing to find out...). The links in the paper will be replaced with the proper repository in the final version.

See conference paper: ANONYMIZED

## MoTTL-Transcriptor v.0.9

This component transcribes Modelica packages to knowledge graphs. It was developed as a Java tool and is delivered as a *.jar.

### How to use it
* download the executable *.jar from [https://github.com/anon2609/MoTTL-Transcriptor/releases/tag/v0.9.0]
* it contains all dependencies and can be run out of the box
* it can be executed on a JVM version 11 (or higher)
* run the following command to generate a turtle file representing some Modelica package (adapt the paths to your files)
```
java -Dpolyglot.engine.WarnInterpreterOnly=false -jar c:\MoTTL-Transcriptor-0.9-SNAPSHOT-jar-with-dependencies.jar -p "ex" -n "LBDCG_example" -t "knowledge graph representing the Modelica LBDCG_example package" -v "v1.0.1-1.0.0" -o "C:\output\path" --inputPath "c:\LBDCG_example"
```
you need to provided six parameters:
* inputPath i: path to directory containing the input package (package.mo, package.order) e.g. c:\\LibEAS (without trailing slash), use quotes if whitespaces contained 
* outputPath o: path to directory where the turtle file should be placed e.g. c:\\TMP (without trailing slash), use quotes if whitespaces contained
* prefix p: ontology prefix e.g. \"mbl\" (without colon and quotes)
* ontologyLongName n: e.g. \"Buildings\" (no quotes necessary)
* ontologyTitle t: e.g. Modelica Buildings Library (v8.0.0) ontology
* ontologyVersion v: combined version number of Modelica package and the ontology v8.0.0-1.0.0

### Examples
* example outputs (knowledge graphs in ttl serialization) for common libraries (AixLib, BuildingSystems, Modelica Buildings, Modelica Standard Library) are contained in the folder: ./src/main/resources/ontologies/8_ModelicaLibraries
* their native Modelica files are available on their respective github repositories
* an example input Modelica package is contained in the folder: ./src/test/resources/C_HeatPumpPlant
* the corresponding output is contained in the file: ./src/test/java/output/ex_20221215_1154_fullclean.ttl

### Dependencies
Through maven this code depends primarily on:
* ANTLR 4.8

### sources belonging to the EC3 paper
* MoOnt definition is given in this file: ./src/main/resources/ontologies/7_MoOnt/MoOnt.ttl
* the heat pump plant example (native Modelica Code) is given here: ./src/test/resources/C_HeatPumpPlant
* the corresponding output (knowledge graph in ttl serialization) is contained in the file: ./src/test/java/output/ex_20221215_1154_fullclean.ttl
* knowledge graphs in ttl serialization for common Modelica libraries (AixLib, BuildingSystems, Modelica Buildings, Modelica Standard Library) are contained in the folder: ./src/main/resources/ontologies/8_ModelicaLibraries
* python code to execute the queries described in section "Discussion and Result Analysis ??? Answering Competency Questions" are given here: ./test/EC3example_SPARQLqueries.py
* as discussed in the paper there are some implementation issues with CQ2, these are shown here: ./test/CQ2
* the outputs of these scripts are shown here (only excerpts are shown in the paper wrt page limitations): ./test/EC3example_SPARQLqueries_outputs.txt

### Contact
ANONYMIZED

### License and Copyright
no license granted, repository merely for review process within EC3 conference
