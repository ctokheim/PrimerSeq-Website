---
layout: page
title: "FAQ"
description: ""
tagline: "{Frequently Asked Questions}"
---
{% include JB/setup %}

<div class="accordion" id="accordion2">
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseOne">
      Why does sorting a GTF seem to stall or fail?
    </a>
  </div>
  <div id="collapseOne" class="accordion-body collapse in">
    <div class="accordion-inner">
Sorting a GTF fails likely because of insufficient memory. You can change the allotted memory by editing the PrimerSeq.cfg
file found in the PrimerSeq installation directory. Change the "sort" option above the 1536 MB default. You may need to install
a 64 bit version of java or switch to computer with more memory. The only available PrimerSeq download
for Windows is 32 bit. You could switch to a 64 bit linux computer.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseTwo">
      How do I open .gz files?
    </a>
  </div>
  <div id="collapseTwo" class="accordion-body collapse">
    <div class="accordion-inner">
If you are using Windows, you can use a graphical program like <a href="http://www.7-zip.org/">7zip</a>. For Linux and Mac OS you can use the <i>gunzip</i> command
<br></br>
{% highlight bash %}
$ gunzip your_file.gz
{% endhighlight %}

    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseThree">
      Does PrimerSeq support Mac OS?
    </a>
  </div>
  <div id="collapseThree" class="accordion-body collapse">
    <div class="accordion-inner">
PrimerSeq does not currently have a Mac OS download. However, PrimerSeq was built to be compatiable with Mac OS and a download should be coming shortly.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseFour">
      Does PrimerSeq support Linux?
    </a>
  </div>
  <div id="collapseFour" class="accordion-body collapse">
    <div class="accordion-inner">
PrimerSeq does support linux, <b>Linux Mint 13</b> and <b>Ubuntu >=12.04</b>. Follow the installation instructions
found <a href="linux.html">here</a>.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseFive">
     PrimerSeq says the Java JRE is required, what should I do?
    </a>
  </div>
  <div id="collapseFive" class="accordion-body collapse">
    <div class="accordion-inner">
      PrimerSeq requires the Java JRE to be installed on your computer.
      You can install the <a href="http://www.oracle.com/technetwork/java/javase/downloads/java-se-jre-7-download-432155.html">Java JRE</a> from oracle.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseSix">
      How do I decompress the .2bit format?
    </a>
  </div>
  <div id="collapseSix" class="accordion-body collapse">
    <div class="accordion-inner">
You should use the <i>twoBitToFa</i> utility from UCSC. You can find the utility for Mac OS and linux <a href="http://hgdownload.cse.ucsc.edu/admin/exe/">here</a>.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseEight">
      The PrimerSeq results say that Primer3 could not design primers, what should I do?
    </a>
  </div>
  <div id="collapseEight" class="accordion-body collapse">
    <div class="accordion-inner">
Try adjusting the allowed PCR product lengths in the Primer3 configuration file. Press <i>Edit->Primer3</i>. You can edit the allowed PCR product lengths by changing the first parameter in the displayed file.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseNine">
      What coordinate format should I use?
    </a>
  </div>
  <div id="collapseNine" class="accordion-body collapse">
    <div class="accordion-inner">
PrimerSeq assumes the first nucleotide in a chromosome is at position 0. The end coordinate is not inclusive.
Strand information is provided as either + or -. A fictitous example is shown below.
<br>

<pre>-chr8:0-100</pre>
This example would therefore be the first 100 nucleotides on the negative strand of chromosome 8. If using the UCSC genome browser, subtract 1 from the start coordinate.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseTen">
      Why does loading a FASTA, GTF, or SAM/BAM file take a long time?
    </a>
  </div>
  <div id="collapseTen" class="accordion-body collapse">
    <div class="accordion-inner">
The length of loading files varies. The first time you use a FASTA, PrimerSeq will need to index the FASTA
which may take several minutes. Subsequent loading for the FASTA should be almost instantaneous. Average sized
GTF files generally take ~1 minute to load. Loading a sorted BAM file named with a <code>.sorted.bam</code>
extenstion should be quick. If you use a SAM file, PrimerSeq will convert the SAM file to a BAM file and then sort the resulting BAM file. This process of converting from a SAM to BAM will take a considerable ammount of time due to the typical large file sizes.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion2" href="#collapseEleven">
      I am not using Human/hg19, what should I enter for the "Genome" and "Assembly" text fields?
    </a>
  </div>
  <div id="collapseEleven" class="accordion-body collapse">
    <div class="accordion-inner">
Specifying a genome and assembly is needed only for <i>in-silico</i> PCR. You can find the designated "Genome"
names in the "Genome" dropdown of <a href="http://genome.ucsc.edu/cgi-bin/hgGateway">UCSC's in-silico PCR</a>.
You can also find the "assembly" in the "assembly" dropdown in <a href="http://genome.ucsc.edu/cgi-bin/hgGateway">UCSC's in-silico PCR</a>.

For your convenience, the "Genome" and "Assembly" name of common species is below. You should type your species name <b>exactly</b> as it appears:

<table class="table">
  <thead>
    <tr>
      <th>Genome</th>
      <th>Assembly</th>
    </tr>
  </thead>
  <tbody>
    <tr>
     <td>Human</td>
     <td>hg19, hg18, etc.</td>
    </tr>
    <tr>
     <td>Chimp</td>
     <td>panTro4, panTro3, etc.</td>
    </tr>
    <tr>
     <td>Rhesus</td>
     <td>rheMac3, rheMac2, etc.</td>
    </tr>
    <tr>
     <td>Mouse</td>
     <td>mm10, mm9, etc.</td>
    </tr>
    <tr>
     <td>Rat</td>
     <td>rn5, rn4, etc.</td>
    </tr>
  </tbody>
</table>

    </div>
  </div>
</div>
</div>
