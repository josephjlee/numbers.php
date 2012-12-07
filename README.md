numeric.ly.js - an advanced mathematics toolkit for JavaScript and Node.js
developed by Steve Kaliski, [@sjkaliski](http://twitter.com/sjkaliski)


## Description

Numeric.ly provides a comprehensive set of mathematical tools that currently are not offered in JavaScript.  These tools include:

* Basic calculations
* Calculus
* Matrix Operations
* Prime Numbers
* Statistics
* More...

A few things to note before using: JavaScript, like many languages, does not necessarily manage floating points as well as we'd all like it to. For example, if adding decimals, the addition tool won't return the exact value. This is an unfortunate error. Precautions have been made to account for this. After including numeric, you can set an error bound. Anything in this will be considered an "acceptable outcome."

The primary uses cases are client side operations which the DOM will recognize (e.g. 1.1px == 1px). It can be used for data analysis, calculations, etc. on the server as well.

## How to use

Numeric.ly is pretty straightforward to use.

For example, if we wanted to estimate the integral of sin(x) from -2 to 4, we could:

Use riemann integrals (with 200 subdivisions)

```javascript
var func = function(x) {
  return Math.sin(x);
}

numeric.calculus.riemann(func, -2, 4, 200);
```

Or adaptive simpson quadrature (with epsilon .0001)

```javascript
numeric.calculus.adaptiveSimpson(func, -2, 4, .0001);
```

Say we wanted to run some matrix calculations:

We can add two matrices

```javascript
var array1 = [0, 1, 2];
var array2 = [3, 4, 5];

numeric.matrix.addition(array1, array2);
```

We can transpose a matrix

```javascript
numeric.matrix.transpose(array);
```

Numeric.ly also includes some basic prime number analysis.  We can check if a number is prime:

```javascript
//basic check
numeric.prime.simple(number);

//elliptic analysis (good for huge numbers)
numeric.prime.elliptic(number);
```

The statistics tools include mean, median, mode, standard deviation, random sample generator, correlation, confidence intervals, t-test, chi-square, and more.

```javascript
numeric.statistic.mean(array);
numeric.statistic.median(array);
numeric.statistic.mode(array);
numeric.statistic.standardDev(array);
numeric.statistic.randomSample(lower, upper, n);
numeric.statistic.correlation(array1, array2);
```
For further documentation, check out our [JSDoc](http://jsdoc.info/sjkaliski/numeric.ly/)

## Test

Tests have been written for basic operations (addition, product, gcd, etc).

To execute, run:

```
make test
```

## Contributors
* Steve Kaliski - [@sjkaliski](http://twitter.com/sjkaliski)
* David Byrd - [@davidbyrd11](http://twitter.com/davidbyrd11)
* Ethan Resnick - [@studip101](http://twitter.com/studip101)