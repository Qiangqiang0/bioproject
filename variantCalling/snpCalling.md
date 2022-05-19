# variant calling
 || germiline | somatic|
|-------|------|------|
 snp/indel | hap| mutect 
 copy number| gCNV| CNV + acnv 
 sv|SVDiscovery|--

# introduction
* how to get seq data?
samples -> library -> fastq 

* genome vs exome

* different exome kit produce analyzable coverage

* Qulity control

    Bad coverage, how to solve?
    chimerism: 
    insert size: too big or too small
    shearing-based oxidation (poor QxoQ value)
    library size too small: 

    Exomes: serve coverage
    Whole genomes: high propotion of unmapped reads

GC content interfere with data generation


# preprocess
there is no need to do quanlity trimming(calling would remove this) and adaptor removal(can be marked)

    1. fastq
    2. bam
    3. mark duplicate
    4. recalibrete
    5. analysis of bam


    pair end reads help align into the genome

CIGAR: tell us how reads are mapped into reference

unmapped bam vs mapped bam:
star for rna data and 
bwa for dna data

why mark dulicates? 
duplicates are reads duplicated(artifical side effects, artifacts)





