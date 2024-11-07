## Project Overview

The **Music Knowledge Graph Generator** builds a knowledge graph that merges local tabular data about music albums and artists with additional structured data from DBpedia. It extends knowledge with information about band members, cities, countries of origin, and other relevant details by dynamically querying DBpedia and extracting roles from Wikipedia summaries.

### Key Features

1. **Data Integration and Enrichment**:
   - Loads and combines two CSV files containing music data (albums, artists, genres, ratings, etc.).
   - Constructs RDF triples to represent album, artist, and genre relationships.
   - Enriches the knowledge graph by querying DBpedia for additional information about artists and bands.
  
2. **Structured and Unstructured Data Fusion**:
   - Retrieves structured information about band members and places of origin from DBpedia.
   - Uses Wikipedia summaries to identify roles and instruments associated with band members, enriching the knowledge graph with unstructured data.

3. **Automated RDF Graph Construction**:
   - Adds RDF triples for albums, artists, genres, and band members, using custom namespaces and standard vocabularies like DBpedia (`dbp`), RDFS, and RDF.
   - Outputs the final knowledge graph as RDF, which can be queried using SPARQL.

## Prerequisites

Before running the project, ensure the following libraries are installed:

- `rdflib`
- `SPARQLWrapper`
- `owlrl`
- `gdown`
- `pandas`
- `wikipedia-api`

Install them using the following command:

```bash
pip install rdflib sparqlwrapper owlrl gdown pandas wikipedia-api
