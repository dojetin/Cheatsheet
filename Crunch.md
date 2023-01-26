
```
crunch 1 8
```
crunch will display a wordlist that starts at a and ends at zzzzzzzz

```
crunch 1 6 abcdefg
```
crunch  will  display a wordlist using the character set abcdefg that starts at a and ends
at gggggg

```
crunch 1 6 abcdefg\
```
there is a space at the end of the character string.  In order for crunch to use the space
you  will  need  to  escape  it using the \ character.  In this example you could also put
quotes around the letters and not need the \, i.e. "abcdefg  ".   Crunch  will  display  a
wordlist using the character set abcdefg  that starts at a and ends at (6 spaces)

```
crunch 1 8 -f charset.lst mixalpha-numeric-all-space -o wordlist.txt
```
crunch  will  use  the  mixalpha-numeric-all-space character set from charset.lst and will
write the wordlist to a file named wordlist.txt.  The file will start with a and end  with
"        "

```
crunch  8  8  -f  charset.lst  mixalpha-numeric-all-space  -o  wordlist.txt -t @@dog@@@ -s
cbdogaaa
```
crunch  should  generate  a  8  character  wordlist  using  the  mixalpha-number-all-space
character  set  from charset.lst and will write the wordlist to a file named wordlist.txt.
The file will start at cbdogaaa and end at "  dog   "

```
crunch 2 3 -f charset.lst ualpha -s BB
```
crunch with start generating a wordlist at BB and end with ZZZ.  This  is  useful  if  you
have to stop generating a wordlist in the middle.  Just do a tail wordlist.txt and set the
-s parameter to the next word in the sequence.  Be sure to rename  the  original  wordlist
BEFORE you begin as crunch will overwrite the existing wordlist.

```
crunch 4 5 -p abc
```
The numbers aren't processed but are needed.
crunch will generate abc, acb, bac, bca, cab, cba.

```
crunch 4 5 -p dog cat bird
```
The numbers aren't processed but are needed.
crunch   will   generate   birdcatdog,  birddogcat,  catbirddog,  catdogbird,  dogbirdcat,
dogcatbird.

```
crunch 1 5 -o START -c 6000 -z bzip2
```
crunch will generate bzip2 compressed files with each file  containing  6000  words.   The
filenames of the compressed files will be first_word-last_word.txt.bz2



