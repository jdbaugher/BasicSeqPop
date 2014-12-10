BasicSeqPop
===========

### Creating simulated populations of sequence reads for sampling

These scripts can be used to create populations of sequencing reads from which random samplings of reads can be drawn. The scripts accompany an upcoming peer-reviewed journal article. Additional details will be provided as they become available.

## Requirements
This workflow has been tested on MACOSX and linux operating systems using recent versions of R.

#### R libraries:
    Biostrings
    optparse

## Usage

#### simulate_population.Rscript

  This script can be used to create a population of reads, including multiple haplotypes
  (unrelated) and incorporating an error rate for base calls.
	
	Rscript simulate_population.Rscript [options: e.g. --name=Sim_Pop --nreads=10000]


	Options:
	--name        The desired name of the simulated population [default = sim_pop]
	--nreads      The number of reads in the population [default = 10000]
	--width       The width of the simulated alignment [default = 300]
	--err         The simulated error rate probability at each position [default = 0.01]
	--haps        The number of unrelated baseline haplotype sequences [default = 2]
	--hap_probs   A comma-separated list of the probability of a read belonging to each haplotype (no spaces) 
	                [default = 0.5,0.5]
	--samples     The number of samples [default = 1]
  	-g, --gap     Indicates whether to include gaps as valid symbols in the simulated sequences 
                  	[default = FALSE]
	-n, --n       Indicates whether to include Ns (missing data) as valid symbols in the simulated sequences 
	                [default = FALSE]
	-h, --help    Show this help message and exit
	
	
#### create_random_samples.Rscript

  This script can be used to create samples consisting of reads randomly drawn from the simulated population. 
	
	Rscript create_random_samples.Rscript [options: e.g. --file=Sim_Pop.fasta --nreads=100]


	Options:
	--file        The name of the fasta-formatted input file[default = ""]
	--nreads      The number of reads in each sample [default = 100]
	--samples     The desired number of samples of randomly drawn reads [default = 100]


## Authors

Joseph D. Baugher, Ph.D. and Fernando J. Pineda, Ph.D.<br>
Copyright (c) 2014 Joseph D. Baugher, Ph.D.

## Maintainer

Joseph D. Baugher, Ph.D., jbaughe2(at)jhmi.edu

