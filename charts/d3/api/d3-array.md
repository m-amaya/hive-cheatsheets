# Arrays (d3-array)

Array manipulation, ordering, searching, summarizing, etc.

## Statistics

Methods for computing basic summary statistics.

* `d3.min` - compute the minimum value in an array.
* `d3.max` - compute the maximum value in an array.
* `d3.extent` - compute the minimum and maximum value in an array.
* `d3.sum` - compute the sum of an array of numbers.
* `d3.mean` - compute the arithmetic mean of an array of numbers.
* `d3.median` - compute the median of an array of numbers (the 0.5-quantile).
* `d3.quantile` - compute a quantile for a sorted array of numbers.
* `d3.variance` - compute the variance of an array of numbers.
* `d3.deviation` - compute the standard deviation of an array of numbers.

## Search

Methods for searching arrays for a specific element.

* `d3.scan` - linear search for an element using a comparator.
* `d3.bisect` - binary search for a value in a sorted array.
* `d3.bisectRight` - binary search for a value in a sorted array.
* `d3.bisectLeft` - binary search for a value in a sorted array.
* `d3.bisector` - bisect using an accessor or comparator.
  * `<bisector>.left` - `bisectLeft`, with the given comparator.
  * `<bisector>.right` - `bisectRight`, with the given comparator.
* `d3.ascending` - compute the natural order of two values.
* `d3.descending` - compute the natural order of two values.

## Transformations

Methods for transforming arrays and for generating new arrays.

* `d3.cross` - compute the Cartesian product of two arrays.
* `d3.merge` - merge multiple arrays into one array.
* `d3.pairs` - create an array of adjacent pairs of elements.
* `d3.permute` - reorder an array of elements according to an array of indexes.
* `d3.shuffle` - randomize the order of an array.
* `d3.ticks` - generate representative values from a numeric interval.
* `d3.tickIncrement` - generate representative values from a numeric interval.
* `d3.tickStep` - generate representative values from a numeric interval.
* `d3.range` - generate a range of numeric values.
* `d3.transpose` - transpose an array of arrays.
* `d3.zip` - transpose a variable number of arrays.

## Histograms

Bin discrete samples into continuous, non-overlapping intervals.

* `d3.histogram` - create a new histogram generator.
  * `<histogram>` - compute the histogram for the given array of samples
  * `<histogram>.value` - specify a value accessor for each sample.
  * `<histogram>.domain` - specify the interval of observable values.
  * `<histogram>.thresholds` - specify how values are divided into bins.
* `d3.thresholdFreedmanDiaconis` - the Freedman-Diaconis binning rule.
* `d3.thresholdScott` - Scott's normal reference binning rule.
* `d3.thresholdSturges` - Sturges' binning formula.