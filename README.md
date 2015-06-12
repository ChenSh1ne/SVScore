# SVScore
Prioritize structural variants based on annotations and C scores

Still under active development

# Usage
```
usage: ./svscore.pl [-dzas] [-c file] vcf
  -d	Debug (verbose) mode, keeps intermediate and supporting files
  -z	Indicates that vcf is gzipped
  -a	Indicates that vcf has already been annotated using vcfanno
  -s	Create/download supporting files and quit
  -c	Used to point to whole_genome_SNVs.tsv.gz

  vcf must be sorted naturally (e.g. chromosome 1, chromosome 2,...,chromosome 9, chromosome 10,...)
```

# Dependencies
* [vcfanno](https://www.github.com/brentp/vcfanno)

* whole_genome_SNVs.tsv.gz (and .tbi) - file of all possible hg19/GRCh37 SNVs and associated C scores from [CADD](http://cadd.gs.washington.edu/download) 

* Your favorite exon- and gene-describing BED files (optional). If you don't have any, svscore.pl will automatically download them (functionality courtesy of Colby Chiang). If using your own files, make sure they are naturally sorted

* [bedtools](https://www.github.com/arq5x/bedtools)


# Notes
SVScore creates a file of introns (unless a file called introns.bed already exists in the current directory) by subtracting the exon file from the gene file using bedtools
