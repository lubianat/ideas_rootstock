# Automated scholarly manuscripts on GitHub - lubianat`s idea mod

<!-- usage note: edit the H1 title above to personalize the manuscript -->

[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://lubianat.github.io/ideas_rootstock/)
[![PDF Manuscript](https://img.shields.io/badge/manuscript-PDF-blue.svg)](https://lubianat.github.io/ideas_rootstock/manuscript.pdf)
[![GitHub Actions Status](https://github.com/lubianat/ideas_rootstock/workflows/Manubot/badge.svg)](https://github.com/lubianat/ideas_rootstock/actions)
[![Travis Build Status](https://travis-ci.com/lubianat/ideas_rootstock.svg?branch=master)](https://travis-ci.com/lubianat/ideas_rootstock)
<!-- usage note: delete CI badges above for services not used by your manuscript -->

## Project idea description

<!-- usage note: edit this section. -->

This repository is a template manuscript (a.k.a. rootstock) for open project ideas.

Actual manuscript instances will clone this repository (see [`SETUP.md`](SETUP.md)) and replace this paragraph with a description of their manuscript.

## Manubot

<!-- usage note: do not edit this section -->

Manubot is a system for writing scholarly manuscripts via GitHub.
Manubot automates citations and references, versions manuscripts using git, and enables collaborative writing via GitHub.
An [overview manuscript](https://greenelab.github.io/meta-review/ "Open collaborative writing with Manubot") presents the benefits of collaborative writing with Manubot and its unique features.
The [rootstock repository](https://git.io/fhQH1) is a general purpose template for creating new Manubot instances, as detailed in [`SETUP.md`](SETUP.md).

Please open [an issue](https://git.io/fhQHM) for questions related to Manubot usage, bug reports, or general inquiries.

### Repository directories & files

The directories are as follows:

+ [`content`](content) contains the manuscript source, which includes markdown files as well as inputs for citations and references.
  See [`USAGE.md`](USAGE.md) for more information.
+ [`output`](output) contains the outputs (generated files) from Manubot including the resulting manuscripts.
  You should not edit these files manually, because they will get overwritten.
+ [`webpage`](webpage) is a directory meant to be rendered as a static webpage for viewing the HTML manuscript.
+ [`build`](build) contains commands and tools for building the manuscript.
+ [`ci`](ci) contains files necessary for deployment via continuous integration.


## License

<!--
usage note: edit this section to change the license of your manuscript or source code changes to this repository.
We encourage users to openly license their manuscripts, which is the default as specified below.
-->

[![License: CC BY 4.0](https://img.shields.io/badge/License%20All-CC%20BY%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by/4.0/)
[![License: CC0 1.0](https://img.shields.io/badge/License%20Parts-CC0%201.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

Except when noted otherwise, the entirety of this repository is licensed under a CC BY 4.0 License ([`LICENSE.md`](LICENSE.md)), which allows reuse with attribution.
Please attribute by linking to https://github.com/lubianat/ideas_rootstock.

Please open [an issue](https://github.com/lubianat/ideas_rootstock/issues) for any question related to licensing.
