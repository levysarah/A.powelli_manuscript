## Assembly Methods

#### ABySS-PE (v1.5.2)

###### Configure ABySS to run maximum kmer
```
./configure --enable-maxk=128 && make
sudo make install
```   
###### Bash script to run multiple ABySS assemblies
```
export k
for k in {47, 53, 59, 64, 77, 85, 121, 123, 125, 129, 135}; do 
	mkdir RRP_k$k
	abyss-pe j=8 v=-v -C RRP_k$k name=RRP$k in='output_forward_paired_R1_RRP.fastq.gz output_reverse_paired_R2_RRP.fastq.gz'
done
```
#### SPAdes (v0.10.13)
```
spades.py -k 55, 75, 115, 123, 125, 127 -t 5 --careful --only-assembler --pe1-1 output_forward_paired_R1_RRP.fastq.gz --pe1-2 output_reverse_paired_R2_RRP.fastq.gz -o spades_RRP
```

#### SOAPdenovo2 (127mer version)
##### Run individually for kmers: 63, 83, 91, 93, 97, 101, 103, 113
###### Pregraph, uses configuration file
```
./SOAPdenovo-127mer pregraph -s RRP_ConfigFile -K {insert_kmer} -R -o RRP.{insert_kmer} 1>{insert_kmer}.pregraph.log 2>{insert_kmer}.pregraph.err
```
###### SOAPdenovo2 assembly
```
./SOAPdenovo-127mer contig -g RRP.{insert_kmer} -R 1>{insert_kmer}.contig.log 2>{insert_kmer}.contig.err 
```
