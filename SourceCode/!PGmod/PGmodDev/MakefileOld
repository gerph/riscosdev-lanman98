# Project:   PGmod

#CC = MemCheck.CC cc -g 
CC = cc

INCS = -I StubsG:clib -I StubsG:flexlib

# Toolflags:
CCflagsMod    = -c -depend !Depend $(INCS) -throwback -ff -apcs 3/26bit/fpe3 -memaccess -L22-S22
CC32flagsMod  = -c -depend !Depend $(INCS) -throwback -ff -apcs 3/32bit/fpe3 -memaccess -L22-S22
C++flags      = -c -depend !Depend $(INCS) -throwback -apcs 3/26bit/fpe3 -memaccess -L22-S22
C++32flags    = -c -depend !Depend $(INCS) -throwback -apcs 3/32bit/fpe3 -memaccess -L22-S22
Linkflags     = -aif -c++ -o $@ 
ObjAsmflags   = -throwback -NoCache -depend !Depend -PreDefine "ATPCS32 SETL {FALSE}" -apcs 3/26bit
ObjAsm32flags = -throwback -NoCache -depend !Depend -PreDefine "ATPCS32 SETL {TRUE}" -apcs 3/32bit
MHGflags      = -26bit -depend !Depend -throwBack 
CMHG32flags   = -32bit -depend !Depend -throwBack 
LibFileflags  = -c -o $@
Squeezeflags  = -o $@


PGMOD =	@.o.PGdev	\
	@.o.PGerr	\
	@.o.PGflex	\
	@.o.PGfs	\
	@.o.PGgr	\
	@.o.PGicn	\
	@.o.PGmnu	\
	@.o.PGmode	\
	@.o.PGprt	\
	@.o.PGptr	\
	@.o.PGscan	\
	@.o.PGscn	\
	@.o.PGspr	\
	@.o.PGsprf	\
	@.o.PGtm	\
	@.o.PGvar	\
	@.o.PGwin	\
	@.o.hg_code26 

PGMOD32 =		\
	@.o32.PGdev	\
	@.o32.PGerr	\
	@.o32.PGflex	\
	@.o32.PGfs	\
	@.o32.PGgr	\
	@.o32.PGicn	\
	@.o32.PGmnu	\
	@.o32.PGmode	\
	@.o32.PGprt	\
	@.o32.PGptr	\
	@.o32.PGscan	\
	@.o32.PGscn	\
	@.o32.PGspr	\
	@.o32.PGsprf	\
	@.o32.PGtm	\
	@.o32.PGvar	\
	@.o32.PGwin 	\
	@.o32.hg_code32 

# Standard Rules

.SUFFIXES: .o .o32 .c .c++ .s
.c.o:;		cc $(ccflagsMod) -o $@ $<
.c.o32:;	cc $(cc32flagsMod) -o $@ $<
.c++.o:;	cc $(ccflagsMod) -o $@ $<
.c++.o32:;	cc $(cc32flagsMod) -o $@ $<
.s.o:;		objasm $(objasmflags) -to $@ -from $<
.s.o32:;	objasm $(objasm32flags) -to $@ -from $<

# Final targets:

All:	@.^.o.PGmod @.^.o32.PGmod
        
@.^.o.PGmod: $(PGMOD)
        LibFile $(LibFileflags) $(PGMOD)

@.^.o32.PGmod: $(PGMOD32)
        LibFile $(LibFileflags) $(PGMOD32)

Clean:
	every2 "@.o.* @.o32.* $(Target) $(Traget32)" delete %0


# User-editable dependencies:


# Static dependencies:


