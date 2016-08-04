## Post-assembly Methods

#### Assembly files used in QUAST and BUSCO runs
```
/spades_RRP/K21/final_contigs.fasta
/spades_RRP/K33/final_contigs.fasta
/spades_RRP/K55/final_contigs.fasta
/spades_RRP/K75/final_contigs.fasta
/spades_RRP/K127/final_contigs.fasta
/spades_RRP/K115/final_contigs.fasta
/spades_RRP/K123/final_contigs.fasta 
/soapdenovo/K101/RRP.k101.contig
/soapdenovo/bin/K103/RRP.k103.contig
/soapdenovo/bin/K113/RRP.k113.contig
/soapdenovo/bin/K127/RRP.k127.contig
/soapdenovo/bin/K63/RRP_pregraph.contig
/soapdenovo/bin/K83/RRP.k83.contig
/soapdenovo/bin/K91/RRP.k91.contig
/soapdenovo/bin/K93/RRP.k93.contig
/soapdenovo/bin/K97/RRP.k97.contig
/ABYSS_RRP/RRP_k125/RRP125-contigs.fa
/ABYSS_RRP/RRP_k128/RRP-contigs.fa
/ABYSS_RRP/RRP_k133/RRP_k133-contigs.fa
```
#### QUAST (v3.2)

###### Run for each assembly for comparison
```
quast.py -o /QUAST_RRP_New {list_all_assembly_files}
```
#### BUSCO - PLANT EARLY RELEASE (v1.1b1)

###### Obtain plant_early_release.tar.gz files via website request http://busco.ezlab.org/
###### Update dictonary on line 90 with plantae values
```
valid_clade_info = {'arthropoda':102785,'metazoa':91897,'vertebrata':143785,'fungi':174195,'example':102785,'bacteria':107114,'eukaryota':41317,'plantae':34011}
```
###### Run BUSCO individually for each assembly
```
python /BUSCO_v1.1b1/BUSCO_v1.1b1.py -o {output_filename} -in {fasta_assembly} -l /plantae -m genome -f
```
