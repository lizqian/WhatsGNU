# WhatsGNU
What's Gene Novelty Unit: A Tool For Identifying Proteomic Novelty.
# Introduction
WhatsGNU utilizes the natural variation in public databases to rank protein sequences based on the number of observed exact protein matches (the GNU score) in all known genomes of a certain species & can quickly create whole protein reports.<br/>
WhatsGNU compresses proteins database based on exact match to much fewer number of proteins that differ by at least one amino acid. WhatsGNU will save a copy of the compressed database in two formats; database.txt and database.pickle for faster subsequent uses.<br/>

Three preprocessed compressed databases (.pickle) are available to download and use:
1. [_Mycobacterium tuberculosis_]() current version: 01/30/2019.
2. [_Pseudomonas aeruginosa_]() current version: 01/27/2019.
3. [_Staphylococcus aureus_]() current version: 01/21/2019.<br/>
These three databases contain all available annotated genomes for the species from GenBank. The databases for these 3 organisms will be updated 3 times per year.

# Dependencies
[Python3.x](https://www.python.org/downloads/)<br/>
# Installation
WhatsGNU is a command-line application written in Python3, with no additional dependencies beyond the standard Python3.x package. Simply download and use!
```
$git clone https://github.com/ahmedmagds/WhatsGNU
$cd WhatsGNU
$chmod +x WhatsGNU.py
```
# Test
* Type WhatsGNU.py -h and it should output help screen.
* Type WhatsGNU.py -v and you should see an output like WhatsGNU.py 1.0.
# Input
The program accepts for analysis protein FASTA files (.faa).
# Usage
**First time use**
```
$WhatsGNU.py -m database.faa query.faa
```
**Subsequent uses**
```
$WhatsGNU.py -d database.pickle query.faa
```
**Command line options**
```
$WhatsGNU.py -h
```
```
usage: WhatsGNU.py [-h] [-m MKDATABASE | -d DATABASE] [-o OUTPUT_FOLDER] [-t]
                   [-s STRAINHITS] [-b] [-c [CCST_TYPING]] [-v]
                   fastafile_faa

WhatsGNU v1.0 utilizes the natural variation in public databases to rank
protein sequences based on the number of observed exact protein matches
(the GNU score) in all known genomes of certain species & can quickly create
whole protein reports

positional arguments:
  fastafile_faa         protein FASTA file to analyse (.faa)

optional arguments:
  -h, --help            show this help message and exit
  -m MKDATABASE, --mkdatabase MKDATABASE
                        you have to provide path to faa file format to create
                        compressed database in txt and pickle formats
  -d DATABASE, --database DATABASE
                        you have to provide path to your processed database
  -o OUTPUT_FOLDER, --output_folder OUTPUT_FOLDER
                        give name for output folder to be created for results
                        (default: timestamped WhatsGNU_results_v1 in the
                        current directory)
  -t, --tophits         create a file of top 10 genomes with hits
  -s STRAINHITS, --strainhits STRAINHITS
                        check how many hits you get from a particular
                        strain,you have to use it with -t
  -b, --hits            create a file of each protein with all hits from the
                        database,large file (~ 1 Gb for 3000 pts)
  -c [CCST_TYPING], --CCST_typing [CCST_TYPING]
                        get the CC/ST composition of your hits (Note: Works
                        only for Saureus)
  -v, --version         print version and exit
```
# Output
**query_exact_hits_report.txt** <br/>
tab delimited file of protein and number_of_hits
# Instructions for creating a database
put somehting here
# Bugs
Please submit via the GitHub issues page: https://github.com/ahmedmagds/WhatsGNU/issues
# Software Licence
GPLv3: https://github.com/ahmedmagds/WhatsGNU/blob/master/LICENSE
# Author
Ahmed M. Moustafa: [ahmedmagds](https://github.com/ahmedmagds)<br/>
Twitter: [Ahmed_Microbes](https://twitter.com/Ahmed_Microbes)

