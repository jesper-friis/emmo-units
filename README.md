Temporary repository for development and testing of datatypes and units
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

`emmo-units` is based on the upstream v1.0.0 development branch of EMMO.


Content
-------

| file                               | description |
| ---------------------------------- | ----------- |
| emmo-units.owl                     | Toplevel unit ontology that imports the rest |
| emmo/                              | Git submodule with upstream EMMO |
| base/emmo-annotations.owl          | Additional annotations introduced in emmo-units |
| domain/emmo-datatypes.owl          | Basic data types  |
| domain/emmo-units.owl              | Unit basic (to be included in EMMO core) |
| domain/emmo-si-units.owl           | Realisation of SI units |
| domain/emmo-physical-constants.owl | Realisation physical constants |


Details/comments
----------------
### base/emmo-extra-annotations.owl
Adds two object annotations; iupacDoi and qudtSameAs under
rdfs:seeAlso. They are used to provide a doi to a human readable
definitions in IUPAC and the corresponding concept in QUDT (with
information about e.g. unit conversions), respectively. Maybe iupacDoi
should be placed under rdfs:isDefinedBy instead. They can probably
also be named better. They are currently only used in
emmo-si-units.owl and emmo-physical-constants.owl, but could be used
more widely in EMMO.

### domains/emmo-datatypes.owl
This is an early draft for formalising data types and
dimensionality. A very interesting extension is to add data
representations (in a separate owl file) so that we have a common way
to express how a quantity is represented in an applications, like
whether it is a single number, a field, probability distribution,
etc...

### domains/emmo-units.owl
Defines the basic categorisation for physical quantities and units,
but does not define any unit or quantity itself. It also defines
relations for defining the physical dimensionality of derived physical
quantities in terms of base quantities.

### domains/emmo-si-units.owl
Adds a set of common SI units and corresponding physical
quantities. It is essentially based on the first table on
https://en.wikipedia.org/wiki/SI_derived_unit. Common derived units
without an own name, like square metre, Newton second, etc are still
missing. Likewise a limited set of common Physical constants are not
yet included.

It adds also a `DimensionalQuantity` branch with two subbranches,
VectorQuantity (rank 1) and MultiDimensionalQuantity (rank 2 or larger).

### domains/emmo-physical-constants.owl
Adds physical constants.  The qudtSameAs annotation is used to refer to
the CODATA 2018 value (effectuated May 20, 2019).


Questions
---------

* Should DimensionalQuantitity be moved to its own owl file?

* Referring concepts in EMMO to corresponding concepts in other widely
  accepted resources seems to be a good idea.  We have here introduced
  dedicated annotation properties for referring to IUPAC DOIs and QUDT
  URIs.
  Sub-questions:
    - Are the names iupacDoi and qudtSameAs well chosen?
    - Is it a problem that the URLs to the CODATA definitions of
      physical constants in QUDT are dead links?  For example is
      Avogagro constant referred to as
      https://physics.nist.gov/cuu/CODATA-Value_AvogadroConstant
      (dead) in http://data.qudt.org/qudt/owl/1.0.0/nist-constants.owl.
