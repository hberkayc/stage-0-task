###Project 1###

echo "berkay"
mkdir berkay
mkdir biocomputing && cd biocomputing
wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.fna && wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk && wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk
mv wildtype.fna /content/berkay
rm wildtype.gbk.1
grep "tatatata" wildtype.fna 
grep "tatatata" wildtype.fna > mutant-lines.fna
grep -v "LOCUS\|DEFINITION\|ACCESSION\|VERSION\|KEYWORDS\|SOURCE\|ORGANISM\|COMMENT\|FEATURES\|ORIGIN" wildtype.gbk | wc -l
grep "LOCUS" wildtype.gbk 
grep "SOURCE" wildtype.gbk 
grep "/gene=" wildtype.gbk 
clear ; history > history.txt
ls /content/berkay ; ls /content/biocomputing

###Project 2###

conda activate base
   conda config --add channels defaults
   conda config --add channels bioconda
conda create -n funtools python=3.10
conda activate funtools
sudo apt-get install figlet
figlet Berkay Ç.
conda install -c bioconda bwa
conda install -c bioconda blast
conda install -c bioconda samtools
conda install -c bioconda bedtools
conda install -c bioconda spades
conda install -c bioconda bcftools
conda install -c bioconda fastp 
conda install -c conda-forge multiqc
