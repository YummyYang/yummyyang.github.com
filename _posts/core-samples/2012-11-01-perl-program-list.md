---
layout: post
category : perl
tags : [perl, bioinformatics]
title: Perl Program List
tagline: code for bioinformatics
---
{% include JB/setup %}
### MyBioPerl
The `MyBioPer` is my bio perl codes.

	status : in the initial stage

Perl Program List:

### CG Rich:

{% highlight perl linenos %}
sub cg_percentage{
	$dna = shift;
	return (int (100 * ($dna =~ tr/CGcg//)/(length $dna)))."%";
}	
my $dna = "TTAtTTATTTTTTTTTTTTATCGGCATTTAACCGGGCCACTGGAACCT";
print "cg percentage:".cg_percentage($dna)."\n";
{% endhighlight %}

##Utils
### Get File Data:
{% highlight perl linenos %}
sub get_file_data{
	my($file_name) = @_;
	my @filedata = ();
	die("Can't open:$filename\n") unless(open(FILE,$filename));
	@filedata = <FILE>;
	close FILE;
	return @filedata;
}
my @file_data = get_file_data('get_file');
print @file_data;

{% endhighlight %}

