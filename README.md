# HSCR_WGS
Summary statistics for genetic analysis on HSCR WGS (Tang et al. submitted), including

1. Results of common variant association analysis for low frequency and common variants (MAF>1%)
2. Results of gene-based rare variant burden test
3. VCF file of rare variants included in rare variant burden test
4. Annotation of 4985 protein-truncating ultra-rare variants

## Common variant association analysis (n7224k.gwas_var-maf01.rvtests.MetaScore.SingleWald.chr*.assoc.gz)

- Performed using rvtests (https://github.com/zhanxw/rvtests)
- Score test results using --meta score,cov
-- 

N_INFORMATIVE: Number of samples that are analyzed for association.
AF: allele frequency. For related individuals, we use BLUE estimator. For case-control study, we list overall frequency (adjusted by relatedness if possible), case frequency and control frequency separated by a colon.
INFORMATIVE_ALT_AC: The number of alternative alleles in the analyzed samples.
CALL_RATE: The fraction of non-missing alleles. For case-control study, we calculate call rate for all samples, case samples and control samples separated by a colon.
HWE_PVALUE: Hardy-Weinberg equilibrium. For related individuals, this statistic can be inflated. For case-control study, we calculate HWE pvalues for all samples, case samples and controls samples separated by a colon.
N_REF/N_HET/N_ALT: Number of samples carrying homozygous reference/heterozygous/homozygous alternative alleles. For case-control study, we calculate these three statistics for all samples, case samples and controls samples separated by a colon.
U_STAT, SQRT_V_STAT: U and V statistics are score statistics and their covariance matrix. Details can be found in Dajiang Liu (2014) Nature Genetics.
ALT_EFFSIZE: for continuous outcome, this is the estimated effect size; for binary outcome, this is the estimated log odds-ratio. We apply a new correction method when binary trait associations for related individuals are analyzed in standard linear mixed models. The log odds ratio is approximately correct for related individual analysis as well.

- Wald test P-value
