---
layout: post
category : perl
tags : [perl, bioinformatics]
title: Perl Program List
tagline: code for bioinformatics
---
{% include JB/setup %}
## MyBioPerl
The `MyBioPer` is my bio perl codes.

	status : in the initial stage

Perl Program List:

<ul class="posts">
  {% for tag in site.tags %}
  {{ if tag = bioinformatics }}
  <ul>
    {% assign pages_list = tag[1] %}  
    {% include JB/pages_list %}
  </ul>
  {{ endif }}
  {% endfor %}
</ul>

## CG Rich:
	code:
	sub cg_percentage{
		$dna = shift;
		return (int (100 * ($dna =~ tr/CGcg//)/(length $dna)))."%";
	}	
	my $dna = "TTAtTTATTTTTTTTTTTTATCGGCATTTAACCGGGCCACTGGAACCT";
	print "cg percentage:".cg_percentage($dna)."\n";

