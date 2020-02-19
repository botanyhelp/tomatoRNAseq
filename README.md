## tomatoRNAseq

### HiSeq fastq data 200203_NB551436_0114_AHVHNKBGXC

We have this information and are waiting for credentials:

* hiseq.huck.psu.edu
* sally-mackenzie/200203_NB551436_0114_AHVHNKBGXC/fastq
* requires an FTP client
* cannot be accessed from outside the Penn State domain

..as per instructions:

```
Your NextSeq run is complete, and the data are available on the HiSeq server in directory:

sally-mackenzie/200203_NB551436_0114_AHVHNKBGXC/fastq

The HiSeq server can be reached at hiseq.huck.psu.edu using the user name and password previously received. This server requires an FTP client to connect and cannot be accessed from outside the Penn State domain.  
```

UPDATE:
got it working via email today. 

### HiSeq fastq data 200203_NB551436_0114_AHVHNKBGXC download

We got the data with a PSU machine using Filezilla FTP client. 
Filezilla produced this output in the FTP client:

[downloadFilezillaOutput.txt](downloadFilezillaOutput.txt)

### HiSeq fastq data 200203_NB551436_0114_AHVHNKBGXC checksums

There are 14 fastq files with these checksums:

```
ls 200203_NB551436_0114_AHVHNKBGXC/fastq/*.gz|wc
     14      14     914

64 200203_NB551436_0114_AHVHNKBGXC]$ ls 200203_NB551436_0114_AHVHNKBGXC/fastq/*.gz|grep gz|sed 's/^/md5sum /'
cec24b9233d749a85fba471034f5d218  200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P1_S4_R1_001.fastq.gz
6b155ab0ab34dc5eaba2693a23c864e4  200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P1_S4_R2_001.fastq.gz
6d17a4373a53b3a838ea4809fc0d8f4d  200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P2_S5_R1_001.fastq.gz
971cfaf627e2cf71c08fbd0b186bc5fd  200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P2_S5_R2_001.fastq.gz
7ee8981f324d93f0319b8511d91e453a  200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P3_S6_R1_001.fastq.gz
d5eb13bd6f1564c256a80cdba1bfe8b1  200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P3_S6_R2_001.fastq.gz
fe21d4bfb758beb345fc3273217e5fe0  200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P1_S1_R1_001.fastq.gz
396ac84235e12d6817ad19533b3c0fff  200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P1_S1_R2_001.fastq.gz
ea3707990ab0a2746f03bc3a27dedad4  200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P2_S2_R1_001.fastq.gz
4e4272e8b7922ecb5cd4acc13e1ae655  200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P2_S2_R2_001.fastq.gz
1320493e071d5561cb90deaa5bf94d6c  200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P3_S3_R1_001.fastq.gz
f2304c35bd4b5066d22d83ac8afbd898  200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P3_S3_R2_001.fastq.gz
3295beef3677c3fa5ce027f57bfec7d2  200203_NB551436_0114_AHVHNKBGXC/fastq/Undetermined_S0_R1_001.fastq.gz
25127472adfae7e2750b38e9552b5a20  200203_NB551436_0114_AHVHNKBGXC/fastq/Undetermined_S0_R2_001.fastq.gz
```


### HiSeq fastqc 

We ran fastqc on this paired-end data like this using **ts** and **fastqc**:

```
64 200203_NB551436_0114_AHVHNKBGXC]$ ls /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/|sed 's#\(.*\)#ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/\1/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/\1.fastq.gz#'
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_DR_P1_S4_R1_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P1_S4_R1_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_DR_P1_S4_R2_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P1_S4_R2_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_DR_P2_S5_R1_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P2_S5_R1_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_DR_P2_S5_R2_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P2_S5_R2_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_DR_P3_S6_R1_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P3_S6_R1_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_DR_P3_S6_R2_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P3_S6_R2_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_R_P1_S1_R1_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P1_S1_R1_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_R_P1_S1_R2_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P1_S1_R2_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_R_P2_S2_R1_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P2_S2_R1_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_R_P2_S2_R2_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P2_S2_R2_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_R_P3_S3_R1_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P3_S3_R1_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/R_R_P3_S3_R2_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P3_S3_R2_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/Undetermined_S0_R1_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/Undetermined_S0_R1_001.fastq.gz
ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/Undetermined_S0_R2_001/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/Undetermined_S0_R2_001.fastq.gz

64 200203_NB551436_0114_AHVHNKBGXC]$ ls /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/|sed 's#\(.*\)#ts /usr/local/bin/fastqc -t 4 -f fastq -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastqc/\1/ /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/\1.fastq.gz#'|/bin/sh
0
1
2
3
4
5
6
7
8
9
10
11
12
13
```


