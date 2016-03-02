## 0.5 (Under development)
 * Use exact breakpoint representation of SVs in BEDPE (in conjunction with new version of svtools)
 * Calculate span scores between most likely bases
 * Calculate truncation scores for DELs
 * Treat MEIs like BNDs
 * Only calculate truncation scores for truncated genes, not all genes hit by variants which truncate a gene
 * Bug fixes/code improvements
 * Error handling
 * Modified temp file naming conventions
 * First attempt at insertion support

## 0.4 (11/12/15)
 * Account for regions of the genome which do not have CADD scores
 * Use vcfanno 0.0.8
 * Fixed sorting incompatibilities with vcfanno
 * Implemented -o TOP (mean of top n bases) and -o MEAN options
 * Added -t (number of bases to use in -o top), -p (gene file strand column), and -v (verbose) options
 * Removed exon annotation and -n (SVScore still requires an exon file to create intron file)
 * Added support for CNV and MEI variant types (treated as DELs/DUPs)
 * Replaced BND with TRX, BNDs still supported but only left/right breakend scores are calculated
 * Updated added header lines
 * Temporary files go in svscoretmp directory, which is deleted automatically (except under -d)
 * Made introns.bed filename more descriptive to avoid problems in switching between annotation systems in the same directory
 * Improved performance by returning a score of -1 for regions which are too big (above 1 Mb)
 * Added unit test
 * Allow for calculation of scores for variants reclassified to BND without changing the ALT field

## 0.3 (08/17/15)
 * Performance improvement (fixed high memory usage bug)
 * Use vcfanno v0.0.7 and CADD v1.3
 * Fixed off-by-one error in coordinates
 * Added -g, -e, -m, and -n options to allow use of custom gene/exon annotation files
 * Processes BND variants without mates, provided CIEND field is present
 * Updates VCF header with scores added to INFO field
 * Intermediate files are tagged with timestamp to prevent collisions from parallel instances
 * Automatically detects whether file is gzipped based on filename (removed -z option)
 * Always calls vcfanno (removed -a option)

## 0.2 (06/29/2015)
 * Outputs sorted VCF to standard output, no longer creates *.scored.txt file
 * Relaxed stringency on SVTYPE field
 * File prefix now disregards path prefix to always work in current directory
 * Removed natural sort requirement. SVScore now automatically sorts input VCF based on ID
 * Returns a negative score for variants in regions with no C scores (e.g. GL contigs)
 * Returns a score of 100 for deletions/duplications above 1 Mbp

## 0.1 (06/09/2015)
 * Initial commit
