# Genome Metadata Visualizer 
Genome Metadata Visualizer is a series of scripts written to process and visualise genome metadata after it is pulled from NCBI using the dataset and dataformat command line tools. Additional documentation for how to install and use NCBI's command line tools can be found at the following link: https://www.ncbi.nlm.nih.gov/datasets/docs/v2/download-and-install/

This repository contains the following: 

* ```/executable```: folder containing executable juyter notebook files as well as input data
   * ```AcquiringMetadata.ipynb```: contains documentation on how we ran NCBI's command line tools to pull spiralian genome data, followed by script to import it into python as a pandas dataframe and perform necessary edits/add additional information (including using biopython to find phylum based on taxid). Saves resulting pandas dataframe into metadata.csv to be used in following scripts. 
   * ```PlottingContigN50.ipynb```: filters ```metadata``` to take only the earliest entry for each species and plot it with respect to contig N50. Creates a count plot to show the number of sequences deposited per month. Creates a line plot on the same axis showing the cost of sequencing one megabase of human genome. 
   * ```Boxplot.ipynb```: taking the newest assembly for each species, filter out assemblies which do not meet a certain threshold if necessary. Grouping the metadata by phyla, plot the number of genome assemblies in a count plot and the sequence length and GC percent in box plots. 
   * ```helper_functions.ipynb```: file containing helper functons for other scripts. While this does not need to be opened manually or executed on its own, the other scripts have a ```%run helper_functions.ipynb``` command so this file needs to be accessable. 
   * ```metadata-sample.csv```: results from running NCBI's command line tools to pull spiralian metadata, followed by formatting. This file is formatted and ready to be plugged into either of the plotting scripts. Process shown under ```AcquiringMetadata.ipynb```.
   * ```spiralia_metadata_18apr2023.tsv```: raw NCBI metadata tsv output from 18th April 2023. 
   * ```sequencing_cost_data.csv```: cost of sequencing human genomic data with respect to time. Source: Wetterstrand KA. DNA Sequencing Costs: Data from the NHGRI Genome Sequencing Program (GSP) Available at: www.genome.gov/sequencingcostsdata. 
* ```/html```: contains the html versions of the jupyter notebook files which show our process with embedded results. 

Publication: 
Liao and Lu, et al. Spiralian genomics and the evolution of animal genome architecture, Briefings in Functional Genomics, 2023, elad029, https://doi.org/10.1093/bfgp/elad029

Sample output: 
![Contig N50 with respect to earliest assembly submission date](sample_output/Contig_n50_time.png)
![Sequence length and GC content of various spiralian phyla](sample_output/Phylum_counts.png)
