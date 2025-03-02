# Music Album Knowledge Graph Project

This project creates an RDF knowledge graph from music album data, integrates it with DBpedia, and performs various analyses using SPARQL queries.

## Project Structure

```
.
├── data/                     # Contains CSV data files
│   ├── albumlist.csv         # Album metadata
│   └── rym_top_5000_all_time.csv  # Top 5000 albums data
├── 1.ttl                     # Output RDF graph in Turtle format
├── krr2_project.ipynb  # Main project notebook
└── requirements.txt          # Python dependencies
```

## Requirements

- Python 3.8+
- Required packages:
  - rdflib
  - SPARQLWrapper
  - owlrl
  - gdown
  - pandas
  - wikipedia-api


## Project Steps

1. **Create RDF Graph from CSV Data**
   - Loads album data from CSV files
   - Creates RDF triples for albums, artists, genres, and release dates
   - Uses custom and standard namespaces (DBpedia, RDF, RDFS)

2. **Integrate with DBpedia**
   - Extends local knowledge graph with DBpedia data:
     - Band members
     - Birth places
     - Founding locations
   - Uses SPARQL queries to fetch additional information

3. **Extract Information from Wikipedia**
   - Retrieves artist roles from Wikipedia summaries
   - Adds role information to the knowledge graph

4. **Create Ontology and Taxonomy**
   - Defines classes (Person, Band, MusicAlbum)
   - Creates genre taxonomy with subClassOf relationships
   - Adds domain and range constraints for properties

5. **Materialize Inferences**
   - Uses OWL reasoning to infer additional facts:
     - Genre inheritance
     - Type inference based on domains/ranges
     - Nationality inference for band members

6. **Query the Knowledge Graph**
   - Example SPARQL queries demonstrating:
     - Band member nationality analysis
     - Artist involvement in multiple bands
     - Genre popularity by country
     - Artist connections and collaborations

## Usage

1. Run the Jupyter notebook:
```bash
jupyter notebook krr2_project.ipynb
```

2. Execute cells sequentially to:
   - Download data
   - Build the knowledge graph
   - Integrate with DBpedia
   - Run analyses

## Example Queries

The notebook includes several example SPARQL queries that demonstrate:
- Finding bands with international members
- Identifying artists involved in multiple bands
- Analyzing genre popularity by country
- Discovering artist connections and collaborations

## Data Sources

- Album data from CSV files
- DBpedia for additional artist/band information
- Wikipedia for artist role information

## License

This project is licensed under the MIT License - see the LICENSE file for details.
