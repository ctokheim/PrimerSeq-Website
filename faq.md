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
a 64 bit version of java or switch to computer with more memory.
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
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion3" href="#collapseThree">
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
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion4" href="#collapseFour">
      Does PrimerSeq support Linux?
    </a>
  </div>
  <div id="collapseFour" class="accordion-body collapse">
    <div class="accordion-inner">
PrimerSeq does support linux. There is a 32 bit download tested on Ubuntu 12.04. For best support, use Ubuntu >=12.04 or Linux Mint >=13.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion5" href="#collapseFive">
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
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion6" href="#collapseSix">
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
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion7" href="#collapseSeven">
      In linux, there is an error with the GNU C Library ("libc" or "glibc")?
    </a>
  </div>
  <div id="collapseSeven" class="accordion-body collapse">
    <div class="accordion-inner">
You must have a GNU C Library >2.14. This means you should use a recent linux distribution like Ubuntu >=12.04. You can check your version number with the <b>ldd --version</b> command.
    </div>
  </div>
</div>
<div class="accordion-group">
  <div class="accordion-heading">
    <a class="accordion-toggle" data-toggle="collapse" data-parent="#accordion8" href="#collapseEight">
      The PrimerSeq results say that Primer3 could not design primers, what should I do?
    </a>
  </div>
  <div id="collapseEight" class="accordion-body collapse">
    <div class="accordion-inner">
Try adjusting the allowed PCR product lengths in the Primer3 configuration file. Press <i>Edit->Primer3</i>. You can edit the allowed PCR product lengths by changing the first parameter in the displayed file.
    </div>
  </div>
</div>
</div>