# Dynamic dependencies:
o.PGdev:	c.PGdev
o.PGdev:	StubsG:clib.h.kernel
o.PGdev:	StubsG:clib.h.swis
o.PGdev:	h.PGwin
o.PGdev:	StubsG:clib.h.kernel
o.PGdev:	h.PGspr
o.PGdev:	h.PGerr
o.PGdev:	StubsG:clib.h.kernel
o.PGdev:	h.PGdev
o.PGdev:	h.PGdevH
o.PGerr:	c.PGerr
o.PGerr:	StubsG:clib.h.kernel
o.PGerr:	StubsG:clib.h.swis
o.PGerr:	h.PGwin
o.PGerr:	StubsG:clib.h.kernel
o.PGerr:	h.PGspr
o.PGerr:	h.PGptr
o.PGerr:	h.PGspr
o.PGerr:	h.PGerr
o.PGerr:	StubsG:clib.h.kernel
o.PGflex:	c.PGflex
o.PGflex:	StubsG:clib.h.kernel
o.PGflex:	StubsG:clib.h.stdlib
o.PGflex:	StubsG:flexlib.h.flex
o.PGflex:	h.PGflex
o.PGfs:	c.PGfs
o.PGfs:	StubsG:clib.h.kernel
o.PGfs:	StubsG:clib.h.swis
o.PGfs:	h.PGerr
o.PGfs:	StubsG:clib.h.kernel
o.PGfs:	h.PGfs
o.PGgr:	c.PGgr
o.PGgr:	StubsG:clib.h.kernel
o.PGgr:	StubsG:clib.h.swis
o.PGgr:	h.PGgr
o.PGgr:	h.PGgrH
o.PGicn:	c.PGicn
o.PGicn:	StubsG:clib.h.kernel
o.PGicn:	StubsG:clib.h.swis
o.PGicn:	h.PGerr
o.PGicn:	StubsG:clib.h.kernel
o.PGicn:	h.PGwin
o.PGicn:	StubsG:clib.h.kernel
o.PGicn:	h.PGspr
o.PGicn:	h.PGwinH
o.PGicn:	h.PGspr
o.PGicn:	h.PGsprH
o.PGicn:	h.PGicn
o.PGicn:	h.PGspr
o.PGicn:	h.PGwin
o.PGicn:	h.PGicnH
o.PGicn:	h.BarSpr
o.PGmnu:	c.PGmnu
o.PGmnu:	StubsG:clib.h.kernel
o.PGmnu:	StubsG:clib.h.swis
o.PGmnu:	h.PGmnu
o.PGmnu:	h.PGwin
o.PGmnu:	StubsG:clib.h.kernel
o.PGmnu:	h.PGspr
o.PGmnu:	h.PGmnuH
o.PGmnu:	h.PGwin
o.PGmnu:	h.PGwinH
o.PGmnu:	h.PGerr
o.PGmnu:	StubsG:clib.h.kernel
o.PGmode:	c.PGmode
o.PGmode:	StubsG:clib.h.kernel
o.PGmode:	StubsG:clib.h.swis
o.PGmode:	h.PGmode
o.PGprt:	c.PGprt
o.PGprt:	StubsG:clib.h.stdio
o.PGprt:	StubsG:clib.h.kernel
o.PGprt:	StubsG:clib.h.swis
o.PGprt:	h.PGerr
o.PGprt:	StubsG:clib.h.kernel
o.PGprt:	h.PGwin
o.PGprt:	StubsG:clib.h.kernel
o.PGprt:	h.PGspr
o.PGprt:	h.PGwinH
o.PGprt:	h.PGprt
o.PGptr:	c.PGptr
o.PGptr:	StubsG:clib.h.kernel
o.PGptr:	StubsG:clib.h.swis
o.PGptr:	h.PGptr
o.PGptr:	h.PGspr
o.PGptr:	h.hg_code
o.PGscan:	c.PGscan
o.PGscan:	StubsG:clib.h.kernel
o.PGscan:	StubsG:clib.h.swis
o.PGscan:	h.PGscan
o.PGscn:	c.PGscn
o.PGscn:	StubsG:clib.h.kernel
o.PGscn:	StubsG:clib.h.swis
o.PGscn:	StubsG:clib.h.stdlib
o.PGscn:	h.PGspr
o.PGscn:	h.PGwin
o.PGscn:	StubsG:clib.h.kernel
o.PGscn:	h.PGspr
o.PGscn:	h.PGwinH
o.PGscn:	h.PGscn
o.PGscn:	h.PGscnH
o.PGspr:	c.PGspr
o.PGspr:	StubsG:clib.h.kernel
o.PGspr:	StubsG:clib.h.swis
o.PGspr:	StubsG:clib.h.stdio
o.PGspr:	StubsG:clib.h.stdlib
o.PGspr:	h.PGerr
o.PGspr:	StubsG:clib.h.kernel
o.PGspr:	h.PGgr
o.PGspr:	h.PGgrH
o.PGspr:	h.PGmode
o.PGspr:	h.PGspr
o.PGspr:	h.PGsprH
o.PGsprf:	c.PGsprf
o.PGsprf:	StubsG:clib.h.kernel
o.PGsprf:	StubsG:clib.h.swis
o.PGsprf:	StubsG:clib.h.stdio
o.PGsprf:	StubsG:clib.h.stdlib
o.PGsprf:	h.PGerr
o.PGsprf:	StubsG:clib.h.kernel
o.PGsprf:	h.PGmode
o.PGsprf:	h.PGflex
o.PGsprf:	h.PGspr
o.PGsprf:	h.PGsprH
o.PGtm:	c.PGtm
o.PGtm:	StubsG:clib.h.kernel
o.PGtm:	StubsG:clib.h.swis
o.PGtm:	h.PGerr
o.PGtm:	StubsG:clib.h.kernel
o.PGtm:	h.PGtm
o.PGvar:	c.PGvar
o.PGvar:	StubsG:clib.h.kernel
o.PGvar:	StubsG:clib.h.swis
o.PGvar:	h.PGerr
o.PGvar:	StubsG:clib.h.kernel
o.PGvar:	h.PGvar
o.PGwin:	c.PGwin
o.PGwin:	StubsG:clib.h.kernel
o.PGwin:	StubsG:clib.h.swis
o.PGwin:	h.PGerr
o.PGwin:	StubsG:clib.h.kernel
o.PGwin:	h.PGgr
o.PGwin:	h.PGptr
o.PGwin:	h.PGspr
o.PGwin:	h.PGfs
o.PGwin:	h.PGicn
o.PGwin:	h.PGspr
o.PGwin:	h.PGwin
o.PGwin:	StubsG:clib.h.kernel
o.PGwin:	h.PGspr
o.PGwin:	h.PGicnH
o.PGwin:	h.PGdevH
o.PGwin:	h.PGmnu
o.PGwin:	h.PGwin
o.PGwin:	h.PGmnuH
o.PGwin:	h.PGspr
o.PGwin:	h.PGsprH
o.PGwin:	h.PGwin
o.PGwin:	h.PGwinH
o.hg_code26:	c.hg_code26
o32.PGdev:	c.PGdev
o32.PGdev:	StubsG:clib.h.kernel
o32.PGdev:	StubsG:clib.h.swis
o32.PGdev:	h.PGwin
o32.PGdev:	StubsG:clib.h.kernel
o32.PGdev:	h.PGspr
o32.PGdev:	h.PGerr
o32.PGdev:	StubsG:clib.h.kernel
o32.PGdev:	h.PGdev
o32.PGdev:	h.PGdevH
o32.PGerr:	c.PGerr
o32.PGerr:	StubsG:clib.h.kernel
o32.PGerr:	StubsG:clib.h.swis
o32.PGerr:	h.PGwin
o32.PGerr:	StubsG:clib.h.kernel
o32.PGerr:	h.PGspr
o32.PGerr:	h.PGptr
o32.PGerr:	h.PGspr
o32.PGerr:	h.PGerr
o32.PGerr:	StubsG:clib.h.kernel
o32.PGflex:	c.PGflex
o32.PGflex:	StubsG:clib.h.kernel
o32.PGflex:	StubsG:clib.h.stdlib
o32.PGflex:	StubsG:flexlib.h.flex
o32.PGflex:	h.PGflex
o32.PGfs:	c.PGfs
o32.PGfs:	StubsG:clib.h.kernel
o32.PGfs:	StubsG:clib.h.swis
o32.PGfs:	h.PGerr
o32.PGfs:	StubsG:clib.h.kernel
o32.PGfs:	h.PGfs
o32.PGgr:	c.PGgr
o32.PGgr:	StubsG:clib.h.kernel
o32.PGgr:	StubsG:clib.h.swis
o32.PGgr:	h.PGgr
o32.PGgr:	h.PGgrH
o32.PGicn:	c.PGicn
o32.PGicn:	StubsG:clib.h.kernel
o32.PGicn:	StubsG:clib.h.swis
o32.PGicn:	h.PGerr
o32.PGicn:	StubsG:clib.h.kernel
o32.PGicn:	h.PGwin
o32.PGicn:	StubsG:clib.h.kernel
o32.PGicn:	h.PGspr
o32.PGicn:	h.PGwinH
o32.PGicn:	h.PGspr
o32.PGicn:	h.PGsprH
o32.PGicn:	h.PGicn
o32.PGicn:	h.PGspr
o32.PGicn:	h.PGwin
o32.PGicn:	h.PGicnH
o32.PGicn:	h.BarSpr
o32.PGmnu:	c.PGmnu
o32.PGmnu:	StubsG:clib.h.kernel
o32.PGmnu:	StubsG:clib.h.swis
o32.PGmnu:	h.PGmnu
o32.PGmnu:	h.PGwin
o32.PGmnu:	StubsG:clib.h.kernel
o32.PGmnu:	h.PGspr
o32.PGmnu:	h.PGmnuH
o32.PGmnu:	h.PGwin
o32.PGmnu:	h.PGwinH
o32.PGmnu:	h.PGerr
o32.PGmnu:	StubsG:clib.h.kernel
o32.PGmode:	c.PGmode
o32.PGmode:	StubsG:clib.h.kernel
o32.PGmode:	StubsG:clib.h.swis
o32.PGmode:	h.PGmode
o32.PGprt:	c.PGprt
o32.PGprt:	StubsG:clib.h.stdio
o32.PGprt:	StubsG:clib.h.kernel
o32.PGprt:	StubsG:clib.h.swis
o32.PGprt:	h.PGerr
o32.PGprt:	StubsG:clib.h.kernel
o32.PGprt:	h.PGwin
o32.PGprt:	StubsG:clib.h.kernel
o32.PGprt:	h.PGspr
o32.PGprt:	h.PGwinH
o32.PGprt:	h.PGprt
o32.PGptr:	c.PGptr
o32.PGptr:	StubsG:clib.h.kernel
o32.PGptr:	StubsG:clib.h.swis
o32.PGptr:	h.PGptr
o32.PGptr:	h.PGspr
o32.PGptr:	h.hg_code
o32.PGscan:	c.PGscan
o32.PGscan:	StubsG:clib.h.kernel
o32.PGscan:	StubsG:clib.h.swis
o32.PGscan:	h.PGscan
o32.PGscn:	c.PGscn
o32.PGscn:	StubsG:clib.h.kernel
o32.PGscn:	StubsG:clib.h.swis
o32.PGscn:	StubsG:clib.h.stdlib
o32.PGscn:	h.PGspr
o32.PGscn:	h.PGwin
o32.PGscn:	StubsG:clib.h.kernel
o32.PGscn:	h.PGspr
o32.PGscn:	h.PGwinH
o32.PGscn:	h.PGscn
o32.PGscn:	h.PGscnH
o32.PGspr:	c.PGspr
o32.PGspr:	StubsG:clib.h.kernel
o32.PGspr:	StubsG:clib.h.swis
o32.PGspr:	StubsG:clib.h.stdio
o32.PGspr:	StubsG:clib.h.stdlib
o32.PGspr:	h.PGerr
o32.PGspr:	StubsG:clib.h.kernel
o32.PGspr:	h.PGgr
o32.PGspr:	h.PGgrH
o32.PGspr:	h.PGmode
o32.PGspr:	h.PGspr
o32.PGspr:	h.PGsprH
o32.PGsprf:	c.PGsprf
o32.PGsprf:	StubsG:clib.h.kernel
o32.PGsprf:	StubsG:clib.h.swis
o32.PGsprf:	StubsG:clib.h.stdio
o32.PGsprf:	StubsG:clib.h.stdlib
o32.PGsprf:	h.PGerr
o32.PGsprf:	StubsG:clib.h.kernel
o32.PGsprf:	h.PGmode
o32.PGsprf:	h.PGflex
o32.PGsprf:	h.PGspr
o32.PGsprf:	h.PGsprH
o32.PGtm:	c.PGtm
o32.PGtm:	StubsG:clib.h.kernel
o32.PGtm:	StubsG:clib.h.swis
o32.PGtm:	h.PGerr
o32.PGtm:	StubsG:clib.h.kernel
o32.PGtm:	h.PGtm
o32.PGvar:	c.PGvar
o32.PGvar:	StubsG:clib.h.kernel
o32.PGvar:	StubsG:clib.h.swis
o32.PGvar:	h.PGerr
o32.PGvar:	StubsG:clib.h.kernel
o32.PGvar:	h.PGvar
o32.PGwin:	c.PGwin
o32.PGwin:	StubsG:clib.h.kernel
o32.PGwin:	StubsG:clib.h.swis
o32.PGwin:	h.PGerr
o32.PGwin:	StubsG:clib.h.kernel
o32.PGwin:	h.PGgr
o32.PGwin:	h.PGptr
o32.PGwin:	h.PGspr
o32.PGwin:	h.PGfs
o32.PGwin:	h.PGicn
o32.PGwin:	h.PGspr
o32.PGwin:	h.PGwin
o32.PGwin:	StubsG:clib.h.kernel
o32.PGwin:	h.PGspr
o32.PGwin:	h.PGicnH
o32.PGwin:	h.PGdevH
o32.PGwin:	h.PGmnu
o32.PGwin:	h.PGwin
o32.PGwin:	h.PGmnuH
o32.PGwin:	h.PGspr
o32.PGwin:	h.PGsprH
o32.PGwin:	h.PGwin
o32.PGwin:	h.PGwinH
o32.hg_code32:	c.hg_code32
