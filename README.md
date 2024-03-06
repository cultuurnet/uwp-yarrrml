# Transform input data to RDF/OSLO using YARRRML mapping files

## input-data
* declare variables used in the yarrrml mapping file
* prep data : clean, transform, split...
* these examples use csv files for simplicity

### possible input data formats for morph-kgc engine:
* Relational databases: MySQL, PostgreSQL, Oracle, Microsoft SQL Server, MariaDB, SQLite.
* Tabular files: CSV, TSV, Excel, Parquet, Feather, ORC, Stata, SAS, SPSS, ODS.
* Hierarchical files: JSON, XML.
* In-memory data structures: Python Dictionaries, DataFrames.
* Cloud data lake solutions: Databricks.

## yarrrml-data
* create mappings for every entity/class
* sources : set path to input data file
* graph : generates named graph n-quads output
* s : subject uri (use 'null' to generate blank node (avoid when possible))
* po : predicate-object mappings

## rml-data
* convert YARRRML file to rml using yatter => morph-kgc does not support generating n-quads output when a yarrrml file is used (BUG)

## morph-kgc config
CONFIGURATION
* output_file: specify path to output-data file
* output_format : overwrite default n-triples to n-quads when using named graphs

DataSource
* mappings: path to rml file

## output-data
* generated graph is stored here