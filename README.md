# Sequence Similarity Searching
These materials support a workshop on NCBI BLAST

Sequence similarity searching using BLAST (Basic Local Alignment Search Tool) is a long-standing practice in genome analysis. It is still used for discovering evonlutionarily similar species' protein or DNA molecules, often in virology or microbiology. If you have characterized a new gene in a bacterium, for example, you might want to find if the same sequence exists in other bacteria. Most recently, BLAST has played an important role in discovering mutations in the COVID-19 (SARS-CoV-2) virus that make certain strains more efficient in infecting host cells.  

We'll be using [NCBI's BLAST suite of tools](https://blast.ncbi.nlm.nih.gov/Blast.cgi). We won't have time to explore them all, but we will use Nucleotide BLAST (blastn) and Protein BLAST (blastp). There are lots of other BLAST tools as well, including translated BLAST (tblastn or blastx), BLAST genomes, Primer BLAST, BLAST for just immunoglobulins or conserved domains, and some alignment tools. The BLAST page also has a downloadable version of BLAST for use on your server or local machine, a BLAST API tool and a cloud BLAST launch.

We are going to start with a DNA BLAST on a "Mystery sequence" to illustrate how Nucleotide BLAST can quickly find similar sequences for relatively short queries.  

Then, we are going to use a published manuscript on a mutation in the spike protein in SARS-CoV-2 as our starting point, and try to discover how many other species' viruses may contain a similar spike protein, and also find the sequences available in the BLAST databases that contain the specific mutation in human COVID-19. This particular BLAST search can be very computationally taxing on the NCBI BLAST servers, so we have a backup BLAST search that we can use if we run into heavy server delays.

The manuscript we will be using is:  
Korber B, Fischer WM, Gnanakaran S, Yoon H, Theiler J, Abfalterer W, Hengartner N, Giorgi EE, Bhattacharya T, Foley B, Hastie KM, Parker MD, Partridge DG, Evans CM, Freeman TM, de Silva TI; Sheffield COVID-19 Genomics Group; McDanal C, Perez LG, Tang H, Moon-Walker A, Whelan SP, LaBranche CC, Saphire EO, Montefiori DC. [Tracking Changes in SARS-CoV-2 Spike: Evidence that D614G Increases Infectivity of the COVID-19 Virus](https://pmc.ncbi.nlm.nih.gov/articles/PMC7332439/). Cell. 2020 Aug 20;182(4):812-827.e19. doi: 10.1016/j.cell.2020.06.043. Epub 2020 Jul 3. PMID: 32697968; PMCID: PMC7332439.  

# Support Materials  
The NCBI has lots of support materials available in many formats:  
* The [BLAST Help page](https://blast.ncbi.nlm.nih.gov/doc/blast-help/) (with links to many tutorials and materials)
* [NCBI BLAST YouTube](https://www.youtube.com/playlist?list=PL7dF9e2qSW0azL2xOKAtxDW7QI8UU4XZ6) channel
