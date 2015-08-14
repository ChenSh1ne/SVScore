## 0.3 (Under development)
 * Performance improvement (fixed high memory usage bug)
 * Compatibility with vcfanno v0.0.7
 * Fixed off-by-one error in coordinates
 * Added -g, -e, and -n options to allow use of custom gene/exon annotation files
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
