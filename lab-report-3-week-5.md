# Week 5 Lab Report 3
## Researching Commands (grep)
### grep -c pattern filename
~~~
$ grep -c NO rr74.txt
114
~~~
~~~
$ grep -c 2 rr166.txt
140
~~~
~~~
$ grep -c CSC rr172.txt
55
~~~
### grep -s
### grep -m
~~~
$ grep -m 5 "2" rr74.txt
        2] suggested that inhibition of NO increases acute hypoxic
        these isoforms [ 9, 10, 11, 12] suggest that eNOS-derived
        hypertension in mice that lack eNOS [ 9, 12]. In the
          We studied F1-generation SV129 (Taconic, Germantown,
          Within 24-36 h of birth, pups and dam were placed in
~~~
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