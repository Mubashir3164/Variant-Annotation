 Variant-Annotation
(Customize Variant annotation with snpEff using your own data).
# make a directory  
mkdir Mydirectory
# Download snpEff
It can be downloaded from its website, here is the link
http://pcingola.github.io/SnpEff/se_running/
# unzip 
Unzip the downloaded snpEff files
# Example
Here I am using Gossypium hirsutum as an example for variant annotation.
There are pre-built databases in snpEff, you can check it with the following command

java -jar snpEff.jar databases
# Building database

download Gff and Fasta files from cottonFGD/Cottongen

https://cottonfgd.org/about/download/assembly/genome.Ghir.CRI.fa.gz
https://cottonfgd.org/about/download/annotation/gene.Ghir.CRI.gff3.gz

# Uzip Fasta and GFF files
gzip -d filename.gz
# Make a directory 
mkdir data/hirsutum           

Put the Gff and fasta genome file in hirsutum directory and rename as sequences.fa and genes.gff
# Edit snpEff.config file
To edit the config file you can use any linux commandline editor such as vi, and add hirsutum.genome at the end of it, then save it.  

vi snpEff.config
# To build database run the following command 
java -jar snpEff.jar build -gff3 -v hirsutum.genome

After sometime your database will be ready for variant annotation

# Annotating variant file 
Input file can be in vcf format 

Run the following command for variant annotation  

java -jar snpEff.jar ann hirsutum filename.vcf >out.ann.vcf

for more details visit 

http://pcingola.github.io/SnpEff/se_buildingdb/

# Reference 

"A program for annotating and predicting the effects of single nucleotide polymorphisms, SnpEff: SNPs in the genome of Drosophila melanogaster strain w1118; iso-2; iso-3.", Cingolani P, Platts A, Wang le L, Coon M, Nguyen T, Wang L, Land SJ, Lu X, Ruden DM. Fly (Austin). 2012 Apr-Jun;6(2):80-92. PMID: 22728672



