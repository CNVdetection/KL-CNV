KL-CNV
Kullback-Leibler divergence criterion in detecting genome-wide Copy Number Variations
By Seyed Amir Malekpour, Hamid Pezeshk and Mehdi Sadeghi

Input data to the KL-CNV are as follows:

1- Information relevant to the alignment of the mate pair reads from sample genome, after being aligned to the reference genome. This is a 3-column matrix in which each row represents the mapping position of the first read (in a mate pair) on the reference genome and its insert size and mapping orientation (flag number). An example input matrix which is named Info_ Sample is in the attached dataset.

2- Information relevant to the alignment of the mate pair reads from reference genome, after being aligned to the reference genome. This is a 3-column matrix in which each row represents the mapping position of the first read (in a mate pair) on the reference genome and its insert size and mapping orientation (flag number). An example input matrix which is named Info_Reference is in the attached dataset. After defining the above matrices in MATLAB, the genome-wide deletions and duplications are called by running the MAIN.m script. However, there are a few parameters which should be specified, in the first lines of this script: 

•	Chromosome size (in base pair)
•	The length of each read in mate pair reads (in base pair)
•	Average insert sizes in the sequencing library of the sample and reference genomes (in base pair)
•	The average number of reads in each cluster that is identified by the k-means algorithm
•	The maximum length of the CNVs which we aim to detect (in base pair)
•	Sample and reference genomes sequencing coverage

After running MAIN.m, genome-wide copy gain and copy loss regions which are called by KL-CNV will be shown in the MATLAB variable of “CNVs”. Each row of this matrix represents a different CNV call with its start position, end position and CNV type, in order. CNV types are encoded as follows: 2 for a copy loss region, 3 for a copy gain region (non-tandem duplication), 4 for a copy gain region (tandem duplication)
