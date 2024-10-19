## For our second protein example - finding other viral orthologs to the spike protein
* Go back to the blastp page, which should still be open in a tab in your browser,
  
* **Settings for the BLAST**:
  * Make sure the molecule accession number and query subrange are still populated. Consider re-naming your job, since it will be different this time, in case you want to save it and revisit it.
  * BLAST will usually keep the settings from the last BLAST we did in this session, BUT DON'T CLICK ON "reset page", because you'll lose the accession # and coordinates.
    * We will reset the databases and settings we want to change to find other species' proteins.
  * **Standard databases (nr, etc)**
  * **Database**: Reference proteins (refseq_protein)
  * **Organism**: Clear the COVID entry, and type "viruses". You can click either of the top 2 results (they're the same).
  * **Exclude**: Non-redundant RefSeq proteins (WP) and Uncultured/environmental samples
  * **Algorithm**: DELTA-BLAST
  * **Expand Algorithm parameters**
    * Set Max target sequences to 100
      * We'll miss some species by limiting to 100, but this will make it faster. If I were doing this search for research purposes, I would keep 500 or do 250 at the very least.
    * Filter for low complexity regions. Leave everything else as-is.
 
### **Don't forget to check "Show results in a new window**
 
## **Hit the BLAST button**

## In the Results page
