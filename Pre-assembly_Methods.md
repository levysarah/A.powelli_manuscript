## Pre-assembly Methods

#### Error corrected PE reads using Lighter (v1.1)

```./lighter -r R1_RRPN7-1_combined.fastq.gz -r R2_RRPN7-1_combined.fastq.gz -od /Pigweed_Assembly/RRP_Lighter -t 32 -k 21 500000000 .06```

#### Trim adapters and quality trim PE reads using Trimmomatic (v0.36)

```java -jar /home/tmdbio/Trimmomatic-0.32/trimmomatic-0.32.jar PE -threads 4 \
-trimlog /media/Sarah_Segate/Pigweed_Assembly/RRP_Trimmomatic_Trimmed/RRP_Trimlog.fa \
/media/Sarah_Segate/Pigweed_Assembly/RRP_Lighter_ErrorCorrected/R1_RRPN7-1_combined.fastq.cor.fq.gz /media/Sarah_Segate/Pigweed_Assembly/RRP_Lighter_ErrorCorrected/R2_RRPN7-1_combined.fastq.cor.fq.gz \
/media/Sarah_Segate/Pigweed_Assembly/RRP_Trimmomatic_Trimmed/output_forward_paired_R1_RRP.fastq.gz /media/Sarah_Segate/Pigweed_Assembly/RRP_Trimmomatic_Trimmed/output_forward_unpaired_R1_RRP.fastq.gz \
/media/Sarah_Segate/Pigweed_Assembly/RRP_Trimmomatic_Trimmed/output_reverse_paired_R2_RRP.fastq.gz /media/Sarah_Segate/Pigweed_Assembly/RRP_Trimmomatic_Trimmed/output_reverse_unpaired_R2_RRP.fastq.gz \
ILLUMINACLIP:/home/tmdbio/SEL_DATA/barcodes.fa:2:30:10 \
SLIDINGWINDOW:4:2 \
LEADING:2 \
TRAILING:2 \
MINLEN:25```