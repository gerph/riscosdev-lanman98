
StubsG and related libraries release 0.04
=========================================

This release contains an update for the Acorn C/C++ package, providing
generic support for all versions of SharedCLibrary. In addition, 26 bit and
32 bit versions of other libraries are also supplied.

This release may be used as a supplement for the updated Acorn C/C++ package
provided by Castle Technology Ltd.


Who should use these libraries
------------------------------

These libraries are intended to remove the requirement for additional
distribution of the most recent versions of the SharedCLibrary. Developers
indending to distribute their applications to 26bit and 32bit platforms
and who do not wish to burden the user with the installation of further
components are strongly encouraged to use the StubsG libraries.

Developers wishing to distribute their software to users with machines using
Internet 4 are strongly encouraged to use the internet libraries in their
'COMPAT_INET4' variants. Refer to the TCPIPLibs documentation for more
details.


Supplied files
--------------

Documentation for the libriaries provided with this release can be found
within the directory 'Docs'. In particular, the document 'StubsG/txt'
describes the purpose and use of the 'generic' C library stubs in detail
and should be referred to first.

Updated libraries have been supplied for :

   Toolbox
   Internet development (TCP/IP Library)
   RISC_OSLib
   FlexLib
   Shared C library (stubs)

The !Allocate application has been supplied, linked with StubsG, for
developers use.

A 32 bit-capable CMunge has been supplied in binary only form to reduce the
size of this distribution. Full sources can be obtained from the authors.


Distribution and use
--------------------

This distribution is provided free of charge by RISCOS Ltd. It may be
supplied without charge by third parties without limitation, providing the
files contained within are not modified. Code, or others works, derived from
this distribution may be distributed freely and without limitation.

This applies to all parts of the StubsG distribution with the exception of
the CMunge binary release, and the TCP/IP libraries which are covered by
their own distribution licenses. Consult the relevant sections for more
details.


Release history
---------------

pre-0.01 :
    Released to limited testers as a linkable object and linked with a
    number of well known tools and aplications.
0.01 (12 Apr 2003) :
    Released to wide scale (private) testers for testing with applications
    developed by those authors, including distribution to Castle.
0.02 (04 May 2003) :
    Updated wimplib.h wimp_set_slot_size prototype to use distinct
    argument identifiers; previously this had repeated identifiers which 
    caused problems with recent versions of the Norcroft compiler.
    Fix for C:o.StubsG when used with new C library on processors without
    independent data and code caches.
    !Allocate rebuilt with new StubsG.
    CMunge imported from non-experimental CMunge builds, rebuilt with new
    StubsG.
0.03 (03 Jun 2003) :
    Minor updates to Internet documentation to remove the use of entity
    images.
    Updated !Allocate with corrections reported by Select users.
    Updated CMunge to latest version which claims compatibility with
    CMHG 5.31.
    Added section 'Who should use these libraries'.
    Added 'License' section to the TCPIPLibs documentation.
0.03 (21 Jun 2003) :
    Correction to APCS variant to use. A mistake in annotation of the 
    APCS type specified /fpr erroneously. The type should be /nofpr.
