Grep and fasta files
====================

Each sequence in a FASTA file begins with a header line (`>` followed by an optional sequence id). **Note that the optional sequence id or header can using any characters. However the `>` symbol is required in FASTA format.** Sequence data follows and is usually wrapped (making multiple lines). Read more about FASTA format at http://www.ncbi.nlm.nih.gov/BLAST/blastcgihelp.shtml. 

Here is a simple example of a fasta file called `test.fasta`.

```
>seq1
ATCGATCGCnTCGGGTACT
TCAGnAAAATGCTCTGATC
TCAG
>seq2
TGCGATCCCTACGTCATCA
AAATCGCTAGnnTCA
```

The `grep` program searches for patterns within a file. By default it all prints lines with the pattern in the file. **Remember: In "Usage" statements text that is capitalized represents user specified input and optional arguments are bracketed with square brakets ([ ]).**

Here would be typical usage:

   Usage:   grep [OPTIONS] PATTERN [FILE...]
   
Here is an example of the output of a grep command on `test.fasta`.

```
$ grep "n" test.fasta
ATCGATCGCnTCGGGTACT
TCAGnAAAATGCTCTGATC
AAATCGCTAGnnTCA
```
The `-c` flag tells `grep` to print the count of lines with the pattern.

```
$ grep -c "n" test.fasta
3
```
## Question:

What would be the output of the following command be?

```
$cat test.fasta
>my_header1
ATCGATCGCnTCGGGTACT
TCAGnAAAATGCTCTGATC
TCAG
>my_header2
TGCGATCCCTACGTCATCA
AAATCGCTAGnnTCA
grep -c "AA" test.fasta
```

A) 5

B) 2

C) 3

D) 

TCAGnAAAATGCTCTGATC

AAATCGCTAGnnTCA

## Code challenge:
Given what you know about fasta file format, write a command with `grep` using the `-c` flag that will return the number of sequences in each FASTA file in `~/class/fasta`.

Number of sequences in each file:

What was your `grep` command:
