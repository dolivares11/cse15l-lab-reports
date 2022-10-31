# Week 5 Lab Report 3
## Researching Commands (grep)
### grep -c pattern filename
~~~
$ grep -c NO rr74.txt
114
~~~
-c is printing a count of how many matches it got with the word "NO". This is useful because if you had a text document where you wanted to know how many times a certain word appeared and wanted to know quickly then this option would be very useful.
~~~
$ grep -c 2 rr166.txt
140
~~~
-c is printing a count of how many matches it got with the character "2". This is useful because if you had a text document where you the user input the amount of times something happened and you wanted to count how many times 2 came up or another number this command would be very useful for that.
~~~
$ grep -c CSC rr172.txt
55
~~~
-c is printing a count of how many matches it got with "CSC". This is useful because when you are trying to find how many times something appeared in a text, then you would be able to know in a matter of seconds using this option. 
### grep -w
~~~
$ grep -w "2" rr74.txt
        2] suggested that inhibition of NO increases acute hypoxic
          2 O. RNA was quantified and samples
          2 O and 50 ng were used in
          2 -, NO
          Plasma samples 1 μl were added to 2 ml vanadium III
          As shown in Fig. 2, lung eNOS protein levels were
        2 gas. The hypobaric chambers used in
        2 , but were not increased when rats
        2 . This suggests that hypoxia inhibited
        2 tension [ 42, 40]. In agreement with
~~~
The -w option finds only the whole word "2". This is useful because if we were just doing regular two, then it could find instances of 2 that are not a word by itself. However, when we use -w we ensure that each instance found is a whole word "2" by itself.
~~~
$ grep -w "B" rr167.txt
        B. cepacia also poses a threat to
        B. cepacia is isolated from sputum in
        B. cepacia , a very diverse species,
        B. cepacia complex. Genomovar III is
        B. cepacia genomovar isolated from CF
        B. cepacia isolates in CF patients.
        B. cepacia 's transmissibility from
        B. cepacia syndrome, which results in
        B. cepacia as well as
        B. cepacia strains to PG-1 correlates
        B. cepacia cells and to purified
          B. cepacia ATCC strains 25416 and
          B. cepacia epidemic strain marker
          B. cepacia at an elevated salt
          B. cepacia 25416, both typically at
          B. cepacia 25416 were immobilized
          Activity of PG-1 on P. aeruginosaand B.
          B. cepacia were determined in
          B. cepacia strains was 5.02 μg/ml,
          B. cepacia were 0.17 μg/ml and 8.40
          B. cepacia differed significantly (
          B. cepacia 25416 (PG-1 resistant)
          B. cepacia , and at an 125I-GGPG
          B. cepacia cells appeared larger
          B. cepacia 25416 cells were 0.755
          B. cepacia cells (6.00 μm 2) was
          B. cepacia 25416, we devised a
          B. cepacia differed by 4.6-fold
          B. cepacia C4813) and repeated the
          B. cepacia LPS and lipid A were
          B. cepacia 25416. Injection of LPS
          B. cepacia strain (Fig. 4). Binding
          B. cepacia LPS at protegrin
          B. cepacia bound PG-1 equally (≈
        B. cepacia strains to protegrin PG-1
        B. cepacia . We also found that at
        B. cepacia and its lipid A than to
        B. cepacia needed exposure to much
        B. cepacia to PG-1 is a consequence
        sensitivity to the antibacterial lipopeptide polymyxin B is
        B is also imparted by the absence or masking of critical
        attachment of polymyxin B to
        Yersinia resistance to polymyxin B
        B. cepacia to conventional
        B. cepacia than to
        B. cepacia bound almost exactly
        B. cepacia , one of these phosphates
        B. cepacia LPS was only one-third of
        B. cepacia LPS binds about as much
        B. cepacia LPS binds protegrin less
        B. cepacia and
        B. cepacia , as compared to lipid A
        B. cepacia LPS and lipid A can help
        B. cepacia to protegrins and to
        B. cepacia , and support a hypothesis
        B. cepacia to protegrin is due
~~~
The option -w here is only finding where the whole phrase B is located by itself. The reason this is useful is to find only things with the whole word phrase or word "B". This would be useful if you were trying to find a key phrase within a text or a name, and only wanted the whole version to be found not connected to anything else.
~~~
$ grep -w "P" rr196.txt
          P = 0.001).
          P = 0.51).
          P value of 0.05 or less was
          P = 0.42), the differences in lung
          P < 0.0001). Thus, H
          P value for increased expression in
          P = 0.06). Note that although the
          P = 57). For SERCA 2, 38.9% of
          P = 0.99).
          P value of 0.015, and the
          P value of 0.023. There was no
~~~
The option -w here is finding where the whole word "P" is present within rr196.txt. This is useful here because we wanted to find all the instances where P was stand alone. This would be useful in other scenarios where I would want to find one stand alone word and the places it occured solely with nothing else connected to it.
### grep -m
~~~
$ grep -m 5 "2" rr74.txt
        2] suggested that inhibition of NO increases acute hypoxic
        these isoforms [ 9, 10, 11, 12] suggest that eNOS-derived
        hypertension in mice that lack eNOS [ 9, 12]. In the
          We studied F1-generation SV129 (Taconic, Germantown,
          Within 24-36 h of birth, pups and dam were placed in
~~~
The option -m here is to count a maximum occurrences of 5 of the word "2". This is useful because if I only wanted the first x number of occurrences of a certain word, then that would be available to me.
~~~
$ grep -m 10 "B" rr167.txt
        Burkholderia cepacia has become the
        B. cepacia also poses a threat to
        B. cepacia is isolated from sputum in
        B. cepacia , a very diverse species,
        B. cepacia complex. Genomovar III is
        B. cepacia genomovar isolated from CF
        B. cepacia isolates in CF patients.
        B. cepacia 's transmissibility from
        B. cepacia syndrome, which results in
        B. cepacia as well as
~~~
The option -m here is to count the maximum occurences of "B" 10 times. It presents the first 10 times that B is presented to me in the rr167.txt. The usefulness of this is that it allows the user to be able to find the first x number of occurrences that they want and nothing else if it is not relevant to them.
~~~
$ grep -m 10 "P " rr196.txt
          P = 0.001).
          P = 0.51).
          P value of 0.05 or less was
          P = 0.42), the differences in lung
          P < 0.0001). Thus, H
          P value for increased expression in
          P = 0.06). Note that although the
          P = 57). For SERCA 2, 38.9% of
          P = 0.99).
          P value of 0.015, and the
~~~
The option -m here is to count the maximum occurrences of "P" 10 times. The usefulness of this is that if there were more than 10 times "P" showed up, but we only wanted the first x amount of times then the -m option allows us to do that.