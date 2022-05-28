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


* Different type of genomic variants

    1. Indel
    2. CNV (homozygous deletion, hemizygous deletion, Gain)
    3. SV
    4. path seq(not human)

VCF format

header: what fileds our have in your records,
record: 

VCF for CNV

how cnv and SV data are stored?

SNP and indel

    * single genomoe in isolation: almost never useful( we could get mutation, but it may be sequnce error)
    * joint callset: (more confident on variants)
    * variant filter reduce the false positive, how ?

Genotype refinement improves GT quality?

funtional annotation: intron, upstream, downstream, 3primer_UTR

How to solve tumor heterogenity and contamination?

    * matched normal samples
    
    * panel of normals to remove systematic noise

CNV calling
    coverage --> normalized --> ...--> CNV

SV type

    duplicateion,tandem
    inverted
    dispered
    inversion
    translocation
    Complex, haring thing


# haplotypeCaller

    1. two step GVCF file (same format as vcf but has every genomic information)
    
    create GVCF per sample.  It have all the position in gemone (Why? multiple samples,).
    
    2.VQSQ tells us waht is good variants

    3. what is genotype refinement?

    * process: recalibrated variants -> variant postier qualityes -> variant filtering -> variant annotater

    4. evaluate the callse of downstream?

    5. fitering 
    
    * mutiple samples help a lot,()

# intro to somatic mutations
1. how somatic mutation calling is dfferent from germline mutation?
    
    * mix of tissues(not just tumors)


1. what is driver mutation


2. what is passenager mutation


3. tumor purity
 
    purity = tumor_cell/(normal_cell + tumor_cell)

5. tumor heterogenity

    plogenomic pupulations,segregated vor intermixed, subclonal evolution

6. noise 

    germiline : + AF expected to follow ploidy

    Somatic: other mutaition, heoterogenity,contamination,and noise

    Normal: Signal + Noise,

    Tumor , Signal + germ + noise

7. Tumor normal workflow

    substraction from germline mutation

8. Panel of Normals for SNV and indels

    * Eliminate common/recurring techinical artifacts

    * also eliminate germline variants not called in matched normal

9. Somatic CNV

    converage ->   Normlize to remove noise(based on reference,better from same platform)  -> identiy segment boundaries

    denoising is essential 

    Pnael of normals for CNVs





