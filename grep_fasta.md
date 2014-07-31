Grep and fasta files
====================

Each sequence in a fasta file begins with a header line (">" followed by a sequence id). Sequence data follows and is usually wrapped (making multiple lines).

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
$head test.fasta
>seq1
ATCGATCGCnTCGGGTACT
TCAGnAAAATGCTCTGATC
TCAG
>seq2
TGCGATCCCTACGTCATCA
AAATCGCTAGnnTCA
grep -c "AA" test.fasta
```

A) 5

B) 2

C) 3

D) I don't know

## Code challenge:
Given what you know about fasta file format, write a command with `grep` using the `-c` flag that will return the number of sequences in each fasta file in `~/class/fasta`.

Number of sequences in each file:

What was your `grep` command:
