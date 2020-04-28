# sbx_gene_clusters

Reads-level based alignment to gene clusters of interest, e.g. bai operon or butyrate producing genes. Please refer to [sunbeam_database](https://github.com/zhaoc1/sunbeam_databases.git) for details. 

Take [**UniRef50** database](https://www.uniprot.org/downloads) as an example. First download the uniref50.fasta into your current `sunbeam_output/mapping/sbx_gene_clusters/databases/`.

 ```bash
 mkdir -p sunbeam_output/mapping/sbx_gene_clusters/database/
 wget ftp://ftp.uniprot.org/pub/databases/uniprot/uniref/uniref50/uniref50.fasta.gz -P sunbeam_output/mapping/sbx_gene_clusters/database/
 ```
 Second, update the `genes_fp` variable in `config.yml` with the proper path.

## Usage

 With your [sunbeam](https://github.com/sunbeam-labs/sunbeam) conda environemnt activated, 
 
 1. Clone into your Sunbeam extensions directory:
 
  ```bash
  git clone https://github.com/scottdaniel/sbx_gene_clusters
  ```
  
 2. Add the new config options to your config file
 
  ```bash
  cat sunbeam/extensions/sbx_gene_clusters/config.yml >> sunbeam_config.yml
  ```
  
 3. Run time

 - Use diamond
 
  ```bash
  sunbeam run --use-conda --configfile sunbeam_config.yml all_gene_family
  ```

Note: --use-conda will instruct sunbeam/snakemake to use the sbx_gene_clusters_env.yml to properly install dependencies into a conda environment
 
