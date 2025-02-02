## General

Version 1.3.1 is a bug fix release with the following fixes:

* Use full set of library paths (`.libPaths()`)
* Update `loadNamespace()`/`getNamespaceExports()` 
* Fix 1.3.0 regression preventing multiple imports
* Improved handling of errors in importing modules
* Add `-package` alias is to docs

More info in `NEWS.md`


## Test environments

* local Mac OS X (R 4.3.1)
* r-hub 
  * (Windows Server 2022, R-devel, 64 bit)
  * (Ubuntu Linux 20.04.1 LTS, R-release, GCC)
  * (Fedora Linux, R-devel, clang, gfortran)
* win-builder (devel R R-4.1.0 and release R-4.0.2)
* GitHub CE (macos, linux and windows)


## R CMD check results

There were no ERRORs or WARNINGs.

On winbuilder, there were no NOTEs:

On r-hub.io, some platforms raies one or the other of the following notes:

+---
❯ checking for non-standard things in the check directory ... NOTE
  Found the following files/directories:
    ''NULL''

❯ checking for detritus in the temp directory ... NOTE
  Found the following files/directories:
    'lastMiKTeXException'
+---

These notes are not reproducible locally or on all platforms, and seem not to affect the output. The check reports no errors related to the PDF version of the manual:

#> * checking PDF version of manual ... [12s] OK


## revdepcheck results

We checked 12 reverse dependencies (11 from CRAN + 1 from Bioconductor), comparing R CMD check results across CRAN and dev versions of this package.

 * We saw 0 new problems
 * We failed to check 0 packages


## Other Notes (unchanged since last release):

The package's functionality may alter the search path, but this is intended and should be clear for the user, as the main functionality is an alternative to using `library`. For example the call:

`import::from(parallel, makeCluster, parLapply)`

will make an "imports" entry in the search path and place the imported there.

