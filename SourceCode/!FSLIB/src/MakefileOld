# Project:   FSLib

#MEMCHECK_CC = MemCheck.CC

# Toolflags:
#CCflagsMod = -c -depend !Depend -IFSLIB:,BaseLIB:,C: -throwback -zM -memaccess -L22-S22
CCflagsMod = -c -depend !Depend -IFSLIB:,BaseLIB:,C: -throwback -zM -ff  -apcs 3/26bit/fpe3 -memaccess -L22-S22
CC32flagsMod = -c -depend !Depend -IFSLIB:,BaseLIB:,C: -throwback -zM -ff  -apcs 3/32bit/fpe3 -memaccess -L22-S22
LibFileflags = -c -o $@
ObjAsmflags = -throwback -NoCache -depend !Depend -PreDefine "ATPCS32 SETL {FALSE}" -apcs 3/26bit
ObjAsm32flags = -throwback -NoCache -depend !Depend -PreDefine "ATPCS32 SETL {TRUE}" -apcs 3/32bit


LIB =				\
	@.o.fspatch 		\
	@.o.fspsup_a		\
	@.o.fspsup_b		\
	@.o.fspsup_c		\
	@.o.fspsup_d		\
	@.o.fspsup_e 		\
	@.o.veneer26

LIBC =				\
	@.o.fspatch		\
	@.o.fspsup_a		\
	@.o.fspsup_b		\
	@.o.fspsup_c		\
	@.o.fspsup_dC		\
	@.o.fspsup_e 		\
	@.o.veneer26

LIBM =				\
	@.om.fspatch 		\
	@.om.fspsup_a		\
	@.om.fspsup_b		\
	@.om.fspsup_c		\
	@.om.fspsup_d		\
	@.om.fspsup_e		\
	@.om.veneer26

LIBCM =				\
 	@.om.fspatch		\
	@.om.fspsup_a		\
	@.om.fspsup_b		\
	@.om.fspsup_c		\
	@.om.fspsup_dC		\
	@.om.fspsup_e		\
	@.om.veneer26

LIBDem =			\
	@.o.fspatch_d		\
	@.o.fspsup_a 		\
	@.o.fspsup_b		\
	@.o.fspsup_c		\
	@.o.fspsup_d		\
	@.o.fspsup_e		\
	@.o.veneer26

LIBCDem =			\
	@.o.fspatch_d		\
	@.o.fspsup_a 		\
	@.o.fspsup_b		\
	@.o.fspsup_c		\
	@.o.fspsup_dC		\
	@.o.fspsup_e 		\
	@.o.veneer26

LIBMDem =			\
	@.om.fspatch_d		\
	@.om.fspsup_a		\
	@.om.fspsup_b		\
	@.om.fspsup_c		\
	@.om.fspsup_d		\
	@.om.fspsup_e 		\
	@.om.veneer26

LIBCMDem =			\
	@.om.fspatch_d		\
	@.om.fspsup_a		\
	@.om.fspsup_b		\
	@.om.fspsup_c		\
	@.om.fspsup_dC		\
	@.om.fspsup_e		\
	@.om.veneer26

LIB32 =				\
 	@.o32.fspatch 		\
	@.o32.fspsup_a		\
	@.o32.fspsup_b		\
	@.o32.fspsup_c		\
	@.o32.fspsup_d		\
	@.o32.fspsup_e 		\
	@.o32.veneer32

LIBC32 =			\
	@.o32.fspatch		\
	@.o32.fspsup_a		\
	@.o32.fspsup_b		\
	@.o32.fspsup_c		\
	@.o32.fspsup_dC		\
	@.o32.fspsup_e 		\
	@.o32.veneer32

LIBM32 =			\
	@.om32.fspatch 		\
	@.om32.fspsup_a		\
	@.om32.fspsup_b		\
	@.om32.fspsup_c		\
	@.om32.fspsup_d		\
	@.om32.fspsup_e		\
	@.om32.veneer32

LIBCM32 =			\
 	@.om32.fspatch		\
	@.om32.fspsup_a		\
	@.om32.fspsup_b		\
	@.om32.fspsup_c		\
	@.om32.fspsup_dC	\
	@.om32.fspsup_e		\
	@.om32.veneer32

LIBDem32 =			\
	@.o32.fspatch_d 	\
	@.o32.fspsup_a  	\
	@.o32.fspsup_b		\
	@.o32.fspsup_c		\
	@.o32.fspsup_d		\
	@.o32.fspsup_e		\
	@.o32.veneer32

LIBCDem32 =			\
	@.o32.fspatch_d		\
	@.o32.fspsup_a 		\
	@.o32.fspsup_b		\
	@.o32.fspsup_c		\
	@.o32.fspsup_dC		\
	@.o32.fspsup_e 		\
	@.o32.veneer32

LIBMDem32 =			\
	@.om32.fspatch_d	\
	@.om32.fspsup_a		\
	@.om32.fspsup_b		\
	@.om32.fspsup_c		\
	@.om32.fspsup_d		\
	@.om32.fspsup_e 	\
	@.om32.veneer32

LIBCMDem32 =			\
	@.om32.fspatch_d	\
	@.om32.fspsup_a		\
	@.om32.fspsup_b		\
	@.om32.fspsup_c		\
	@.om32.fspsup_dC	\
	@.om32.fspsup_e		\
	@.om32.veneer32

