# PerlScriptFrontiers
Perl script used in manuscript.

#!/usr/bin/env perl

use strict;
use warnings;

my $fastq;
my $ldx = 0;
while (<>) {
    chomp;
    $fastq->[$ldx++] = $_;
    if ($ldx == 4) {
        my $length = length $fastq->[1];
        if (($length >= 233) && ($length <= 273)) {
            print "$fastq->[0]\n$fastq->[1]\n$fastq->[2]\n$fastq->[3]\n";
        }
        $ldx = 0;
    }
}
