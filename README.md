Temporary repository for development and testing of units and datatypes
=======================================================================

**Warning**: This repository is intrinsic unstable.

We are facing two not compatible aims.  On one side, in order to
actually use EMMO, datatypes and units are essential.  On the other
side, since there has been put so much effort into EMMO, we cannot
allow to introduce new concepts that are not well thought through and
tested.

The aim of this repository is to allow testing out new ideas about
datatypes and units in domain and application ontologies.  The hope is
that this the content soon will be merged into EMMO.

`emmo-units` is based on the upstream 1.0.0 development branch of EMMO.


Content
-------

| file                       | description |
| -------------------------- | ----------- |
| emmo-units.owl             | Toplevel unit ontology that imports the rest |
| base/emmo-annotations.owl  | Additional annotations |
| domain/emmo-datatypes.owl  | Basic data types  |
| domain/emmo-units.owl      | Unit basic (to be included in EMMO core) |
| domain/emmo-si-units.owl   | Realisation of SI units |
