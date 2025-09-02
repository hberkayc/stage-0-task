Project 1: BASh Basic

#1 echo "" to print your message such as print function in python
echo "Berkay"

#2 create a folder name in your current directory using "mkdir"
ls -la #look for the files, directories etc.
mkdir berkay
ls -la
cd /content/berkay #check the directory 
cd .. #go one step back

#3 Create another new directory titled biocomputing and change to that directory with one line of command
pwd #shows your directory
ls -la 
mkdir biocomputing ; cd /content/biocomputing # && can also be used instead of ;
cd ..

#4 Downloading files using wget 
pwd #prints your current directory
wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.fna
# The other 2 files are identical, so instead of repeating the same command, we can use "for" 
for i in {1..2}; do
  wget https://raw.githubusercontent.com/josoga2/dataset-repos/main/wildtype.gbk
done
ls -la

#5 Move the .fna file to the folder titled your name, using mv command
pwd
ls -la 
mv wildtype.fna /content/berkay ; cd /content/berkay
ls -la

#6 Delete the duplicate gbk file with rm
cd /content/biocomputing 
ls -la
rm wildtype.gbk.1 ; ls -la #confirm the deletion

#7 Confirm if the .fna file is mutant or wild type (tatatata vs tata) using grep command
ls -la
grep "tata" wildtype.gbk #shows WT tata sequences
grep "tatatata" wildtype.gbk #shows mutant tatatata seqs

#8 If mutant, print all matching lines into a new file using > 
grep "tatatata" wildtype.gbk > mutantlines.gbk ; cat mutantlines.gbk #cat or less commands to check the file's content
ls -la

#9 Count number of lines (excluding header) in the .gbk file using grep or sed 
less  wildtype.gbk #look into the file
grep -v '^LOCUS\|^DEFINITION\|^ACCESSION\|^VERSION\|^KEYWORDS\|^SOURCE\|^ORGANISM\|^COMMENT\|^FEATURES\|^ORIGIN' /content/biocomputing/wildtype.gbk | wc -l #outcome is 5741 lines
grep -v '^LOCUS\|^DEFINITION\|^ACCESSION\|^VERSION\|^KEYWORDS\|^SOURCE\|^ORGANISM\|^COMMENT\|^FEATURES\|^ORIGIN' /content/biocomputing/wildtype.gbk > nolines.gbk #convert into a file 

sed '1,/^ORIGIN/d' wildtype.gbk > nolines.txt ; less nolines.txt #from line 1 to the line that begins with ORIGIN, delete (d) all the lines. this approach is much more robust than the grep -v command. 
wc -l nolines.txt #outcome is 3291 lines. 

#10  Print the sequence length of the .gbk file. (Use the LOCUS tag in the first line)
grep "LOCUS\| bp"  wildtype.gbk #"\|" is OR operator

#11 Print the source organism of the .gbk file. (Use the SOURCE tag in the first line)
grep "SOURCE"  wildtype.gbk

#12 List all the gene names of the .gbk file. Hint {grep '/gene='}
grep "/gene=" wildtype.gbk

#13 Clear your terminal space and print all commands used today using "clear" and "history"
clear ; history > all-lines.txt
ls -la 

#14 List the files in the two folders 
ls -la /content/berkay ; ls -la /content/biocomputing


Project 2: Installing Bioinformatics Software on the Terminal

#1. Activate your base conda environment
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh #install miniconda
bash Miniconda3-latest-Linux-x86_64.sh #use Bash to execute the file that follows
exit #close and reopen terminal
conda --version # check the version and verify the installation

conda config --add channels defaults #add these channels in correct order 
conda config --add channels bioconda
conda config --add channels conda-forge

conda deactivate #to deactivate the current environment
conda activate base #activate base env

#2. Create a conda environment named funtools
conda create -n funtools python=3.10 #you can adjust the python version

#3. Activate the funtools environment
conda activate funtools 

#4. Install Figlet using conda or apt-get
conda list #to see the loaded packages
conda install pyfiglet 

#5. Run figlet <your name>
figlet berkay

#6. Install bwa through the bioconda channel
conda install -c bioconda bwa #-c to select specific channel

#7. Install blast through the bioconda channel
conda install -c bioconda blast

#8. Install samtools through the bioconda channel
conda install -c bioconda samtools

#9. Install bedtools through the bioconda channel
conda install -c bioconda bedtools

#10. Install spades.py through the bioconda channel
conda install -c bioconda spades

#11. Install bcftools through the bioconda channel
conda install -c bioconda bcftools

#12. Install fastp through the bioconda channel
conda install -c bioconda fastp

#13. Install multiqc through the bioconda channel
conda install -c bioconda multiqc
conda list #to see all packages and verify
