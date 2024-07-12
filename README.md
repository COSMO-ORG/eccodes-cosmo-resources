## ecCodes samples and definition files from COSMO Consortium

### Background

To simplify the usage of the GRIB 2 format within the COSMO Consortium, a **[COSMO GRIB 2 Policy](http://www.cosmo-model.org/content/model/documentation/grib/grib_policy.htm)** has been defined. One element of this policy is to define a unified ecCodes system for the COSMO community, which is compatible with all COSMO software. This unified system is split into two parts, the vendor distribution of the ecCodes, available from **[ECMWF](https://confluence.ecmwf.int//display/ECC/Releases)** and the modified samples and definitions used by the COSMO consortium, available in the current repository.

### Documentation

Besides this document, more technical documentation is available in **[./documentation/README](https://github.com/COSMO-ORG/eccodes-cosmo-resources/blob/master/documentation/README)**. 

### Usage

The data in this repository must be used in conjunction with the correct version of the vendor distribution of the ecCodes, as specified by the **[RELEASE](https://github.com/COSMO-ORG/eccodes-cosmo-resources/blob/master/RELEASE)** file (see next section).

The value of GRIB_DEFINITION_PATH in the host program must be set to "./eccodes-cosmo-resources/definitions:./eccodes-vendor/definitions" (or similarly). All required GRIB sample files are available in the directory "./eccodes-cosmo-resources/samples".

Compatibility of the release number with the host program should be checked, if possible at run time. 

### Releases

The release number takes the form vX.Y.Z.R, where vX.Y.Z is the version number of the associated vendor distribution of the eccodes library, and R an integer which is incremented each time some definition or sample is changed, and which is reset to 1 each time a new version of the vendor library is introduced. A release with a trailing 'd' signals development status; the release information identifies the target release. A release with a trailing 'm' indicates that it contains additional mars definitions for the MeteoSwiss operational data. 

All production releases are tagged, the tag value being the same as the version number.

### Testing procedure

Any changes to this repository, including the use of a different version of eccodes-vendor, must be validated with the COSMO technical test suite. In particular, the programs INT2LM, COSMO, and **[fieldextra](https://github.com/COSMO-ORG/fieldextra)** must pass their respective regression suite, for all originating centers in {78, 215, 250}.

### GitHub repository

The master repository is **[COSMO-ORG/eccodes-cosmo-resources](https://github.com/COSMO-ORG/eccodes-cosmo-resources.git)**.

### Development policy

The master repository holds two main branches with an infinite lifetime.  The **master** branch only contains data in a _production-ready_ state which has been fully tested; all commits on the master branch are tagged. The **develop** branch is used to collect new features for the next release.


