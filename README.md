# protein-annotation-goatools
## Project description
The goal of this project is to provide a list of proteins associated with a search query, categorized by gene ontology terms - using the library goatools.
FASTA protein sequences of the organism (in this case _Stentor_: S_coeruleus_Nov2017_proteins.fasta) were annotated by eggnogmapper (http://eggnog-mapper.embl.de) so that every protein in the organism is annotated with GO terms, and other ortholog information.

## Folders
MM_0k__n476 and MM_ygb98ktq contain output files from eggnogmapper, the difference between them being the parameters used to conduct the ortholog search.
Parameters for MM_ygb98ktq are seed_evalue	0.001, seed_score	60, percen_ident	40, query_cov 20, subject_cov	20.
Parameters for MM_ygb98ktq are seed_evalue	0.001, seed_score	40, percen_ident	20, query_cov 20, subject_cov	20.

## Code

### python-magic 
Input files for the code are the annotated output from eggnogmapper. 
Their format is ascii text with very long lines (example: 'MM_ygb98ktq/out.emapper-2.annotations'). This code uses the python-magic library to convert ascii text into csv files. 

### Find_single_protein_annotations
Code displays the results of any input protein sequence if entered in the correct format (Eg SteCoe_1). Output is information about the orthologs, KEGG ortholog information, description, GO terms etc.

### GO analysis
This code uses goatools to provide all the GO terms associated with a particular search term (in this case eg. dynein). It iterates over the protein sequences to find all the sequences associated with the entered search term. Output is a dataframe containing the columns - GO Terms (corresponding to the search query), GO Term Description (providing the biological function) and Proteins corresponding to each GO Term.
