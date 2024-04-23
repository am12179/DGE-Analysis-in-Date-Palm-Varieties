Introduction: 


Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2) is the virus that causes
coronavirus disease 2019 (COVID-19). The COVID-19 outbreak originated in Wuhan, Hubei province,
China. It has since developed into a pandemic virus that nearly 124.0 Million people have contracted,
and 6.6 million people have died from(1). Severe acute respiratory syndrome is the virus that caused the
2002–2004 outbreak of SARS. In total, 8,098 people were infected within nearly 30 countries, and there
were approximately 774 deaths worldwide(2). The first known case of SARS was discovered in Foshan,
Guangdong, China, in mid-November 2002. Both viruses are from a closely related family of coronarviruses.
In this project, I identified orthologous genes and determined evolutionary rates of each gene in the SARS
and Covid-19 coronavirus genomes. dN, dS, and dN/dS are measures of evolutionary rates. dN is the
number of nonsynonymous (i.e., amino acid altering) changes between two sequences per nonsynonymous
site. dS is the number of synonymous (i.e., silent) changes between two sequences per synonymous site. dS is
often assumed to represent the neutral rate of substitution. dN/dS represents the ratio of non-synonymous
mutations per non-synonymous site (dN) to synonymous mutations per synonymous site (dS), and is the
rate of protein evolution.


Methods: My project was executed using whole genome data from SARS and Covid-19 at the National
Center for Biotechnology Information (NCBI) RefSeq genome collection. The software I used was R (version 4.2.2), Blast+ ( version 2.2.31+), Argtable(version 2.13), Clustal Omega (“clustalo”)(version clustalomega-1.2.4.), KaKs_Calculator (version 1.2), biomartr (version 1.0.2), and Ubuntu (version 22.04.1). Using
Ubuntu as the operating system on Linux by which I executed all of my commands, I first installed R into
my system. To install BLAST+, I extracted the compiled version of BLAST I retrieved from a web server,
and copied BLAST files to usr/local/bin. Following this, I retrieved the argtable from a server, extracted
the file from the folders then ran the system from inside argtable2-13 folder and installed argtable libraries
in /usr/local/lib. I repeated the same steps I used for argtable for my clustal omega download. Then,
I retrieved the KaKs_Calculator file from a web servers, unzipped the file, installed it, and opened the
folder. While inside this folder, I used vim base.h to edit “include<string.h>” into KaKs_Calculator. I
finally saved and quit the file. For my next step, I downloaded several dependencies (“libfreetype6-dev”,
“libpng-dev”,“libtiff5-dev”, “libjpeg-dev”) for devtools to run. I loaded R, then installed devtools using
install.packages(“devtools”). To download orthologr, I Installed package dependencies (“Biostrings”, “GenomicRanges”, “GenomicFeatures”, “Rsamtools”, “rtracklayer”,“IRanges”). Next, I installed metablastr
from GitHub and orthologr from GitHub. After, I installed a core Bioconductor package “BiocManager”,
installed package dependencies which were “Biostrings” and “biomaRt”, and finally installed “biomartr”.
Subsequently, I loaded orthologr and biomartr library. I used the biomartr package to download the CDS
sequences for SARS and Covid-19. I created a function to compute dN/dS values for covid-19 versus SARS.
In this function, I first labeled the query species (SARS) and a subject species (covid-19). Then, I used the
orthologr R package to identify orthologs using reciprocal best hit (“RBH”) approach, aligned my multiple
alignments with Clustal Omega, ran pal2nal to convert protein alignments back to nucleotide alignments,
estimated dN, dS and dN/dS using Comeron’s method from multiple sequence alignments, and finally set
my multi-core processing comp_cores to equal 1. Lastly, I stored the results in an Excel readable .csv file.
To identify which gene in my analysis corresponds to the Spike protein, I utilized NCBI website. To find the
websites for these two reference genomes, I went to NCBI (https://www.ncbi.nlm.nih.gov/) and searched “All
1
Databases” for “GCF_009858895.2” (Covid-19 reference genome) and “GCF_000864885.1” (SARS reference
genome). I then clicked on the main link in the “Genome” section at the top of the search result. To find
the gene names, I searched the GenBank formatted files for each genome to get detailed gene and other
information. On the main genome assembly page for Covid-19, I found the GenBank formatted files under
the “Chromosomes” section of the genome pages and clicking on the link under “RefSeq”


Discussion: The predominant mode of selection acting on viral genes in my analysis was purifying selection.
Purifying selection is a type of selection that reduces the probability of fixation of a deleterious allele. The
low dN/dS value (< 1) for the orthologous gene pairs from the Covid-19 and SARS genome indicates that
these genes are under strong purifying selection. The Covid-19 subject_id result displayed in column B in
the Figure 1 Query Table, cl|NC_045512.2_cds_YP_009724390.1_3, is the surface spike glycoprotein in
Covid-19. The Spike glycoprotein is what regulates fusion to the host membrane, and releases the virus to
the cytoplasm using intracellular receptors(3). The dN is 0.155, dS is 1.368 and dN/dS value is 0.1133 for
this critical gene. dS > 1 means that on average, more than one mutation has accumulated at the same site,
and the orthologous gene pairs from the Covid-19 and SARS genome that show dS > 1 are the surface Spike
glycoprotein and the ORF1a polyprotein. Thus, we can ascertain that one reason the Spike glycoprotein and
ORF1a polyprotein genes differ in evolutionary rate in comparison to other protein coding genes, is because
purifying selection is eliminating non-synonymous mutations at a faster rate than synonymous mutations.


Works Cited
1) World Health Organization. (2022, December 19). “WHO Coronavirus (COVID-19) Dashboard.”
Retrieved from https://covid19.who.int/
2) Lam WK, Zhong NS, Tan WC. Overview on SARS in Asia and the world. Respirology. 2003 Nov;8
Suppl(Suppl 1):S2-5. doi: 10.1046/j.1440-1843.2003.00516.x. PMID: 15018125; PMCID: PMC7159403.
3) Huang, Y., Yang, C., Xu, Xf. et al. Structural and functional properties of SARS-CoV-2 spike protein:
potential antivirus drug development for COVID-19. Acta Pharmacol Sin 41, 1141–1149 (2020). https:
//doi.org/10.1038/s41401-020-0485-4