These fastqc output were generated **before running trim_galore**:

[fastqc/R_DR_P1_S4_R1_001_fastqc.html](fastqc/R_DR_P1_S4_R1_001_fastqc.html)
[fastqc/R_DR_P1_S4_R2_001_fastqc.html](fastqc/R_DR_P1_S4_R2_001_fastqc.html)
[fastqc/R_DR_P2_S5_R1_001_fastqc.html](fastqc/R_DR_P2_S5_R1_001_fastqc.html)
[fastqc/R_DR_P2_S5_R2_001_fastqc.html](fastqc/R_DR_P2_S5_R2_001_fastqc.html)
[fastqc/R_DR_P3_S6_R1_001_fastqc.html](fastqc/R_DR_P3_S6_R1_001_fastqc.html)
[fastqc/R_DR_P3_S6_R2_001_fastqc.html](fastqc/R_DR_P3_S6_R2_001_fastqc.html)
[fastqc/R_R_P1_S1_R1_001_fastqc.html](fastqc/R_R_P1_S1_R1_001_fastqc.html)
[fastqc/R_R_P1_S1_R2_001_fastqc.html](fastqc/R_R_P1_S1_R2_001_fastqc.html)
[fastqc/R_R_P2_S2_R1_001_fastqc.html](fastqc/R_R_P2_S2_R1_001_fastqc.html)
[fastqc/R_R_P2_S2_R2_001_fastqc.html](fastqc/R_R_P2_S2_R2_001_fastqc.html)
[fastqc/R_R_P3_S3_R1_001_fastqc.html](fastqc/R_R_P3_S3_R1_001_fastqc.html)
[fastqc/R_R_P3_S3_R2_001_fastqc.html](fastqc/R_R_P3_S3_R2_001_fastqc.html)
[fastqc/Undetermined_S0_R1_001_fastqc.html](fastqc/Undetermined_S0_R1_001_fastqc.html)
[fastqc/Undetermined_S0_R2_001_fastqc.html](fastqc/Undetermined_S0_R2_001_fastqc.html)

### new Hiseq tomato RNAseq data trim_galore

Here we make the directories where **trim_galore** output will land:

```
64 200203_NB551436_0114_AHVHNKBGXC]$ mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/

64 200203_NB551436_0114_AHVHNKBGXC]$ ls 200203_NB551436_0114_AHVHNKBGXC/fastq/|grep gz|sed 's/[1,2]_001.*//'|sort|uniq|sed 's#\(.*\)#mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1/#'
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P1_S4_R/
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P2_S5_R/
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P3_S6_R/
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P1_S1_R/
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P2_S2_R/
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P3_S3_R/
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/Undetermined_S0_R/

64 200203_NB551436_0114_AHVHNKBGXC]$ ls 200203_NB551436_0114_AHVHNKBGXC/fastq/|grep gz|sed 's/[1,2]_001.*//'|sort|uniq|sed 's#\(.*\)#mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1/#'|/bin/sh`
```

Here we run **trim_galore** with **ts**:


```
64 200203_NB551436_0114_AHVHNKBGXC]$ ls 200203_NB551436_0114_AHVHNKBGXC/fastq/|grep gz|sed 's/[1,2]_001.*//'|sort|uniq|sed 's#\(.*\)#ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1 /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/\11_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/\12_001.fastq.gz#'
ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P1_S4_R /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P1_S4_R1_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P1_S4_R2_001.fastq.gz
ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P2_S5_R /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P2_S5_R1_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P2_S5_R2_001.fastq.gz
ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P3_S6_R /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P3_S6_R1_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_DR_P3_S6_R2_001.fastq.gz
ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P1_S1_R /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P1_S1_R1_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P1_S1_R2_001.fastq.gz

ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P2_S2_R /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P2_S2_R1_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P2_S2_R2_001.fastq.gz
ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P3_S3_R /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P3_S3_R1_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/R_R_P3_S3_R2_001.fastq.gz
ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/Undetermined_S0_R /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/Undetermined_S0_R1_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/Undetermined_S0_R2_001.fastq.gz

