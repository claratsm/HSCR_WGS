# HSCR_WGS
Summary statistics for genetic analysis on HSCR WGS (Tang et al. submitted), including

1. Results of common variant association analysis for low frequency and common variants (MAF>1%)
2. Results of gene-based rare variant burden test
3. VCF file of rare variants included in rare variant burden test
4. Annotation of 4985 protein-truncating ultra-rare variants

## 1. Common variant association analysis
#### (n7224k.gwas_var-maf01.rvtests.MetaScore.SingleWald.chr*.assoc.gz[.tbi])

- Performed using [rvtests](https://github.com/zhanxw/rvtests)
- Bgzipped using [bgzip](http://www.htslib.org/doc/bgzip.html) and indexed using [tabix](http://www.htslib.org/doc/tabix.html)
- Score test results using `--meta score,cov` that could be used for meta-analysis
  - N_INFORMATIVE: Number of samples that are analyzed for association.
  - AF: Overall allele frequency. 
  - INFORMATIVE_ALT_AC: The number of alternative alleles in the analyzed case-control samples.
  - CALL_RATE: The fraction of non-missing alleles.
  - HWE_PVALUE: Hardy-Weinberg equilibrium p-values for controls. 
  - N_REF/N_HET/N_ALT: Number of samples carrying homozygous reference/heterozygous/homozygous alternative alleles. 
  - ALT_EFFSIZE: Estimated log odds-ratio for binary outcome. 
  - PSCORE : Score test p-values.
- Wald test results using `--single wald`
  - PWALD : Wald test p-values.
  
## 2. Rare variant association analysis
#### (n11898.RV-CMC-burdenTest.assoc)

- Performed using [rvtests](https://github.com/zhanxw/rvtests)
- Combined and Multivariate Collapsing (CMC, Li and Leal, 2008) test results using `--burden cmc`
  - Geneset : Gene being tested.
  - NALT : The number of variants with alternative rare alleles in the analyzed case-control samples.
  - NSAMPLES : The number of samples with at least one alternative rare alleles in the analyzed case-control samples.
  - CMC_P : CMC p-values.
  - ExACmissenseZ : ExAC missense z-scores as measures of the intolerance of the genes to missense changes.
  
## 3. VCF file of rare variants included in rare variant burden test
#### (autosomes.RVburdenTest.vcf.gz[.tbi])

- Bgzipped using [bgzip](http://www.htslib.org/doc/bgzip.html) and indexed using [tabix](http://www.htslib.org/doc/tabix.html)
- Information of columns are specified in the header <INFO= > fields, which are briefly described as follows:
  - AC : Allele count in genotypes for each ALT allele
  - AF : Allele Frequency for each ALT allele
  - AN : Total number of alleles in called genotypes
  - HSCR_AF : Allele Frequency, for each ALT allele, in the S-HSCR cases
  - CTRL_AF : Allele Frequency, for each ALT allele, in the controls
  - maxDBmaf : Maximum minor allele frequency (MAF) across all public databases, including 1000G, ExAC v0.2 and ESP
  - FUNCTION : Annotated function of the variant
  - GENE : Annotated gene for the variant

## 4. Protein-truncating ultra-rare variants annotation
#### (n4985.ProteinTruncating_URVs.annot.txt)

- Annotated using [KGGseq](http://grass.cgs.hku.hk/limx/kggseq/)
- Reference : hg19
  - Chromosome : Chromosome.
  - StartPositionHg19 : Position.
  - ReferenceAlternativeAllele : Reference/alternative alleles.
  - rsID : DbSNP ID 138 [. : not present].
  - MostImportantFeatureGene : Gene in which the protein-truncating variants mapped to.
  - MostImportantGeneFeature : Function of the variants.
  - RefGeneFeatures : Function of the variants with respect of RefSeq transcripts.






