# bamCoverageCalculator
Calculate the mean and variance of read depth across sequences.

## Usage

```text
bamCoverageCalculator v1.0.5
A multithreaded tool for calculating the mean and variance of read depth across specified regions of sequences.
https://github.com/liu-congcong/bamCoverageCalculator

Usage:
  bamCoverageCalculator [options]

Options:
  -i    Path to the input sorted bam file
  -o    Path to the outputCoverage file
  -t    Number of threads (default: 1)
  -r    Path to the input region file (default: none)
  -h    Hash table size (default: 100000000)
  -I    Minimum alignment identity (0-1, default: 0.0)
  -M    Minimum mapping quality (0-255, default: 0)
```

## File Formats

### Input Region File (-r)

A tab-delimited file specifying the regions for coverage calculation.

Each line contains three columns, with no header line.

|`Sequence ID`|`Start Position`|`End Position`|
|:-----------:|:--------------:|:------------:|
|     id1     |      1000      |     5000     |
|     id2     |      1000      |     5000     |
|     id2     |      3000      |     6000     |

### Output Coverage File (-o)

A tab-delimited file containing the mean and variance of read depth for each specified sequence region.

Each line contains five columns, with a header line.

|Sequence ID|Start|End |Mean|Variance|
|:---------:|:---:|:--:|:--:|:------:|
|    id1    |1000 |5000|0.1 |0.2     |
|    id2    |1000 |5000|0.2 |0.4     |
|    id2    |3000 |6000|0.3 |0.6     |
