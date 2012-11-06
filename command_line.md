---
layout: page
title: "Command Line"
tagline: "{how-to run PrimerSeq}"
---
{% include JB/setup %}

## Installation
1. Copy my project to where ever you want
2. You will need to have installed the [Java JRE](http://www.oracle.com/technetwork/java/javase/downloads/java-se-jre-7-download-432155.html).
3. If you use PrimerSeq from source files you will need to do a little more
setup. First, I recommend using python2.7. Next, you will need to install additional
python packages:
{% highlight bash %}
$ pip install pygr
$ pip install numpy
$ pip install matplotlib
$ wget http://networkx.lanl.gov/download/networkx/networkx-1.7.tar.gz
$ tar xvzf networkx-1.7.tar.gz
$ cd networkx-1.7
$ python setup.py install
{% endhighlight %}

## Run 
To run the program you will need several files:
* FASTA (eg. hg19.fa)
* gtf (I do not recommend using bigbed at this point)
* single or multiple SAM/BAM file (If it is already sorted then name it with `.sorted.bam` extension)

You can checkout the command line options by typing `python primer.py --help`:
{% highlight bash %}
usage: primer.py [-h] (-b BIG_BED | -g GTF) [--no-gene-id] -f FASTA -r RNASEQ
                 -t TARGET (--annotaton | --rnaseq | --both) [--psi PSI]
                 [--read-threshold READ_THRESHOLD] [--keep-temp] -o OUTPUT

Command line interface for designing primers

optional arguments:
  -h, --help            show this help message and exit
  -b BIG_BED            big bed file that defines the possible exons in a gene
  -g GTF                gtf file that defines the possible exons in a gene
  --no-gene-id          Use this flag if your gtf does not have a valid
                        gene_id
  -f FASTA              path to fasta file
  -r RNASEQ             path to SAM/BAM file(s) ("," delimited)
  -t TARGET             path to txt file with <strand><chr>:<start>-<end> for
                        each target on separate lines.
  --annotaton           only use junctions supported from annotation
  --rnaseq              only use junctions supported from RNA-Seq
  --both                use junctions from both RNA-Seq and annotation
  --psi PSI             Define inclusion level sufficient to define
                        constitutive exon. Valid: 0<psi<1.
  --read-threshold READ_THRESHOLD
                        Define the minimum number of read support necessary to
                        call a junction from RNA-Seq
  --keep-temp           Keep temporary files in your tmp directory
  -o OUTPUT             Output directory
{% endhighlight %}

### Example
The following command has paths where you should specify your own data.
{% highlight bash %}
python primer.py -g right.gtf -f path/to/hg19.fa -r path/to/unique.S1.sorted.bam -t mats.example.2.txt --both --psi .95 -o my/output/dir
{% endhighlight %}

**NOTE:** the gtf file should be sorted. To find how to sort the gtf type `python gtf.py --help`. Notice the example gtf file called **right.gtf** is
alreadly sorted.

To define your own targets (**-t** option) create a two column file with no header as specified below:
<table class="table table-hover">
<tr>
<th>ID</th>
<th>Target</th>
</tr>
<tr>
<td>1</td>
<td>-chr17:73969705-73969866</td>
</tr>
<tr>
<td>2</td>
<td>-chr9:123222849-123222945</td>
</tr>
</table>
