## For our second protein example - finding other viral orthologs to the spike protein binding domain
We're going to use a different manuscript for this orthology search:  
Piplani S, Singh PK, Winkler DA, Petrovsky N. [In silico comparison of SARS-CoV-2 spike protein-ACE2 binding affinities across species and implications for virus origin](https://pmc.ncbi.nlm.nih.gov/articles/PMC8225877/). Sci Rep. 2021 Jun 24;11(1):13063. doi: 10.1038/s41598-021-92388-5. Erratum in: Sci Rep. 2021 Sep 14;11(1):18610. doi: 10.1038/s41598-021-98366-1. PMID: 34168168; PMCID: PMC8225877.  

The RefSeq record referred to in this manuscript is [YP_009724390.1](https://www.ncbi.nlm.nih.gov/protein/YP_009724390.1). It's basically the same molecule.
* Scroll down to the Region for the receptor binding domain (it's the second Region in the record). Click on the Region link, just like last time.
* In the tab window for the region, click on FASTA format, like last time. From the FASTA page, again, click on Run BLAST. 
  
* **Settings for the BLAST**:
  * Make sure the molecule accession number and query subrange are populated. Again, consider giving your job a descriptive name.
  * BLAST will usually keep the settings from the last BLAST we did in this session, BUT DON'T CLICK ON "reset page", because you'll lose the accession # and coordinates.
    * We will change the databases and settings we want to change to find other species' proteins.
  * **Standard databases (nr, etc)**
  * **Database**: Reference proteins (refseq_protein)
  * **Organism**: Clear the COVID entry, and type "viruses". You can click either of the top 2 results (they're the same).
  * **Exclude**: Non-redundant RefSeq proteins (WP) and Uncultured/environmental samples
  * **Algorithm**: PSI-BLAST
  * **Expand Algorithm parameters**
    * Set Max target sequences to 100
      * We might miss some species by limiting to 100, but this will make it faster. If I were doing this search for research purposes, I would keep 500 or do 250 at the very least.
    * Filter for low complexity regions. Leave everything else as-is.
 
### **Don't forget to check "Show results in a new window**
 
## **Hit the BLAST button**

## In the Results page
