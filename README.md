<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Loss functions

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> SGD loss functions.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/ml-base-sgd-loss-functions
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var lossFunctions = require( '@stdlib/ml-base-sgd-loss-functions' );
```

#### lossFunctions()

Returns a list of SGD loss functions.

```javascript
var out = lossFunctions();
// e.g., returns [ 'epsilon-insensitive', 'hinge', 'huber', 'log', 'modified-huber', 'perceptron', 'squared-epsilon-insensitive', 'squared-error', 'squared-hinge' ]
```

The output array contains the following loss functions:

-   `epsilon-insensitive`: penalty is the absolute value of the error whenever the absolute error exceeds epsilon and zero otherwise.
-   `hinge`: hinge loss function. Corresponds to a soft-margin linear Support Vector Machine (SVM), which can handle non-linearly separable data.
-   `huber`: squared-error loss for observations with error smaller than epsilon in magnitude, linear loss otherwise. Should be used in order to decrease the influence of outliers on the model fit.
-   `log`: logistic loss function. Corresponds to Logistic Regression.
-   `modified-huber`: Huber loss function variant for classification.
-   `perceptron`: hinge loss function without a margin. Corresponds to the original perceptron by Rosenblatt (1957).
-   `squared-epsilon-insensitive`: squared epsilon insensitive loss function.
-   `squared-error`: squared error loss (i.e., the squared difference of the observed and fitted values).
-   `squared-hinge`: squared hinge loss function SVM (L2-SVM).

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var contains = require( '@stdlib/array-base-assert-contains' ).factory;
var lossFunctions = require( '@stdlib/ml-base-sgd-loss-functions' );

var isLossFunction = contains( lossFunctions() );

var bool = isLossFunction( 'hinge' );
// returns true

bool = isLossFunction( 'log' );
// returns true

bool = isLossFunction( 'beep' );
// returns false
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->

* * *

<section class="c">

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="usage">

### Usage

```c
#include "stdlib/ml/base/sgd/loss_functions.h"
```

#### STDLIB_ML_SGD_LOSS_FUNCTION

An enumeration of SGD loss functions with the following fields:

-   **STDLIB_ML_SGD_EPSILON_INSENSITIVE**: penalty is the absolute value of the error whenever the absolute error exceeds epsilon and zero otherwise.
-   **STDLIB_ML_SGD_HINGE**: corresponds to a soft-margin linear Support Vector Machine (SVM), which can handle non-linearly separable data.
-   **STDLIB_ML_SGD_HUBER**: squared-error loss for observations with error smaller than epsilon in magnitude, linear loss otherwise.
-   **STDLIB_ML_SGD_LOG**: corresponds to Logistic Regression.
-   **STDLIB_ML_SGD_MODIFIED_HUBER**: Huber loss function variant for classification.
-   **STDLIB_ML_SGD_PERCEPTRON**: corresponds to the original perceptron by Rosenblatt (1957).
-   **STDLIB_ML_SGD_SQUARED_EPSILON_INSENSITIVE**: squared epsilon insensitive loss function.
-   **STDLIB_ML_SGD_SQUARED_ERROR**: squared difference of the observed and fitted values.
-   **STDLIB_ML_SGD_SQUARED_HINGE**: squared hinge loss function SVM (L2-SVM).

```c
#include "stdlib/ml/base/sgd/loss_functions.h"

const enum STDLIB_ML_SGD_LOSS_FUNCTION v = STDLIB_ML_SGD_HINGE;
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

### Notes

-   Enumeration constants should be considered opaque values, and one should **not** rely on specific integer values.

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

</section>

<!-- /.examples -->

</section>

<!-- /.c -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ml-base-sgd-loss-functions.svg
[npm-url]: https://npmjs.org/package/@stdlib/ml-base-sgd-loss-functions

[test-image]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ml-base-sgd-loss-functions/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ml-base-sgd-loss-functions?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ml-base-sgd-loss-functions.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ml-base-sgd-loss-functions/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/tree/deno
[deno-readme]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/tree/umd
[umd-readme]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/tree/esm
[esm-readme]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ml-base-sgd-loss-functions/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ml-base-sgd-loss-functions/main/LICENSE

</section>

<!-- /.links -->
