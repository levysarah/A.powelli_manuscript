## QC Methods

#### Check read quality using FastQC ()

```fastqc -t 4 R1_RRPN7-1_combined.fastq.gz R2_RRPN7-1_combined.fastq.gz```

#### Check read quality using SGApreQC 

###### Preprocess reads
```
sga preprocess --pe-mode 1 input_1.fastq input_2.fastq > my_genome.fastq
```
###### Preprocess reads
```
sga preprocess --pe-mode 1 'Raw_RRP_R1.fastq.gz' 'Raw_RRP_R2.fastq.gz' > RRP_genome.fastq
```
###### Index reads
```
sga index -a ropebwt -t 8 --no-reverse RRP_genome.fastq
```
###### Run PreQC
```
sga preqc -t 8 RRP_genome.fastq > RRP_genome.preqc
```
###### Build a report
```
/sga-master/src/bin/sga-preqc-report.py RRP_genome.preqc /sga-master/src/examples/preqc/*.preqc
```