# Standard Rules
.SUFFIXES:    .om .o .o32 .om32 .c .s
.c.o:;		cc $(ccflagsMod) -o $@ $<
.c.o32:;	cc $(cc32flagsMod) -o $@ $<
.c.om:;		$(MemCheck_CC) cc -g $(ccflagsMod) -o $@ $<
.c.om32:;	$(MemCheck_CC) cc -g $(cc32flagsMod) -o $@ $<
.s.o:;		objasm $(objasmflags) -to $@ -from $<
.s.o32:;	objasm $(objasm32flags) -to $@ -from $<



# Final targets:
All:	FSLIB:o.FSLIBZ		\
	FSLIB:o.FSLIBCZ		\
	FSLIB:o.FSLIBZM		\
	FSLIB:o.FSLIBCZM	\
	FSLIB:o.FSLIBZDem	\
	FSLIB:o.FSLIBCZDem	\
	FSLIB:o.FSLIBZMDem	\
	FSLIB:o.FSLIBCZMDem 	\
	FSLIB:o.FSLIBZ32	\
	FSLIB:o.FSLIBCZ32	\
	FSLIB:o.FSLIBZM32	\
	FSLIB:o.FSLIBCZM32	\
	FSLIB:o.FSLIBZDem32	\
	FSLIB:o.FSLIBCZDem32	\
	FSLIB:o.FSLIBZMDem32	\
	FSLIB:o.FSLIBCZMDem32 

CleanDist:
	every2 "@.o.* @.om.* @.o32.* @.om32.* FSLIB:o.*" delete %0

Clean:
	every2 "@.o.* @.om.* @.o32.* @.om32.*" delete %0


# User-editable dependencies:

FSLIB:o.FSLIBZ:   $(LIB)
        LibFile $(LibFileFlags) $(LIB)

FSLIB:o.FSLIBCZ:   $(LIBC)
        LibFile $(LibFileFlags) $(LIBC)

FSLIB:o.FSLIBZM:   $(LIBM)
        LibFile $(LibFileFlags) $(LIBM)

FSLIB:o.FSLIBCZM:   $(LIBCM)
        LibFile $(LibFileFlags) $(LIBCM)

FSLIB:o.FSLIBZDem:   $(LIBDem)
        LibFile $(LibFileFlags) $(LIBDem)

FSLIB:o.FSLIBCZDem:   $(LIBCDem)
        LibFile $(LibFileFlags) $(LIBCDem)

FSLIB:o.FSLIBZMDem:   $(LIBMDem)
        LibFile $(LibFileFlags) $(LIBMDem)

FSLIB:o.FSLIBCZMDem:   $(LIBCMDem)
        LibFile $(LibFileFlags) $(LIBCMDem)

FSLIB:o.FSLIBZ32:   $(LIB32)
        LibFile $(LibFileFlags) $(LIB32)

FSLIB:o.FSLIBCZ32:   $(LIBC32)
        LibFile $(LibFileFlags) $(LIBC32)

FSLIB:o.FSLIBZM32:   $(LIBM32)
        LibFile $(LibFileFlags) $(LIBM32)

FSLIB:o.FSLIBCZM32:   $(LIBCM32)
        LibFile $(LibFileFlags) $(LIBCM32)

FSLIB:o.FSLIBZDem32:   $(LIBDem32)
        LibFile $(LibFileFlags) $(LIBDem32)

FSLIB:o.FSLIBCZDem32:   $(LIBCDem32)
        LibFile $(LibFileFlags) $(LIBCDem32)

FSLIB:o.FSLIBZMDem32:   $(LIBMDem32)
        LibFile $(LibFileFlags) $(LIBMDem32)

FSLIB:o.FSLIBCZMDem32:   $(LIBCMDem32)
        LibFile $(LibFileFlags) $(LIBCMDem32)

@.o.fspatch_d:	@.c.fspatch
	cc $(ccflagsMod) -DDEMO -o @.o.fspatch_d @.c.fspatch

@.o32.fspatch_d:	@.c.fspatch
	cc $(cc32flagsMod) -DDEMO -o @.o32.fspatch_d @.c.fspatch

@.om.fspatch_d:	@.c.fspatch
	$(MemCheck_CC) cc -g $(ccflagsMod) -DDEMO -o @.om.fspatch_d @.c.fspatch

@.om32.fspatch_d:	@.c.fspatch
	$(MemCheck_CC) cc -g $(cc32flagsMod) -DDEMO -o @.om32.fspatch_d @.c.fspatch

# Static dependencies:


