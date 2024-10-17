# Sequence Similarity Searching
These materials support a workshop on NCBI BLAST initially taught in Fall 2024, as part of the series Foundations in Genome Analyses, hosted by NUIT Research Computing and Data Services. These materials were prepared and presented by Pamela Shaw of Galter Health Sciences Library.

# Introduction and Workshop Plan
Sequence similarity searching using BLAST (Basic Local Alignment Search Tool) is a long-standing practice in genome analysis. While newer methods in genome sequencing dominate bioinformatics analyses, BLAST is still used for discovering evolutionarily similar species' protein or nucleotide molecules. If you have characterized a new gene in a bacterium, for example, you might want to find if the same sequence exists in other bacteria. Most recently, BLAST has played an important role in discovering mutations in the COVID-19 (SARS-CoV-2) virus that make certain strains more efficient in infecting host cells.  

We'll be using [NCBI's BLAST suite of tools](https://blast.ncbi.nlm.nih.gov/Blast.cgi). We won't have time to explore them all, but we will use Nucleotide BLAST (blastn) and Protein BLAST (blastp). There are lots of other BLAST tools as well, including translated BLAST (tblastn or blastx), BLAST genomes, Primer BLAST, BLAST for just immunoglobulins or conserved domains, and some alignment tools. The BLAST page also has a downloadable version of BLAST for use on your server or local machine, a BLAST API tool and a cloud BLAST launch.

We are going to start with a DNA BLAST on a "Mystery sequence" to illustrate how Nucleotide BLAST can quickly find similar sequences for relatively short queries.  

Then, we are going to use a published manuscript on a mutation in the spike protein in SARS-CoV-2 as our starting point, and try to discover how many other species' viruses may contain a similar spike protein, and also (time permitting) find the sequences available in the BLAST databases that contain the specific mutation in human COVID-19. This particular BLAST search can be very computationally taxing on the NCBI BLAST servers, so we have a backup BLAST search that we can use if we run into heavy server delays.
 

# Support Materials  
The NCBI has lots of support materials available in many formats:  
* The [BLAST Help page](https://blast.ncbi.nlm.nih.gov/doc/blast-help/) (with links to many tutorials and materials)
* [NCBI BLAST YouTube](https://www.youtube.com/playlist?list=PL7dF9e2qSW0azL2xOKAtxDW7QI8UU4XZ6) channel