64 200203_NB551436_0114_AHVHNKBGXC]$ ls 200203_NB551436_0114_AHVHNKBGXC/fastq/|grep gz|sed 's/[1,2]_001.*//'|sort|uniq|sed 's#\(.*\)#ts /usr/local/bin05169/trim_galore  --phred33 --paired --gzip --fastqc --length 30 -o /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1 /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/\11_001.fastq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/fastq/\12_001.fastq.gz#'|/bin/sh
14
15
16
17
18
19
20
```

### new Hiseq tomato RNAseq data STAR alignment

First we make directories for output of STAR:
```
64 star_align]$ ls ../trim_galore/|sed 's/\(.*\)/mkdir \1/'
mkdir R_DR_P1_S4_R
mkdir R_DR_P2_S5_R
mkdir R_DR_P3_S6_R
mkdir R_R_P1_S1_R
mkdir R_R_P2_S2_R
mkdir R_R_P3_S3_R
mkdir Undetermined_S0_R
64 star_align]$ ls ../trim_galore/|sed 's/\(.*\)/mkdir \1/'|/bin/sh
```

..we create the commands to be run:
```
64 star_align]$ ls ../trim_galore|sed 's#\(.*\)#zts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1/\11_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1/\12_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/\1/#'

zts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P1_S4_R/R_DR_P1_S4_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P1_S4_R/R_DR_P1_S4_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P1_S4_R/
zts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P2_S5_R/R_DR_P2_S5_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P2_S5_R/R_DR_P2_S5_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P2_S5_R/
zts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P3_S6_R/R_DR_P3_S6_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P3_S6_R/R_DR_P3_S6_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P3_S6_R/
zts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P1_S1_R/R_R_P1_S1_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P1_S1_R/R_R_P1_S1_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P1_S1_R/
zts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P2_S2_R/R_R_P2_S2_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P2_S2_R/R_R_P2_S2_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P2_S2_R/
zts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P3_S3_R/R_R_P3_S3_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P3_S3_R/R_R_P3_S3_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P3_S3_R/
zts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/Undetermined_S0_R/Undetermined_S0_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/Undetermined_S0_R/Undetermined_S0_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/Undetermined_S0_R/
```
..and we start one **STAR** with **ts**:
```
64 star_align]$ ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P1_S4_R/R_DR_P1_S4_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P1_S4_R/R_DR_P1_S4_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P1_S4_R/
21

64 star_align]$ date; ts |grep finished|wc; ts|grep queued|wc; ts|grep running|wc
Thu Feb 13 05:50:56 EST 2020
     21     294    7472
      0       0       0
      1      26     674

```
..later on we see that it has finished:
```
64 star_align]$ date; ts |grep finished|wc; ts|grep queued|wc; ts|grep running|wc
Thu Feb 13 09:17:15 EST 2020
     22     322    8155
      0       0       0
      0       0       0
64 star_align]$ ls -altF R_DR_P1_S4_R/|sed 's/.*mda//'
total 10294896
        233 Feb 13 06:14 ./
       1866 Feb 13 06:14 Log.final.out
      27135 Feb 13 06:14 Log.out
       2925 Feb 13 06:14 Log.progress.out
 4518932463 Feb 13 06:14 Aligned.sortedByCoord.out.bam
    4001864 Feb 13 06:12 SJ.out.tab
 6018995519 Feb 13 06:12 Aligned.toTranscriptome.out.bam
         62 Feb 13 06:00 _STARgenome/
         57 Feb 13 06:00 _STARpass1/
        211 Feb 13 05:47 ../

