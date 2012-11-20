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

##Program

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
##Others
### Get options:
{% highlight perl linenos %}
#!/usr/bin/perl -w
=head1
Version 1.0
Author : YummyYang
Date : 2012.11.05
=head Example
	-a : [string] ,argument a
	-b : [string] ,argument b
Example : xxxx -a argu_a -b argu_b
=cut
use strict;
use Getopt::Long;
my ($argu_a,$argu_b);
GetOptions(
	"a:s" => \$argu_a;
	"b:s" => \$argu_b;
);
die `pod2text $0` if(!$argu_a || !$argu_b );
print "a:$argu_a\n";
print "b:$argu_b\n";
{% endhighlight %}
