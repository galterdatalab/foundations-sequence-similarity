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
  * These choices can make your searches (somewhat) faster and more focused. Just like in nucleotide BLAST, you can limit to certain organisms and exclude some sequence types. 
 
### For the program (algorithm)
* The choices here will be different dependent upon whether you chose standard or experimental databases.
  * There are more algorithms to choose from when you search using the standard databases.
  * **blastp** is the most general form of BLAST, while **Quick BLASTP** is based on blastp, but assumes higher identity, and is only available for the nr data set.
  * **PSI-BLAST** and **DELTA-BLAST** both build position-specific scoring matrices (PSSM), and are good when you want to search for orthologs for a conserved domain or fold. DELTA-BLAST is the more focused of the two, because it uses members of the Conserved Domain Database (CDD) to build its initial PSSM, then constructs the search around these domains.
  * **PHI-BLAST** is very useful for finding matches to a highly-conserved region which has a signature sequence pattern that you enter in the space provided. The NCBI has a handy document on the [rules for PHI-BLAST pattern syntax](https://blast.ncbi.nlm.nih.gov/doc/blast-topics/rulesforphipattern.html).

## Expand the algorithm parameters
Don't forget to expand the algorithm parameters to change any of the defaults. Depending on your choice of algorithm in the above section, your options here will be different.   

**Consider**:
* **Max target sequences** will default to 500 for PSI-BLAST, but if your search is taking too long, consider making this number smaller.
* Make your **expect threshhold** more stringent and your **word size** larger for more similar sequences -- unless you are looking for more distantly-related orthologs.
* **Max matches in a query range** defaults to 0, but the NCBI recommends setting a limit in cases where there may be ranges of extreme identity, so it will not miss areas of less similarity in proteins that have some highly identical regions.
* **Scoring parameters**
  * BLOSUM62 is the default, but for conserved domains that may have undergone more evolutionary mutation without losing function, choose a less stringent scoring matrix.
    * Remember: High BLOSUM numbers = higher identity; High PAM numbers = lower identity
  * Make the **gap cost** higher for existence for a more stringent search. The default will change, depending on your scoring matrix choice, with the gap cost that performs best for each matrix selected by default.
  * **Filter for low complexity regions** is something I almost always choose, depending on my query, and **masking** can speed your search.
 
## For our first example - finding if there are any SARS-CoV-2 D614G sequences in the dataset
* Start at the [6VSB, Chain C](https://www.ncbi.nlm.nih.gov/protein/1812779093) record, which is the protein cited in the manuscript.
* Scroll down to the Region "SARS-CoV-like-Spike_SD1-2_S1-S2_S2" (aa 543-1208). Click on the "Region" link.
  * This will take you to the sequence with the region highlighted, and a tab window in the lower right. In that tab window, click on FASTA for the Display.
* From this FASTA page, you will notice that you have a link directly to **Run BLAST**. Click that.
* **Settings for the BLAST**:
  * You'll notice the molecule name and region is already filled in. Consider naming your job, in case you want to save it and revisit it.
  * **Standard databases (nr, etc)**
  * **Database**: non-redundant protein sequences (nr)
  * **Organism**: start typing "severe acute", when this shows: Severe acute respiratory syndrome coronavirus 2 (taxid:2697049), select it.
  * **Exclude**: Non-redundant RefSeq proteins (WP) and Uncultured/environmental samples
  * **Algorithm**: Quick BLASTP
  * **Expand Algorithm parameters**
    * Make sure Max target sequences is 100 and Filter for low complexity regions. Leave everything else as-is.
 
### **Don't forget to check "Show results in a new window**
 
## **Hit the BLAST button**

## In the Results page
* Note that the percent identity is all very high. This is not a surprise.
* Click on **Multiple Alignment** under the "Other reports" section in the top box OR just above the list of results
* In the multiple alignment page, drag to highlight the first portion of the red (aligned) area and zoom in, then zoom even more to the sequence level
* Here, you will have to drag to position 708 -- this corresponds to our query position 614. Hover over this amino acid to see that 52% of the results are mismatches in this position.
  * Scroll down a bit to see that several of the sequences have G in this position.
* So the BLAST database does contain at least some individuals' sequences that show this increased infectivity mutation. 
