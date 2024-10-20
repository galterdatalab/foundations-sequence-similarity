## For our second protein example - finding other viral orthologs to the spike protein receptor binding domain
We're going to use a different manuscript for this orthology search:  
Piplani S, Singh PK, Winkler DA, Petrovsky N. [In silico comparison of SARS-CoV-2 spike protein-ACE2 binding affinities across species and implications for virus origin](https://pmc.ncbi.nlm.nih.gov/articles/PMC8225877/). Sci Rep. 2021 Jun 24;11(1):13063. doi: 10.1038/s41598-021-92388-5. Erratum in: Sci Rep. 2021 Sep 14;11(1):18610. doi: 10.1038/s41598-021-98366-1. PMID: 34168168; PMCID: PMC8225877.  

The RefSeq record referred to in this manuscript is [YP_009724390.1](https://www.ncbi.nlm.nih.gov/protein/YP_009724390.1). It's basically the same molecule.
* Scroll down to the Region for the receptor binding domain (it's the second Region in the record). Click on the Region link, just like last time.
* In the tab window for the region, click on FASTA format, like last time.
* From the FASTA page, again, click on Run BLAST. 
  
## **Settings for the BLAST**:
  * Make sure the molecule accession number and query subrange are populated. BUT let's add some residues to the beginning and end of the RBD.
    * Enter 250 in the **From** box, and enter 700 in the **To** box. This will show us the sequence just before the RBD (about 60 residues) and also cover part of the beta sheet region that has the aspartic acid (D) that is mutated in some human sequences. 
    * Again, consider giving your job a descriptive name.
  * BLAST will usually keep the settings from the last BLAST we did in this session, BUT DON'T CLICK ON "reset page", because you'll lose the accession # and coordinates.
    * We will change the databases and settings we want to change to find other species' proteins.
  * **Standard databases (nr, etc)**
  * **Database**: Reference proteins (refseq_protein)
  * **Organism**: Clear the COVID entry, and type "viruses". You can click either of the top 2 results (they're the same).
  * **Exclude**: Non-redundant RefSeq proteins (WP) and Uncultured/environmental samples
  * **Algorithm**: PSI-BLAST
  * **Expand Algorithm parameters**
    * Set Max target sequences to 100
      * We might miss some species by limiting to 100, but this will make it faster. If I were doing this search for research purposes, I would keep 500 or 250.
    * Set **Max matches in a query range** to 20. This will winnow out the many many human SARS-CoV-2 sequences, and give us more species for comparison.
    * Set the **Matrix** to BLOSUM45 - this is because there is low sequence similarity between some coronavirus species, but the literature suggests that this binding region is similar in different types of coronaviruses (and other viruses) for binding host proteins.
    * Filter for low complexity regions.
    * Leave everything else as-is.
 
### **Don't forget to check "Show results in a new window**
 
## **Hit the BLAST button**

## In the Results page  
* Take a look at the list of hits and note how many species are represented, and what the percent coverage is for each hit.
* Look at the Graphic Summary tab. Note the regions that are covered by hits in various species (some species have hits toward the beginning of the RBD, but others only have hits in the area after the binding region).
* The distance tree of results shows that one bat viral protein is most similar (as you might know already). Look at the multiple alignment, too. 
* Things to consider: are the weaker hits (sparrow or heron viruses, for example) really similar enough to be considered orthologous? A possible BLAST of the complete protein (rather than just the region around the RBD) may show more.
### Try running a BLAST iteration 2 and see how many new species you get. Try another one after that.  

### What can you do with the results?
BLAST allows you to download results in a few formats:    
* **From the Descriptions page of the results**: FASTA of each sequence or of the aligned sequences; a "hit table", a descriptions table, and more
* **From the multiple alignment page (COBALT)**: FASTA plus gaps, CLUSTAL, Phylip (for tree building), Newick (also for tree building), ASN.1
  * If you don't like the COBALT aligner, the CLUSTAL option allows you to take the alignments to other multiple sequence alignment tools, so you have more control over the conditions for the alignment.
* **From the distance tree of results**: You can reset the parameters and rebuild the tree, or you can download (from the "Tools" menu over the image) as ASN text or binary, NEXUS (also for tree building), Newick, or as PDF for an image.

## Another search to try: Instead of BLAST on the viral protein, it might be interesting to BLAST the orthologs for ACE2.
Rationale: The manuscript cited for this example describes that some species' ACE2 proteins do bind the SARS-CoV-2 spike protein with varying affinities, so it might be interesting to look at the differences in the residues that they describe in their paper. 