# Dynamic dependencies:
o.fspatch:	c.fspatch
o.fspatch:	MemCheck:h.MemCheck
o.fspatch:	BaseLIB:h.strext
o.fspatch:	C:h.swis
o.fspatch:	C:h.kernel
o.fspatch:	C:h.kernel
o.fspatch:	h.rmbase
o.fspatch:	h.veneer
o.fspatch:	C:h.kernel
o.fspatch:	BaseLIB:h.error
o.fspatch:	C:h.kernel
o.fspatch:	BaseLIB:h.memory
o.fspatch:	BaseLIB:h.errorxxx
o.fspatch:	BaseLIB:h.nsetjmp
o.fspatch:	FSLIB:h.fsys_err
o.fspatch:	FSLIB:h.fsys
o.fspatch:	FSLIB:h.path
o.fspatch:	h.fspsup_a
o.fspatch:	FSLIB:h.fsys
o.fspatch:	h.fspsup_b
o.fspatch:	FSLIB:h.fsys
o.fspatch:	h.fspsup_e
o.fspatch:	FSLIB:h.path
o.fspatch:	FSLIB:h.fsys
o.fspatch:	h.fspsup_c
o.fspatch:	FSLIB:h.fsys
o.fspatch:	h.fspsup_d
o.fspatch:	FSLIB:h.fsys
o.fspatch:	h.fspsup_e
o.fspatch:	FSLIB:h.fspatch
o.fspatch:	FSLIB:h.fsys
om.fspatch:	c.fspatch
om.fspatch:	MemCheck:h.MemCheck
om.fspatch:	BaseLIB:h.strext
om.fspatch:	C:h.swis
om.fspatch:	C:h.kernel
om.fspatch:	C:h.kernel
om.fspatch:	h.rmbase
om.fspatch:	h.veneer
om.fspatch:	C:h.kernel
om.fspatch:	BaseLIB:h.error
om.fspatch:	C:h.kernel
om.fspatch:	BaseLIB:h.memory
om.fspatch:	BaseLIB:h.errorxxx
om.fspatch:	BaseLIB:h.nsetjmp
om.fspatch:	FSLIB:h.fsys_err
om.fspatch:	FSLIB:h.fsys
om.fspatch:	FSLIB:h.path
om.fspatch:	h.fspsup_a
om.fspatch:	FSLIB:h.fsys
om.fspatch:	h.fspsup_b
om.fspatch:	FSLIB:h.fsys
om.fspatch:	h.fspsup_e
om.fspatch:	FSLIB:h.path
om.fspatch:	FSLIB:h.fsys
om.fspatch:	h.fspsup_c
om.fspatch:	FSLIB:h.fsys
om.fspatch:	h.fspsup_d
om.fspatch:	FSLIB:h.fsys
om.fspatch:	h.fspsup_e
om.fspatch:	FSLIB:h.fspatch
om.fspatch:	FSLIB:h.fsys
o.fspsup_d:	c.fspsup_d
o.fspsup_d:	BaseLIB:h.strext
o.fspsup_d:	BaseLIB:h.memory
o.fspsup_d:	BaseLIB:h.error
o.fspsup_d:	C:h.kernel
o.fspsup_d:	BaseLIB:h.memory
o.fspsup_d:	BaseLIB:h.errorxxx
o.fspsup_d:	BaseLIB:h.nsetjmp
o.fspsup_d:	FSLIB:h.fsys_err
o.fspsup_d:	FSLIB:h.fsys
o.fspsup_d:	FSLIB:h.path
o.fspsup_d:	h.fspsup_e
o.fspsup_d:	FSLIB:h.path
o.fspsup_d:	FSLIB:h.fsys
o.fspsup_d:	h.fspsup_d
o.fspsup_d:	FSLIB:h.fsys
o.fspsup_d:	h.fspsup_e
o.fspatch_d:	c.fspatch
o.fspatch_d:	MemCheck:h.MemCheck
o.fspatch_d:	BaseLIB:h.strext
o.fspatch_d:	C:h.swis
o.fspatch_d:	C:h.kernel
o.fspatch_d:	C:h.kernel
o.fspatch_d:	h.rmbase
o.fspatch_d:	h.veneer
o.fspatch_d:	C:h.kernel
o.fspatch_d:	BaseLIB:h.error
o.fspatch_d:	C:h.kernel
o.fspatch_d:	BaseLIB:h.memory
o.fspatch_d:	BaseLIB:h.errorxxx
o.fspatch_d:	BaseLIB:h.nsetjmp
o.fspatch_d:	FSLIB:h.fsys_err
o.fspatch_d:	FSLIB:h.fsys
o.fspatch_d:	FSLIB:h.path
o.fspatch_d:	h.fspsup_a
o.fspatch_d:	FSLIB:h.fsys
o.fspatch_d:	h.fspsup_b
o.fspatch_d:	FSLIB:h.fsys
o.fspatch_d:	h.fspsup_e
o.fspatch_d:	FSLIB:h.path
o.fspatch_d:	FSLIB:h.fsys
o.fspatch_d:	h.fspsup_c
o.fspatch_d:	FSLIB:h.fsys
o.fspatch_d:	h.fspsup_d
o.fspatch_d:	FSLIB:h.fsys
o.fspatch_d:	h.fspsup_e
o.fspatch_d:	FSLIB:h.fspatch
o.fspatch_d:	FSLIB:h.fsys
o.fspsup_a:	c.fspsup_a
o.fspsup_a:	BaseLIB:h.strext
o.fspsup_a:	BaseLIB:h.memory
o.fspsup_a:	FSLIB:h.path
o.fspsup_a:	h.fspsup_a
o.fspsup_a:	FSLIB:h.fsys
o.fspsup_a:	FSLIB:h.path
o.fspsup_b:	c.fspsup_b
o.fspsup_b:	BaseLIB:h.strext
o.fspsup_b:	BaseLIB:h.memory
o.fspsup_b:	BaseLIB:h.error
o.fspsup_b:	C:h.kernel
o.fspsup_b:	BaseLIB:h.memory
o.fspsup_b:	BaseLIB:h.errorxxx
o.fspsup_b:	BaseLIB:h.nsetjmp
o.fspsup_b:	FSLIB:h.fsys
o.fspsup_b:	FSLIB:h.path
o.fspsup_b:	FSLIB:h.fsys_err
o.fspsup_b:	h.fspsup_b
o.fspsup_b:	FSLIB:h.fsys
o.fspsup_b:	h.fspsup_e
o.fspsup_b:	FSLIB:h.path
o.fspsup_b:	FSLIB:h.fsys
o.fspsup_c:	c.fspsup_c
o.fspsup_c:	BaseLIB:h.error
o.fspsup_c:	C:h.kernel
o.fspsup_c:	BaseLIB:h.memory
o.fspsup_c:	BaseLIB:h.errorxxx
o.fspsup_c:	BaseLIB:h.nsetjmp
o.fspsup_c:	FSLIB:h.fsys_err
o.fspsup_c:	FSLIB:h.fsys
o.fspsup_c:	FSLIB:h.path
o.fspsup_c:	h.fspsup_c
o.fspsup_c:	FSLIB:h.fsys
o.fspsup_dC:	c.fspsup_dC
o.fspsup_dC:	BaseLIB:h.strext
o.fspsup_dC:	BaseLIB:h.memory
o.fspsup_dC:	BaseLIB:h.error
o.fspsup_dC:	C:h.kernel
o.fspsup_dC:	BaseLIB:h.memory
o.fspsup_dC:	BaseLIB:h.errorxxx
o.fspsup_dC:	BaseLIB:h.nsetjmp
o.fspsup_dC:	FSLIB:h.fsys_err
o.fspsup_dC:	FSLIB:h.fsys
o.fspsup_dC:	FSLIB:h.path
o.fspsup_dC:	h.fspsup_e
o.fspsup_dC:	FSLIB:h.path
o.fspsup_dC:	FSLIB:h.fsys
o.fspsup_dC:	h.fspsup_d
o.fspsup_dC:	FSLIB:h.fsys
o.fspsup_dC:	h.fspsup_e
o.fspsup_e:	c.fspsup_e
o.fspsup_e:	BaseLIB:h.strext
o.fspsup_e:	BaseLIB:h.memory
o.fspsup_e:	BaseLIB:h.error
o.fspsup_e:	C:h.kernel
o.fspsup_e:	BaseLIB:h.memory
o.fspsup_e:	BaseLIB:h.errorxxx
o.fspsup_e:	BaseLIB:h.nsetjmp
o.fspsup_e:	FSLIB:h.fsys_err
o.fspsup_e:	FSLIB:h.fsys
o.fspsup_e:	FSLIB:h.path
o.fspsup_e:	h.fspsup_e
o.fspsup_e:	FSLIB:h.path
o.fspsup_e:	FSLIB:h.fsys
o.veneer26:	c.veneer26
o.veneer26:	BaseLIB:h.error
o.veneer26:	C:h.kernel
o.veneer26:	BaseLIB:h.memory
o.veneer26:	BaseLIB:h.errorxxx
o.veneer26:	BaseLIB:h.nsetjmp
o.veneer26:	h.veneer
o.veneer26:	C:h.kernel
om.fspsup_d:	c.fspsup_d
om.fspsup_d:	BaseLIB:h.strext
om.fspsup_d:	BaseLIB:h.memory
om.fspsup_d:	BaseLIB:h.error
om.fspsup_d:	C:h.kernel
om.fspsup_d:	BaseLIB:h.memory
om.fspsup_d:	BaseLIB:h.errorxxx
om.fspsup_d:	BaseLIB:h.nsetjmp
om.fspsup_d:	FSLIB:h.fsys_err
om.fspsup_d:	FSLIB:h.fsys
om.fspsup_d:	FSLIB:h.path
om.fspsup_d:	h.fspsup_e
om.fspsup_d:	FSLIB:h.path
om.fspsup_d:	FSLIB:h.fsys
om.fspsup_d:	h.fspsup_d
om.fspsup_d:	FSLIB:h.fsys
om.fspsup_d:	h.fspsup_e
om.fspatch_d:	c.fspatch
om.fspatch_d:	MemCheck:h.MemCheck
om.fspatch_d:	BaseLIB:h.strext
om.fspatch_d:	C:h.swis
om.fspatch_d:	C:h.kernel
om.fspatch_d:	C:h.kernel
om.fspatch_d:	h.rmbase
om.fspatch_d:	h.veneer
om.fspatch_d:	C:h.kernel
om.fspatch_d:	BaseLIB:h.error
om.fspatch_d:	C:h.kernel
om.fspatch_d:	BaseLIB:h.memory
om.fspatch_d:	BaseLIB:h.errorxxx
om.fspatch_d:	BaseLIB:h.nsetjmp
om.fspatch_d:	FSLIB:h.fsys_err
om.fspatch_d:	FSLIB:h.fsys
om.fspatch_d:	FSLIB:h.path
om.fspatch_d:	h.fspsup_a
om.fspatch_d:	FSLIB:h.fsys
om.fspatch_d:	h.fspsup_b
om.fspatch_d:	FSLIB:h.fsys
om.fspatch_d:	h.fspsup_e
om.fspatch_d:	FSLIB:h.path
om.fspatch_d:	FSLIB:h.fsys
om.fspatch_d:	h.fspsup_c
om.fspatch_d:	FSLIB:h.fsys
om.fspatch_d:	h.fspsup_d
om.fspatch_d:	FSLIB:h.fsys
om.fspatch_d:	h.fspsup_e
om.fspatch_d:	FSLIB:h.fspatch
om.fspatch_d:	FSLIB:h.fsys
om.fspsup_a:	c.fspsup_a
om.fspsup_a:	BaseLIB:h.strext
om.fspsup_a:	BaseLIB:h.memory
om.fspsup_a:	FSLIB:h.path
om.fspsup_a:	h.fspsup_a
om.fspsup_a:	FSLIB:h.fsys
om.fspsup_a:	FSLIB:h.path
om.fspsup_b:	c.fspsup_b
om.fspsup_b:	BaseLIB:h.strext
om.fspsup_b:	BaseLIB:h.memory
om.fspsup_b:	BaseLIB:h.error
om.fspsup_b:	C:h.kernel
om.fspsup_b:	BaseLIB:h.memory
om.fspsup_b:	BaseLIB:h.errorxxx
om.fspsup_b:	BaseLIB:h.nsetjmp
om.fspsup_b:	FSLIB:h.fsys
om.fspsup_b:	FSLIB:h.path
om.fspsup_b:	FSLIB:h.fsys_err
om.fspsup_b:	h.fspsup_b
om.fspsup_b:	FSLIB:h.fsys
om.fspsup_b:	h.fspsup_e
om.fspsup_b:	FSLIB:h.path
om.fspsup_b:	FSLIB:h.fsys
om.fspsup_c:	c.fspsup_c
om.fspsup_c:	BaseLIB:h.error
om.fspsup_c:	C:h.kernel
om.fspsup_c:	BaseLIB:h.memory
om.fspsup_c:	BaseLIB:h.errorxxx
om.fspsup_c:	BaseLIB:h.nsetjmp
om.fspsup_c:	FSLIB:h.fsys_err
om.fspsup_c:	FSLIB:h.fsys
om.fspsup_c:	FSLIB:h.path
om.fspsup_c:	h.fspsup_c
om.fspsup_c:	FSLIB:h.fsys
om.fspsup_dC:	c.fspsup_dC
om.fspsup_dC:	BaseLIB:h.strext
om.fspsup_dC:	BaseLIB:h.memory
om.fspsup_dC:	BaseLIB:h.error
om.fspsup_dC:	C:h.kernel
om.fspsup_dC:	BaseLIB:h.memory
om.fspsup_dC:	BaseLIB:h.errorxxx
om.fspsup_dC:	BaseLIB:h.nsetjmp
om.fspsup_dC:	FSLIB:h.fsys_err
om.fspsup_dC:	FSLIB:h.fsys
om.fspsup_dC:	FSLIB:h.path
om.fspsup_dC:	h.fspsup_e
om.fspsup_dC:	FSLIB:h.path
om.fspsup_dC:	FSLIB:h.fsys
om.fspsup_dC:	h.fspsup_d
om.fspsup_dC:	FSLIB:h.fsys
om.fspsup_dC:	h.fspsup_e
om.fspsup_e:	c.fspsup_e
om.fspsup_e:	BaseLIB:h.strext
om.fspsup_e:	BaseLIB:h.memory
om.fspsup_e:	BaseLIB:h.error
om.fspsup_e:	C:h.kernel
om.fspsup_e:	BaseLIB:h.memory
om.fspsup_e:	BaseLIB:h.errorxxx
om.fspsup_e:	BaseLIB:h.nsetjmp
om.fspsup_e:	FSLIB:h.fsys_err
om.fspsup_e:	FSLIB:h.fsys
om.fspsup_e:	FSLIB:h.path
om.fspsup_e:	h.fspsup_e
om.fspsup_e:	FSLIB:h.path
om.fspsup_e:	FSLIB:h.fsys
om.veneer26:	c.veneer26
om.veneer26:	BaseLIB:h.error
om.veneer26:	C:h.kernel
om.veneer26:	BaseLIB:h.memory
om.veneer26:	BaseLIB:h.errorxxx
om.veneer26:	BaseLIB:h.nsetjmp
om.veneer26:	h.veneer
om.veneer26:	C:h.kernel
o32.fspatch:	c.fspatch
o32.fspatch:	MemCheck:h.MemCheck
o32.fspatch:	BaseLIB:h.strext
o32.fspatch:	C:h.swis
o32.fspatch:	C:h.kernel
o32.fspatch:	C:h.kernel
o32.fspatch:	h.rmbase
o32.fspatch:	h.veneer
o32.fspatch:	C:h.kernel
o32.fspatch:	BaseLIB:h.error
o32.fspatch:	C:h.kernel
o32.fspatch:	BaseLIB:h.memory
o32.fspatch:	BaseLIB:h.errorxxx
o32.fspatch:	BaseLIB:h.nsetjmp
o32.fspatch:	FSLIB:h.fsys_err
o32.fspatch:	FSLIB:h.fsys
o32.fspatch:	FSLIB:h.path
o32.fspatch:	h.fspsup_a
o32.fspatch:	FSLIB:h.fsys
o32.fspatch:	h.fspsup_b
o32.fspatch:	FSLIB:h.fsys
o32.fspatch:	h.fspsup_e
o32.fspatch:	FSLIB:h.path
o32.fspatch:	FSLIB:h.fsys
o32.fspatch:	h.fspsup_c
o32.fspatch:	FSLIB:h.fsys
o32.fspatch:	h.fspsup_d
o32.fspatch:	FSLIB:h.fsys
o32.fspatch:	h.fspsup_e
o32.fspatch:	FSLIB:h.fspatch
o32.fspatch:	FSLIB:h.fsys
om32.fspatch:	c.fspatch
om32.fspatch:	MemCheck:h.MemCheck
om32.fspatch:	BaseLIB:h.strext
om32.fspatch:	C:h.swis
om32.fspatch:	C:h.kernel
om32.fspatch:	C:h.kernel
om32.fspatch:	h.rmbase
om32.fspatch:	h.veneer
om32.fspatch:	C:h.kernel
om32.fspatch:	BaseLIB:h.error
om32.fspatch:	C:h.kernel
om32.fspatch:	BaseLIB:h.memory
om32.fspatch:	BaseLIB:h.errorxxx
om32.fspatch:	BaseLIB:h.nsetjmp
om32.fspatch:	FSLIB:h.fsys_err
om32.fspatch:	FSLIB:h.fsys
om32.fspatch:	FSLIB:h.path
om32.fspatch:	h.fspsup_a
om32.fspatch:	FSLIB:h.fsys
om32.fspatch:	h.fspsup_b
om32.fspatch:	FSLIB:h.fsys
om32.fspatch:	h.fspsup_e
om32.fspatch:	FSLIB:h.path
om32.fspatch:	FSLIB:h.fsys
om32.fspatch:	h.fspsup_c
om32.fspatch:	FSLIB:h.fsys
om32.fspatch:	h.fspsup_d
om32.fspatch:	FSLIB:h.fsys
om32.fspatch:	h.fspsup_e
om32.fspatch:	FSLIB:h.fspatch
om32.fspatch:	FSLIB:h.fsys
o32.fspsup_d:	c.fspsup_d
o32.fspsup_d:	BaseLIB:h.strext
o32.fspsup_d:	BaseLIB:h.memory
o32.fspsup_d:	BaseLIB:h.error
o32.fspsup_d:	C:h.kernel
o32.fspsup_d:	BaseLIB:h.memory
o32.fspsup_d:	BaseLIB:h.errorxxx
o32.fspsup_d:	BaseLIB:h.nsetjmp
o32.fspsup_d:	FSLIB:h.fsys_err
o32.fspsup_d:	FSLIB:h.fsys
o32.fspsup_d:	FSLIB:h.path
o32.fspsup_d:	h.fspsup_e
o32.fspsup_d:	FSLIB:h.path
o32.fspsup_d:	FSLIB:h.fsys
o32.fspsup_d:	h.fspsup_d
o32.fspsup_d:	FSLIB:h.fsys
o32.fspsup_d:	h.fspsup_e
o32.fspatch_d:	c.fspatch
o32.fspatch_d:	MemCheck:h.MemCheck
o32.fspatch_d:	BaseLIB:h.strext
o32.fspatch_d:	C:h.swis
o32.fspatch_d:	C:h.kernel
o32.fspatch_d:	C:h.kernel
o32.fspatch_d:	h.rmbase
o32.fspatch_d:	h.veneer
o32.fspatch_d:	C:h.kernel
o32.fspatch_d:	BaseLIB:h.error
o32.fspatch_d:	C:h.kernel
o32.fspatch_d:	BaseLIB:h.memory
o32.fspatch_d:	BaseLIB:h.errorxxx
o32.fspatch_d:	BaseLIB:h.nsetjmp
o32.fspatch_d:	FSLIB:h.fsys_err
o32.fspatch_d:	FSLIB:h.fsys
o32.fspatch_d:	FSLIB:h.path
o32.fspatch_d:	h.fspsup_a
o32.fspatch_d:	FSLIB:h.fsys
o32.fspatch_d:	h.fspsup_b
o32.fspatch_d:	FSLIB:h.fsys
o32.fspatch_d:	h.fspsup_e
o32.fspatch_d:	FSLIB:h.path
o32.fspatch_d:	FSLIB:h.fsys
o32.fspatch_d:	h.fspsup_c
o32.fspatch_d:	FSLIB:h.fsys
o32.fspatch_d:	h.fspsup_d
o32.fspatch_d:	FSLIB:h.fsys
o32.fspatch_d:	h.fspsup_e
o32.fspatch_d:	FSLIB:h.fspatch
o32.fspatch_d:	FSLIB:h.fsys
o32.fspsup_a:	c.fspsup_a
o32.fspsup_a:	BaseLIB:h.strext
o32.fspsup_a:	BaseLIB:h.memory
o32.fspsup_a:	FSLIB:h.path
o32.fspsup_a:	h.fspsup_a
o32.fspsup_a:	FSLIB:h.fsys
o32.fspsup_a:	FSLIB:h.path
o32.fspsup_b:	c.fspsup_b
o32.fspsup_b:	BaseLIB:h.strext
o32.fspsup_b:	BaseLIB:h.memory
o32.fspsup_b:	BaseLIB:h.error
o32.fspsup_b:	C:h.kernel
o32.fspsup_b:	BaseLIB:h.memory
o32.fspsup_b:	BaseLIB:h.errorxxx
o32.fspsup_b:	BaseLIB:h.nsetjmp
o32.fspsup_b:	FSLIB:h.fsys
o32.fspsup_b:	FSLIB:h.path
o32.fspsup_b:	FSLIB:h.fsys_err
o32.fspsup_b:	h.fspsup_b
o32.fspsup_b:	FSLIB:h.fsys
o32.fspsup_b:	h.fspsup_e
o32.fspsup_b:	FSLIB:h.path
o32.fspsup_b:	FSLIB:h.fsys
o32.fspsup_c:	c.fspsup_c
o32.fspsup_c:	BaseLIB:h.error
o32.fspsup_c:	C:h.kernel
o32.fspsup_c:	BaseLIB:h.memory
o32.fspsup_c:	BaseLIB:h.errorxxx
o32.fspsup_c:	BaseLIB:h.nsetjmp
o32.fspsup_c:	FSLIB:h.fsys_err
o32.fspsup_c:	FSLIB:h.fsys
o32.fspsup_c:	FSLIB:h.path
o32.fspsup_c:	h.fspsup_c
o32.fspsup_c:	FSLIB:h.fsys
o32.fspsup_dC:	c.fspsup_dC
o32.fspsup_dC:	BaseLIB:h.strext
o32.fspsup_dC:	BaseLIB:h.memory
o32.fspsup_dC:	BaseLIB:h.error
o32.fspsup_dC:	C:h.kernel
o32.fspsup_dC:	BaseLIB:h.memory
o32.fspsup_dC:	BaseLIB:h.errorxxx
o32.fspsup_dC:	BaseLIB:h.nsetjmp
o32.fspsup_dC:	FSLIB:h.fsys_err
o32.fspsup_dC:	FSLIB:h.fsys
o32.fspsup_dC:	FSLIB:h.path
o32.fspsup_dC:	h.fspsup_e
o32.fspsup_dC:	FSLIB:h.path
o32.fspsup_dC:	FSLIB:h.fsys
o32.fspsup_dC:	h.fspsup_d
o32.fspsup_dC:	FSLIB:h.fsys
o32.fspsup_dC:	h.fspsup_e
o32.fspsup_e:	c.fspsup_e
o32.fspsup_e:	BaseLIB:h.strext
o32.fspsup_e:	BaseLIB:h.memory
o32.fspsup_e:	BaseLIB:h.error
o32.fspsup_e:	C:h.kernel
o32.fspsup_e:	BaseLIB:h.memory
o32.fspsup_e:	BaseLIB:h.errorxxx
o32.fspsup_e:	BaseLIB:h.nsetjmp
o32.fspsup_e:	FSLIB:h.fsys_err
o32.fspsup_e:	FSLIB:h.fsys
o32.fspsup_e:	FSLIB:h.path
o32.fspsup_e:	h.fspsup_e
o32.fspsup_e:	FSLIB:h.path
o32.fspsup_e:	FSLIB:h.fsys
o32.veneer32:	c.veneer32
o32.veneer32:	BaseLIB:h.error
o32.veneer32:	C:h.kernel
o32.veneer32:	BaseLIB:h.memory
o32.veneer32:	BaseLIB:h.errorxxx
o32.veneer32:	BaseLIB:h.nsetjmp
o32.veneer32:	h.veneer
o32.veneer32:	C:h.kernel
om32.fspsup_d:	c.fspsup_d
om32.fspsup_d:	BaseLIB:h.strext
om32.fspsup_d:	BaseLIB:h.memory
om32.fspsup_d:	BaseLIB:h.error
om32.fspsup_d:	C:h.kernel
om32.fspsup_d:	BaseLIB:h.memory
om32.fspsup_d:	BaseLIB:h.errorxxx
om32.fspsup_d:	BaseLIB:h.nsetjmp
om32.fspsup_d:	FSLIB:h.fsys_err
om32.fspsup_d:	FSLIB:h.fsys
om32.fspsup_d:	FSLIB:h.path
om32.fspsup_d:	h.fspsup_e
om32.fspsup_d:	FSLIB:h.path
om32.fspsup_d:	FSLIB:h.fsys
om32.fspsup_d:	h.fspsup_d
om32.fspsup_d:	FSLIB:h.fsys
om32.fspsup_d:	h.fspsup_e
om32.fspatch_d:	c.fspatch
om32.fspatch_d:	MemCheck:h.MemCheck
om32.fspatch_d:	BaseLIB:h.strext
om32.fspatch_d:	C:h.swis
om32.fspatch_d:	C:h.kernel
om32.fspatch_d:	C:h.kernel
om32.fspatch_d:	h.rmbase
om32.fspatch_d:	h.veneer
om32.fspatch_d:	C:h.kernel
om32.fspatch_d:	BaseLIB:h.error
om32.fspatch_d:	C:h.kernel
om32.fspatch_d:	BaseLIB:h.memory
om32.fspatch_d:	BaseLIB:h.errorxxx
om32.fspatch_d:	BaseLIB:h.nsetjmp
om32.fspatch_d:	FSLIB:h.fsys_err
om32.fspatch_d:	FSLIB:h.fsys
om32.fspatch_d:	FSLIB:h.path
om32.fspatch_d:	h.fspsup_a
om32.fspatch_d:	FSLIB:h.fsys
om32.fspatch_d:	h.fspsup_b
om32.fspatch_d:	FSLIB:h.fsys
om32.fspatch_d:	h.fspsup_e
om32.fspatch_d:	FSLIB:h.path
om32.fspatch_d:	FSLIB:h.fsys
om32.fspatch_d:	h.fspsup_c
om32.fspatch_d:	FSLIB:h.fsys
om32.fspatch_d:	h.fspsup_d
om32.fspatch_d:	FSLIB:h.fsys
om32.fspatch_d:	h.fspsup_e
om32.fspatch_d:	FSLIB:h.fspatch
om32.fspatch_d:	FSLIB:h.fsys
om32.fspsup_a:	c.fspsup_a
om32.fspsup_a:	BaseLIB:h.strext
om32.fspsup_a:	BaseLIB:h.memory
om32.fspsup_a:	FSLIB:h.path
om32.fspsup_a:	h.fspsup_a
om32.fspsup_a:	FSLIB:h.fsys
om32.fspsup_a:	FSLIB:h.path
om32.fspsup_b:	c.fspsup_b
om32.fspsup_b:	BaseLIB:h.strext
om32.fspsup_b:	BaseLIB:h.memory
om32.fspsup_b:	BaseLIB:h.error
om32.fspsup_b:	C:h.kernel
om32.fspsup_b:	BaseLIB:h.memory
om32.fspsup_b:	BaseLIB:h.errorxxx
om32.fspsup_b:	BaseLIB:h.nsetjmp
om32.fspsup_b:	FSLIB:h.fsys
om32.fspsup_b:	FSLIB:h.path
om32.fspsup_b:	FSLIB:h.fsys_err
om32.fspsup_b:	h.fspsup_b
om32.fspsup_b:	FSLIB:h.fsys
om32.fspsup_b:	h.fspsup_e
om32.fspsup_b:	FSLIB:h.path
om32.fspsup_b:	FSLIB:h.fsys
om32.fspsup_c:	c.fspsup_c
om32.fspsup_c:	BaseLIB:h.error
om32.fspsup_c:	C:h.kernel
om32.fspsup_c:	BaseLIB:h.memory
om32.fspsup_c:	BaseLIB:h.errorxxx
om32.fspsup_c:	BaseLIB:h.nsetjmp
om32.fspsup_c:	FSLIB:h.fsys_err
om32.fspsup_c:	FSLIB:h.fsys
om32.fspsup_c:	FSLIB:h.path
om32.fspsup_c:	h.fspsup_c
om32.fspsup_c:	FSLIB:h.fsys
om32.fspsup_dC:	c.fspsup_dC
om32.fspsup_dC:	BaseLIB:h.strext
om32.fspsup_dC:	BaseLIB:h.memory
om32.fspsup_dC:	BaseLIB:h.error
om32.fspsup_dC:	C:h.kernel
om32.fspsup_dC:	BaseLIB:h.memory
om32.fspsup_dC:	BaseLIB:h.errorxxx
om32.fspsup_dC:	BaseLIB:h.nsetjmp
om32.fspsup_dC:	FSLIB:h.fsys_err
om32.fspsup_dC:	FSLIB:h.fsys
om32.fspsup_dC:	FSLIB:h.path
om32.fspsup_dC:	h.fspsup_e
om32.fspsup_dC:	FSLIB:h.path
om32.fspsup_dC:	FSLIB:h.fsys
om32.fspsup_dC:	h.fspsup_d
om32.fspsup_dC:	FSLIB:h.fsys
om32.fspsup_dC:	h.fspsup_e
om32.fspsup_e:	c.fspsup_e
om32.fspsup_e:	BaseLIB:h.strext
om32.fspsup_e:	BaseLIB:h.memory
om32.fspsup_e:	BaseLIB:h.error
om32.fspsup_e:	C:h.kernel
om32.fspsup_e:	BaseLIB:h.memory
om32.fspsup_e:	BaseLIB:h.errorxxx
om32.fspsup_e:	BaseLIB:h.nsetjmp
om32.fspsup_e:	FSLIB:h.fsys_err
om32.fspsup_e:	FSLIB:h.fsys
om32.fspsup_e:	FSLIB:h.path
om32.fspsup_e:	h.fspsup_e
om32.fspsup_e:	FSLIB:h.path
om32.fspsup_e:	FSLIB:h.fsys
om32.veneer32:	c.veneer32
om32.veneer32:	BaseLIB:h.error
om32.veneer32:	C:h.kernel
om32.veneer32:	BaseLIB:h.memory
om32.veneer32:	BaseLIB:h.errorxxx
om32.veneer32:	BaseLIB:h.nsetjmp
om32.veneer32:	h.veneer
om32.veneer32:	C:h.kernel
