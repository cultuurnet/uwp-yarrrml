# Transform input data to RDF/OSLO using YARRRML mapping files

## create-graph-with-yarrrml notebook
python notebook that:
* declares input and output variables
* introduces a function to transform yarrrml to rml
* introduces a function to generate a graph using morph-kgc engine

## folder structure explained
### input-data
* declare variables used in the yarrrml mapping file
* prep data : clean, transform, split...
* these examples use csv files for simplicity but other input data formats for morph-kgc engine are available:
    * Relational databases: MySQL, PostgreSQL, Oracle, Microsoft SQL Server, MariaDB, SQLite.
    * Tabular files: CSV, TSV, Excel, Parquet, Feather, ORC, Stata, SAS, SPSS, ODS.
    * Hierarchical files: JSON, XML.
    * In-memory data structures: Python Dictionaries, DataFrames.
    * Cloud data lake solutions: Databricks.

### yarrrml-data
* create mappings for every entity/class
* sources : set path to input data file
* graph : generates named graph n-quads output
* s : subject uri (use 'null' to generate blank node (avoid when possible))
* po : predicate-object mappings

### rml-data
* convert YARRRML file to rml using yatter => morph-kgc does not support generating n-quads output when a yarrrml file is used (BUG)

### config
morph-kgc config ini file
* CONFIGURATION
    * output_file: specify path to output-data file
    * output_format : overwrite default n-triples to n-quads when using named graphs
* DataSource
    * mappings: path to rml file

### output-data
* generated graph is stored here