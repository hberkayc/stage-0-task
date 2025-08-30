###Project 1###

1. echo "berkay"
2. mkdir berkay
3. mkdir biocomputing && cd biocomputing
4. wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.fna && wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk && wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk
5. mv wildtype.fna /content/berkay
6. rm wildtype.gbk.1
7. grep "tatatata" wildtype.fna 
8. grep "tatatata" wildtype.fna > mutant-lines.fna
9. grep -v "LOCUS\|DEFINITION\|ACCESSION\|VERSION\|KEYWORDS\|SOURCE\|ORGANISM\|COMMENT\|FEATURES\|ORIGIN" wildtype.gbk | wc -l
10. grep "LOCUS" wildtype.gbk 
11. grep "SOURCE" wildtype.gbk 
12. grep "/gene=" wildtype.gbk 
13. clear ; history > history.txt
14. ls /content/berkay ; ls /content/biocomputing

###Project 2###

1. conda activate base
   conda config --add channels defaults
   conda config --add channels bioconda
2. conda create -n funtools python=3.10
3. conda activate funtools
4. sudo apt-get install figlet
5. figlet Berkay Ç.
6. conda install -c bioconda bwa
7. conda install -c bioconda blast
8. conda install -c bioconda samtools
9. conda install -c bioconda bedtools
10. conda install -c bioconda spades
11. conda install -c bioconda bcftools
12. conda install -c bioconda fastp  
13. conda install -c conda-forge multiqc
