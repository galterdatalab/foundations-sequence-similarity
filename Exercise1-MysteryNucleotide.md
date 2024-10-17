# The NCBI BLAST Home Page
You can get to the NCBI BLAST suite of tools at [https://blast.ncbi.nlm.nih.gov/Blast.cgi](https://blast.ncbi.nlm.nih.gov/Blast.cgi). You can also Google NCBI BLAST and get right into the BLAST interface. Also, whenever you are viewing a record for an entry in NCBI's RefSeq database, you will see the BLAST option on the right side menu. This is convenient.  

There are lots of types of BLAST: from the basics for nucleotide, protein and translated BLAST, to specialized BLAST for primer design, to find vector contamination, to global alignment and many more. We'll only have time to try the most-used BLAST types: nucleotide and protein.  

# Create an account and save your search strategies!
Setting up an account at NCBI is free. There's a good chance you already have an account for managing your publications and grant associations in NCBI's My Bibliography, or you use your NCBI account to save PubMed searches and collections.  
* Click on the "Sign in" button in the upper right corner of the BLAST page (or any other NCBI database page).
* Log in with any of several options:
  * eRA Commons, Login.gov (if you have NIH grants and want to use your Commons credentials to log in).
  * If you don't have a Commons account, you can log in with your Google account, your Northwestern secure sign-in, or many other options.
  * Over time, you will want to make sure that you LINK your multiple identities with your NCBI account (ORCID, Northwestern email, etc.)
* In your NCBI "Dashboard" you will see places to save BLAST search settings. This is really helpful if you have taken a lot of time to set up the perfect parameters, and will need to revisit the BLAST to write the methods for a publication, or duplicate the search with new data (or just remember what you did).

NCBI's BLAST online is easy to use, but, because of the rapid expansion of sequences in the databases (especially thanks to COVID research), web BLAST can be slow, and you may get warnings about over use of CPU time, even for simple searches. If this happens, try BLAST at less common times: like the evening or early morning. Or set up an account to use ElasticBLAST in the cloud, if you have a lot of BLAST searches to do (this does involve some cost). 


# Set up a nucleotide BLAST
Nucleotide BLAST comes with some difficulties: DNA sequences are longer than their translated proteins, so they expand the search space and time to search. Also, since different codons can encode for the same amino acid, so there is some uncertainty of which amino acid will be coded by any 3-letter subset, depending on where the algorithm finds its match and starts the search.  

## Start with a sequence
Click on the **Nucleotide BLAST** graphic on the BLAST home page.  

We're going to use a "mystery sequence" in FASTA format. Copy this sequence. Copy the whole sequence, along with the line that begins with the ">", and paste it into the box on the blastn page.   
\>MysterySequence  
GAATTCCGTTGGGAGGAGCTTACGCTGGGCTTGAAATGTCAATCAGAGTGTGAGTGCCAATGATCTGAAGCAATCT
GTTAGGAACTGACCTGGTCCACTCAGATCAATAGCATCAGAGGGAGAGGACAGAGTCACCGAGATCCCTGCTGGAA
CCCTAGCAGCCCGGTTCCCCCTTCCTCGGTCACTTGATGTGTAGGGAGAGGGGGAAACAAAGTCAGGTCATAAAAG
GGGATTCCCTGTGCCTCCGGCTGCACCATGTCCTTCCCACAGCTGGGCTACCAGTACATCAGACCTCTGTACCCCT
CGGACAGACAGAGCGTGGGGGTAACCAGGAGCGGAACTGAGCTGTCTCCGGCAGGGACTCTTTCTAATGTACTTTC
CTCCGTGTATGGAGCACCCTACGCTGCAGCCGCCGCAGCACAAGCCTATGGAGCCTTCCTGCCCTACAGCGCGGAG
CTGCCCATCTTCCCCCAGCTGGGTTCACAGTATGACATGAAGGACAGTCCTGGGGTCCAGCATGCCGCCTTCTCCC
ACCCTCACCCAGCCTTTTATCCCTACGGACAATACCAATTTGGAGATCCGTCAAGGCCCAAAAATGCTACCAGAGA
GAGCACAAGCACCCTTAAGGCCTGGCTCAATGAGCACAGAAAGAACCCCTATCCGACCAAGGGCGAGAAAATCATG
CTTGCTATCATCACTAAAATGACCCTCACGCAGGTGTCCACCTGGTTTGCTAACGCAAGGAGGAGACTTAAAAAGG
AGAACAAAATGACTTGGGCCCCTAGGAGCCGAACAGACGAGGAAGGTAACGCCTATGGCAGCGACCACGAAGAAGA
CAAGCACGAGGACGAGGAGGAGATTGACTTGGAGAACATCGACACTGAGGACATTGAGAGTAAAGAAGATTTGGAT
GACCCAGACACTGATATACACTCGGACTCTAAAACTGATACTAGGAGTGACTCGGAAGTCTCGGATGGGTTTGAAG
ACCTAAATGTCCCTGAGGACAGACTTCTCAAATCTGTGGTTGGTCAAAGGCAACTTTTAAATGAGGAGCCTCAGGA
CAAGTGTGCACTTTCTTCTGATGCTAAAGTTCCACAACCTGCATGTGAGCAGATCAAACTTAACAGACTCCCCCCT
AGTCCTCCTCAGGAGAACAACATGCCCGTAGCCCATAAACCCAAAATCTGGTCATTGGCAGAGACTGCCACAACCC
CAGATAACCCACGTAATTCTCCCAATACTGGGGGCTCAGTGAACACACAAAACCTGATTGCACAACACAGACTTAT
TGCCTCCCCAGGGAGCAGGTTCCAGGGTTGGACTGGGAGAGCTTTCTCTGCTCAGCAGTTGTCCTTACTGAACTCG
GCTCATTTTCTACAAGGACTCGGTGTCTCTCACACAGCCCCATGTTCTGGCAATGCAAGTTTCCCTAAGGCCGCGG
AGTCCAAGTGCAGCACAAACTCTCTAACAGATCGACCCAGTACAGTGGACATAGAGAAAACAATACCTGTATTAAA
TACAGCTTTCCAACCAGTGCAACGGAGGTCACAAGATCACCTGGACGCTGCAATGATTCTTTCCGCTTTATCCTCA
TCCTAACACTGTATTTTATATTTATATTTTTATTTCCTTTTTTTTAAACTATTTGAATGACTGTAAAATATATCTG
TGTTGGGTAGTTACGCCTTGTGAGCATGTCTGTGGATAAAATGGAACAACTATTTGTTTCTATACTCTCATTCAGA
GCAGCTGAGTTCGTATGGTTTGTCTTGTGCTAATTAAACGTCGGTCATTTTTGTATATATAGTACAAATGTAAATA
TGTGTTTAAACCAAATTGTACAAGAAAGTATATATTTTTGGTCAATAAATTCTCAATTTACTACAAAAAAAAAAAA
AAAGCGGAATCCGCGGTGGCGGCCGCTCTAGAACTAGTGGATCCCCCGGGCTGCAGGAATTCGATATCAAGCTTAT
CGATACCGTCGACCTCGAGGGGGGGCCCGGTACCCAGCTTTTGTTCCCTTTAGTGAGGGTTAATTGCGCGCTTGGC
GTAATCATGGTCATAGCT

Note that you can also just copy and paste an accession number or upload a formatted file from your computer. 

## Set your database and parameters
Because BLAST has been slow, we're going to keep the defaults for this search for faster return of results.  
* Core Nucleotide is now the default database. It's basically the same as the old default ("nr/nt"), but it's been cleaned up to remove non-annotated and non-gene coding sequences. There are some cases where you might NOT want to remove non-gene sequences, so nr/nt is still available. There are many more database options to select from as well. Use whatever suits your experimental question the best.
* You can limit to specific species, classes, etc (like "mammals", "vertebrates", "viruses", "drosophila"). This can speed your searches. In this case, we don't know what the species is, so we'll leave it blank.
* You can exclude models and environmental samples.
* Choose a program that will search for more or less similar sequences (again, in the interest of time, we're going to use "megablast").
* **Algorithm Parameters**
  * Click on the "+" by Algorithm parameters to expand this section.
  * You can select more target hits, change the match/mismatch and gap penalties, filter out low-complexity regions, and mask repeats.
  * For some experiments, I do alter these defaults. They are set to provide the best overall results for most sequence searches, but if you are searching with a novel sequence you have discovered, you may want to alter some of the scoring criteria to be less stringent for matches and gaps.
 
### Helpful: Click the checkbox for "Show results in a new window".
I like doing this, because I can look at my settings, then my results, and decide what I need to change if my initial results were not satisfying.  

## Hit the BLAST button

## Results
Take some time to look at the results.  
  * See how many species are represented in the results. Do you notice something weird?
  * Take a look at the tabs for **Graphic Summary**, **Alignments**, and **Taxonomy**
    * In the Taxonomy tab, look at the sub-tabs for **Lineage**, **Organism**, and **Taxonomy**
  * Look at the multiple sequence alignment in the **MSA Viewer**
  * Look at the **Distance Tree of results**

Note that from the top of your results page you can easily search a subset of your sequence, filter by organism or percent identity, E value or query coverage.
You can also Edit the search (very top of the results page, above your query title), and run it again.
