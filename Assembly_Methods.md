## Assembly Methods

#### ABySS-PE

###### Configure ABySS to run maximum kmer
```
./configure --enable-maxk=128 && make
sudo make install
```   
###### Bash script to run multiple ABySS assemblies
```
export k
for k in 47, 53, 59, 64, 77, 85, 121, 123, 125, 129, 135; do 
	mkdir RRP_k$k
	abyss-pe j=8 v=-v -C RRP_k$k name=RRP$k in='output_forward_paired_R1_RRP.fastq.gz output_reverse_paired_R2_RRP.fastq.gz'
done
```
#### ABySS-PE