64 star_align]$ samtools view R_DR_P1_S4_R/Aligned.sortedByCoord.out.bam |head
NB551436:114:HVHNKBGXC:2:21111:15659:17915      163     1       582     255     10M38S  =       13198   12690   AGGGAATATTTAAATATTTAAAAAAAAAAAAAAGTTAAATGAAAAAAA        666///////E/////A/A//AEAEE/E/EEE///E/////EEAEE/E        NH:i:1  HI:i:1  AS:i:81 nM:i:0
NB551436:114:HVHNKBGXC:4:11603:22392:8637       163     1       1380    255     24S20M  =       14690   13385   AGGTTGGGAGCGAAAATGAGTAAAAAAATAAAAAAAGAATTGTT    A//A/A6/6////EE6//A/EA///E///AAEA////E////EE    NH:i:1  HI:i:1  AS:i:86 nM:i:3
NB551436:114:HVHNKBGXC:1:11212:25230:11736      163     1       12977   255     74M     =       13067   238     CTTTAATTAATTCTCCAAAAACTTTTTAATTATTTACAACAACATAATGGTTCTCTCAAAAACTCCTTCTGATG      AAAAAAEEEEEE/EEEEEEEEEEEEEEEEEEEEEEEEEEEEAEEEEEE6EEEEEAEEEEEEAEEEEEEEEEEEE      NH:i:1  HI:i:1  AS:i:149        nM:i:0
NB551436:114:HVHNKBGXC:1:11312:15746:15953      163     1       12977   255     74M     =       13178   275     CTTTAATTAATTCTCCAAAAACTTTTTAATTATTTACAACAACATAATGGTTCTCTCAAAAACTCCTTCTGATG      AAAAAAEA//EEAEEEEE/AAAE/EE/EEEAEEEEA//EEEEEEA/EE/EE/EEEEEEE/<EEEE/A6EA<AE/      NH:i:1  HI:i:1  AS:i:146        nM:i:0
NB551436:114:HVHNKBGXC:1:13202:11693:17164      163     1       12977   255     74M     =       13198   295     CTTTAATTAATTCTCCAAAAACTTTTTAATTATTTACAACAACATAATGGTTCTCTCAAAAACTCCTTCTGATG      AAAAAEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE/EEEAEEEEEEEEEEEEEEEAEEEEEEEE<EEA      NH:i:1  HI:i:1  AS:i:146        nM:i:0
NB551436:114:HVHNKBGXC:1:21105:24513:9430       163     1       12977   255     74M     =       13178   275     CTTTAATTAATTCTCCAAAAACTTTTTAATTATTTACAACAACATAATGGTTCTCTCAAAAACTCCTTCTGATG      AAAA6EEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE6EEEAEEEEEEEE      NH:i:1  HI:i:1  AS:i:146        nM:i:0
NB551436:114:HVHNKBGXC:1:22312:21118:16052      163     1       12977   255     74M     =       13067   238     CTTTAATTAATTCTCCAAAAACTTTTTAATTATTTACAACAACATAATGGTTCTCTCAAAAACTCCTTCTGATG      AAAAAEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE      NH:i:1  HI:i:1  AS:i:149        nM:i:0
NB551436:114:HVHNKBGXC:2:21307:17417:13328      163     1       12977   255     74M     =       13067   238     CTTTAATTAATTCTCCAAAAACTTTTTAATTATTTACAACAACATAATGGTTCTCTCAAAAACTCCTTCTGATG      AAAAAEEEEEEEEEEEEEEEEEEEEEEEEEEAEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE      NH:i:1  HI:i:1  AS:i:149        nM:i:0
NB551436:114:HVHNKBGXC:2:23102:20049:12663      163     1       12977   255     22M1D53M        =       13063   233     CTTTAATTAATTCTCCAAAAACTTTTAATTATTTACAACAACATAATGGTTCTCTCAAAAACTCCTTCTGATGAT     AAAAAEEEEEEEEEEEEEEEEEEEEEAEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEE     NH:i:1  HI:i:1  AS:i:137        nM:i:4
NB551436:114:HVHNKBGXC:2:23207:17019:3323       163     1       12977   255     74M     =       13178   275     CTTTAATTAATTCTCCAAAAACTTTTTAATTATTTACAACAACATAATGGTTCTCTCAAAAACTCCTTCTGATG      AAAAAEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEAEEEEEEEAEEEEEEEEEEEEEA/EEEEEEEEEEEE      NH:i:1  HI:i:1  AS:i:146        nM:i:0
64 star_align]$ cat /tmp/ts-out.1PHURt
Feb 13 05:50:31 ..... started STAR run
Feb 13 05:50:31 ..... loading genome
Feb 13 05:51:07 ..... started 1st pass mapping
Feb 13 06:00:31 ..... finished 1st pass mapping
Feb 13 06:00:32 ..... inserting junctions into the genome indices
Feb 13 06:01:20 ..... started mapping
Feb 13 06:12:41 ..... finished mapping
Feb 13 06:12:41 ..... started sorting BAM
Feb 13 06:14:36 ..... finished successfully
```

That looks okay and so we start the other 6:
```
64 star_align]$ ls ../trim_galore|sed 's#\(.*\)#ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1/\11_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1/\12_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/\1/#'|tail -6
ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P2_S5_R/R_DR_P2_S5_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P2_S5_R/R_DR_P2_S5_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P2_S5_R/
ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P3_S6_R/R_DR_P3_S6_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_DR_P3_S6_R/R_DR_P3_S6_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P3_S6_R/
ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P1_S1_R/R_R_P1_S1_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P1_S1_R/R_R_P1_S1_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P1_S1_R/
ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P2_S2_R/R_R_P2_S2_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P2_S2_R/R_R_P2_S2_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P2_S2_R/
ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P3_S3_R/R_R_P3_S3_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/R_R_P3_S3_R/R_R_P3_S3_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P3_S3_R/
ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/Undetermined_S0_R/Undetermined_S0_R1_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/Undetermined_S0_R/Undetermined_S0_R2_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/Undetermined_S0_R/

