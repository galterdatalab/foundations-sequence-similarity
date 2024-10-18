Here, we are going to try using a published manuscript on a mutation in the entry spike protein for the SARS-CoV-2 virus. We'll find a protein sequence that matches the publication and BLAST it against viral proteins.  


The manuscript we will be using is:  
Korber B, Fischer WM, Gnanakaran S, Yoon H, Theiler J, Abfalterer W, Hengartner N, Giorgi EE, Bhattacharya T, Foley B, Hastie KM, Parker MD, Partridge DG, Evans CM, Freeman TM, de Silva TI; Sheffield COVID-19 Genomics Group; McDanal C, Perez LG, Tang H, Moon-Walker A, Whelan SP, LaBranche CC, Saphire EO, Montefiori DC. [Tracking Changes in SARS-CoV-2 Spike: Evidence that D614G Increases Infectivity of the COVID-19 Virus](https://pmc.ncbi.nlm.nih.gov/articles/PMC7332439/). Cell. 2020 Aug 20;182(4):812-827.e19. doi: 10.1016/j.cell.2020.06.043. Epub 2020 Jul 3. PMID: 32697968; PMCID: PMC7332439.  

Two NCBI Protein records related to this paper:  
* RefSeq surface glycoprotein for SARS-CoV-2 [YP_009724390.1](https://www.ncbi.nlm.nih.gov/protein/YP_009724390.1).
* PDB protein [6VSB, Chain C](https://www.ncbi.nlm.nih.gov/protein/1812779093) (though all chains are identical -- NCBI protein record linked).

If this does not work because of BLAST server lag, we'll try a [shorter, simpler protein record](https://www.ncbi.nlm.nih.gov/protein/YP_401672.1).  

# Protein BLAST
Protein BLAST works basically the same as nucleotide BLAST, but with different algorithm choices and different databases specific to proteins.  

If you still have the BLAST setup page open from our nucleotide BLAST, you can just click on the "blastp" tab near the top of the page, then hit the "reset page" button over in the right corner of the blue border. If you've navigated away from BLAST, here's the link to the BLAST home page:  
[https://blast.ncbi.nlm.nih.gov/Blast.cgi](https://blast.ncbi.nlm.nih.gov/Blast.cgi)  

It's a good idea to hit the "reset page" button here, even if you came in from the BLAST home page, in case any settings from any previous session were saved. 
