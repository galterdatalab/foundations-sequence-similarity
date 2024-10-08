# A Short Background on BLAST

## Pattern Matching Algorithms
Pattern matching algorithms form the basis for modern BLAST. The "evolution" of BLAST algorithms is:
* Needleman-Wunsch - global alignment; slow and cpu intensive, but still used for NCBI's Global Alignment tool; will miss domain or motif alignments
* Smith-Waterman - local alignment; slow and cpu intensive, because it uses all possible "word" lengths to search for pattern hits
* FASTA - local alignment; uses a set "word" size to search lookup tables, so it's fast
* BLAST - local alignment; also uses "words" to search, find matches, then extend forward and backward in target sequences; is what we still use now

## Amino Acid Substitution Matrices (protein only)
* PAM - 
