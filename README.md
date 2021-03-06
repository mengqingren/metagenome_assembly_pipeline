# A pipeline for metagenomic assembly

A pipeline to go from raw sequencing data to high quality bins and pretty plots.

## Introduction

This is a simple pipeline for analyzing metagenomic data, starting from raw reads to assembly, to binning, to functional analysis. Throughout the pipeline, there 
will be example commands at each step - **however; replace the generic filenames and paths with your own data.**

Prior to getting started, look over the [software list](#exhaustive-list-of-software-used) and ensure all of it is installed. If you are using the lab machine 'entamoeba', the majority of software will be installed locally. For steps which require the ZCU (Zoology computing unit), you will need to install the software to your own folder if it is not already installed globally.

You can preview each step of the pipeline under the [overview](#overview) section.

## Important note about intermediate files

By default, each command here keeps intermediate files during analysis, in case you need to go back a step or need to verify something. However, some files can get **very large**, so please be mindful of the amount of disk space you are using (especially if you are on a lab machine). Can you quickly re-create the files if you need it later? If yes, then delete it.

## Overview

- [Section 0: Prelude][section0]
- [Section 1: File preprocessing][section1]
- [Section 2: Assembly][section2]
- [Section 3: Assembly quality evaluation][section3]
- [Section 4: Coverage][section4]
- [Section 5: Filtering contigs][section5]
- [Section 6: Binning][section6]
- [Section 7: Binning quality evaluation][section7]
- [Section 8: Binning, taxonomy and bin refinement in Anvi'o][section8]
- [Section 9: Functional annotation and basic plots][section9]
- [Section 10: Functional annotation with PROKKA and Krona plots][section10]

## Issues

Any issues or clarification needed can be raised by creating a new issue in this repository. Alternatively, you can email me at kevchan1@alumni.ubc.ca.

## Exhaustive list of software used

Note that many of these tools can be installed through [conda][conda-link] or [homebrew][homebrew-link]. Try those options first before a manual install.

### Quality metrics/visualization 

- [FastQC][fastqc-link]
- [MultiQC][multiqc-link]

### Data preprocessing

- [BBTools][bbtools-link]

### Read alignment (host removal, coverage, gene quantification)

- [bowtie2][bowtie2-link]
- [Picard][picard-link] 
- [htseq][htseq-link] 

### Assemblers

- [IDBA-UD][idba-ud-link] 
- [MetaSPAdes][metaspades-link]<sup>1,2</sup> (**NOTE:** may or may not work with your data, fix should be rolled out in v3.12.1) 

### Assembly evaluation

- [MetaQUAST][metaquast-link]

### Binning

- [CONCOCT][concoct-link] (built-in in Anvi'o) 
- [MetaBAT][metabat-link]<sup>1</sup> 
- [MaxBin2][maxbin2-link]<sup>1</sup> 

### Binning quality evaluation

- [CheckM][checkm-link]<sup>1</sup> 
- [Anvi'o][anvio-link] 

### Taxonomy assignment

- [Kaiju][kaiju-link]<sup>1</sup>

### Manual binning refinement

- [Anvi'o][anvio-link] 

### Functional annotation

- [PROKKA][prokka-link] 
- [MinPath][minpath-link] 
- [GhostKOALA][ghostkoala-link] 

### Functional annotation databases

- [COGs][cogs-link] 
- [KEGG][kegg-link] 

### Other

- [Samtools][samtools-link] 
- [Krona][krona-link] 
- [blast][blast-link] 
- [MEGAN][megan-link] 

### Legend

<sup>1</sup>: Linux/cluster use only <br/>
<sup>2</sup>: High memory usage

[conda-link]: https://conda.io/docs/user-guide/getting-started.html
[homebrew-link]: https://brew.sh/
[fastqc-link]: https://www.bioinformatics.babraham.ac.uk/projects/fastqc/
[multiqc-link]: http://multiqc.info/
[bbtools-link]: https://sourceforge.net/projects/bbmap/
[bowtie2-link]: http://bowtie-bio.sourceforge.net/bowtie2/index.shtml
[picard-link]: https://broadinstitute.github.io/picard/
[htseq-link]: https://htseq.readthedocs.io/en/release_0.10.0/overview.html
[idba-ud-link]: https://github.com/loneknightpy/idba
[metaspades-link]: http://cab.spbu.ru/files/release3.12.0/manual.html
[metaquast-link]: http://quast.bioinf.spbau.ru/manual.html
[concoct-link]: https://concoct.readthedocs.io/en/latest/
[metabat-link]: https://bitbucket.org/berkeleylab/metabat
[maxbin2-link]: https://downloads.jbei.org/data/microbial_communities/MaxBin/MaxBin.html
[checkm-link]: https://github.com/Ecogenomics/CheckM/wiki
[anvio-link]: http://merenlab.org/software/anvio/
[kaiju-link]: https://github.com/bioinformatics-centre/kaiju
[prokka-link]: https://github.com/tseemann/prokka
[minpath-link]: http://omics.informatics.indiana.edu/MinPath/
[ghostkoala-link]: https://www.kegg.jp/ghostkoala/
[cogs-link]: https://www.ncbi.nlm.nih.gov/COG/
[kegg-link]: https://www.kegg.jp/kegg/
[samtools-link]: http://www.htslib.org/
[krona-link]: https://github.com/marbl/Krona/wiki
[blast-link]: https://www.ncbi.nlm.nih.gov/books/NBK279684/
[megan-link]: https://ab.inf.uni-tuebingen.de/software/megan6
[section0]: section_0/
[section1]: section_1/
[section2]: section_2
[section3]: section_3
[section4]: section_4
[section5]: section_5
[section6]: section_6
[section7]: section_7
[section8]: section_8
[section9]: section_9
[section10]: section_10

