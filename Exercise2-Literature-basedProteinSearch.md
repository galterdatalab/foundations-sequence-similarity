Here, we are going to try using a published manuscript on a mutation in the entry spike protein for the SARS-CoV-2 virus. We'll find a protein sequence that matches the publication and BLAST it against viral proteins.  


The manuscript we will be using is:  
Korber B, Fischer WM, Gnanakaran S, Yoon H, Theiler J, Abfalterer W, Hengartner N, Giorgi EE, Bhattacharya T, Foley B, Hastie KM, Parker MD, Partridge DG, Evans CM, Freeman TM, de Silva TI; Sheffield COVID-19 Genomics Group; McDanal C, Perez LG, Tang H, Moon-Walker A, Whelan SP, LaBranche CC, Saphire EO, Montefiori DC. [Tracking Changes in SARS-CoV-2 Spike: Evidence that D614G Increases Infectivity of the COVID-19 Virus](https://pmc.ncbi.nlm.nih.gov/articles/PMC7332439/). Cell. 2020 Aug 20;182(4):812-827.e19. doi: 10.1016/j.cell.2020.06.043. Epub 2020 Jul 3. PMID: 32697968; PMCID: PMC7332439.  

Two NCBI Protein records related to this paper:  
* PDB protein [6VSB, Chain C](https://www.ncbi.nlm.nih.gov/protein/1812779093) (though all chains are identical -- NCBI protein record linked). This is the sequence for the structural model used in the manuscript. 
* RefSeq surface glycoprotein for SARS-CoV-2 [YP_009724390.1](https://www.ncbi.nlm.nih.gov/protein/YP_009724390.1).

If this does not work because of BLAST server lag, we'll try a [shorter, simpler protein record](https://www.ncbi.nlm.nih.gov/protein/YP_401672.1).  

# Protein BLAST
Protein BLAST works basically the same as nucleotide BLAST, but with different algorithm choices and different databases specific to proteins.  

If you still have the BLAST setup page open from our nucleotide BLAST, you can just click on the "blastp" tab near the top of the page, then hit the "reset page" button over in the right corner of the blue border. If you've navigated away from BLAST, here's the link to the BLAST home page:  
[https://blast.ncbi.nlm.nih.gov/Blast.cgi](https://blast.ncbi.nlm.nih.gov/Blast.cgi)  

It's a good idea to hit the "reset page" button here, even if you came in from the BLAST home page, in case any settings from any previous session were saved. 

## Choosing your BLAST Search Set and Program
How do you decide what database to search? Which BLAST algorithm should you use?

### For the search set  
* **Standard databases (nr, etc)**
  * Despite its name, "nr" non-redundant protein sequences has a high level of redundancy in the respect that there will be several near-identical sequences from different individuals of the same species. It is the largest search space in protein BLAST.
  * The rest of the search sets are smaller and more focused. I will sometimes BLAST only against RefSeq proteins (but rarely RefSeq Select) or UniProt/SwissProt proteins. The database you choose should be based on your intended purpose.
* **Experimental databases (clustered nr)**
  * The clustered non-redundant search set is useful for speeding up your search. It uses just one sequence to represent a whole group of similar proteins. Your results will match against the representative sequence, but include the rest of the cluster in your result set.

* Limit by organism and exclude some types of sequences
  * These choices can make your searches (somewhat) faster and more focused. If you only want to search against vertebrates, or viruses, or specific bacteria, or mammals, you can make those choices here. Unless you're interested in environmental samples, this is a good exclusion to select. 
 
### For the program (algorithm)
* The choices here will be different dependent upon whether you chose standard or experimental databases.
  * There are more algorithms to choose from when you search using the standard databases.
  * **blastp** is the most general form of BLAST, while **Quick BLASTP** is based on blastp, but assumes higher identity, and is only available for the nr data set.
  * **PSI-BLAST** and **DELTA-BLAST** both build position-specific scoring matrices (PSSM), and are good when you want to search for orthologs for a conserved domain or fold. DELTA-BLAST is the more focused of the two, because it uses members of the Conserved Domain Database (CDD) to build its initial PSSM, then constructs the search around these domains.
  * **PHI-BLAST** is very useful for finding matches to a highly-conserved region which has a signature sequence pattern that you enter in the space provided. The NCBI has a handy document on the [rules for PHI-BLAST pattern syntax](https://blast.ncbi.nlm.nih.gov/doc/blast-topics/rulesforphipattern.html).
  * 