64 star_align]$ ls ../trim_galore|sed 's#\(.*\)#ts STAR --genomeDir /data5/tomato_RNAseq/STAR_INDEX --readFilesCommand zcat --readFilesIn /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1/\11_001_val_1.fq.gz /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/trim_galore/\1/\12_001_val_2.fq.gz --outSAMtype BAM SortedByCoordinate --limitBAMsortRAM 150000000000 --twopassMode Basic --outFilterMultimapNmax 1 --quantMode TranscriptomeSAM --runThreadN 10 --outFileNamePrefix /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/\1/#'|tail -6|/bin/sh
22
23
24
25
26
27

64 star_align]$ date; ts |grep finished|wc; ts|grep queued|wc; ts|grep running|wc
Thu Feb 13 09:22:59 EST 2020
     22     322    8155
      0       0       0
      6     156    4054
```
..later on things look complete:
```
64 tmp]$ date; ts |grep finished|wc; ts|grep queued|wc; ts|grep running|wc
Thu Feb 13 10:02:01 EST 2020
     28     490   12263
      0       0       0
      0       0       0
```

### new Hiseq tomato RNAseq data QoRTs

We start with new directory and file here:

/data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/tomato_05_QoRTs.sh

First we make a directory where the output can reside, one for each sample:
```
64 QoRTs]$ ls ../star_align/|egrep -v bash|sed 's#\(.*\)#mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/\1#'
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_DR_P1_S4_R
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_DR_P2_S5_R
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_DR_P3_S6_R
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_R_P1_S1_R
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_R_P2_S2_R
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_R_P3_S3_R
mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/Undetermined_S0_R
64 QoRTs]$ ls ../star_align/|egrep -v bash|sed 's#\(.*\)#mkdir /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/\1#'|/bin/sh 
```
We produce these commands:

```
64 QoRTs]$ ls ../star_align/|egrep -v bash|sed 's#\(.*\)#ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/\1/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/\1/#'
ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P1_S4_R/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_DR_P1_S4_R/
ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P2_S5_R/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_DR_P2_S5_R/
ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_DR_P3_S6_R/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_DR_P3_S6_R/
ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P1_S1_R/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_R_P1_S1_R/
ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P2_S2_R/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_R_P2_S2_R/
ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/R_R_P3_S3_R/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/R_R_P3_S3_R/
ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/Undetermined_S0_R/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/Undetermined_S0_R/
```
..and run them by piping into bash:
```
64 QoRTs]$ ls ../star_align/|egrep -v bash|sed 's#\(.*\)#ts QoRTs QC --stranded --minMAPQ 25 --runFunctions GeneCalcs,JunctionCalcs,annotatedSpliceExonCounts,writeKnownSplices,writeNovelSplices,writeSpliceExon,writeGeneCounts,writeDEXSeq,writeGeneBody,writeDESeq /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/star_align/\1/Aligned.sortedByCoord.out.bam /data5/tomato_RNAseq/genome/Solanum_lycopersicum.SL3.0.43.gtf /data5/200203_NB551436_0114_AHVHNKBGXC/200203_NB551436_0114_AHVHNKBGXC/QoRTs/\1/#'|/bin/sh
28
29
30
31
32
33
34

```
..and we happily notice that they have all reached a state of **running**:
```
64 QoRTs]$ date; ts |grep finished|wc; ts|grep queued|wc; ts|grep running|wc
Tue Feb 18 11:23:42 EST 2020
     28     490   12263
      0       0       0
      7      91    3798
```
..and 15 minutes later we see that one has completed:
```
64 QoRTs]$ date; ts |grep finished|wc; ts|grep queued|wc; ts|grep running|wc
Tue Feb 18 11:38:20 EST 2020
     29     505   12820
      0       0       0
      6      78    3246
```
..but that is NOT because we are running them serially.  As shown,
all 7 jobs were running and here we see that we have **ts** set to
run up to 16 jobs concurrently:
```
64 QoRTs]$ ts -S
16
```
..and we see them completed:

```
64 QoRTs]$ date; ts |grep finished|wc; ts|grep queued|wc; ts|grep running|wc
Tue Feb 18 12:10:18 EST 2020
     35     595   16114
      0       0       0
      0       0       0

```

