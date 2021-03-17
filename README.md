# Fixing BRegDCAT validation errors

## Introduction

This is a brief tutorial focused on how to fix validation errors reported by the [BRegDCAT Validator Web UI](https://www.itb.ec.europa.eu/shacl/bregdcat-ap/upload) in BRegDCAT RDF documents.

We will be using a RDF document serialized in RDF/XML (`original_with_errors.xml`) that represents a register of schools of secondary education in the region of Chalkidiki (Greece).

The reader should have a basic grasp of the concepts of linked data. The following list is an attempt at defining the technologies mentioned in this article in an easily understandable fashion. There are, however, lots of great resources in the Internet to learn about RDF. I personally find [A brief introduction to linked data](https://ontola.io/what-is-linked-data/) (by Joep Meindertsma) to be a really good entry point to the world of linked data.

- **RDF**: RDF is a data model to represent knowledge that may seem intuitive to us humans in a fashion that is understandable to machines (e.g. a _Person_ has a _name_). RDF is usually represented as a set of _subject - predicate - object_ triples that form a graph. It should be noted that RDF is an **abstract concept** that may be **serialized** (i.e. written to a file) in many different _RDF serialization formats_.
- **RDF/XML**: One of the existing _RDF serialization formats_, that is, a specification that defines how to write RDF data to a file using XML.
- **Turtle**: Another _RDF serialization format_ that is usually less verbose than XML and easier to read for humans.
- **SHACL**: RDF enables us, for instance, to define that a _Person_ has a _name_, but does not provide means to _constrain_ RDF graphs (e.g. a _Person_ must have exactly one _name_). SHACL is an specification that was created to fill this gap. SHACL files are also written using a _RDF serialization format_. For example, [these two RDF files in Turtle format](https://github.com/ISAITB/validator-resources-bregdcat-ap/tree/master/resources/v2.00) are the SHACL constraints used by the BRegDCAT validator.
