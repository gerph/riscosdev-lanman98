# Project:   CIFS

#MEMCHECK_CC = MemCheck.CC

#Tools

#CC = MemCheck.CC cc -g
#LINKMOD = MemCheck.DDTModLink DrLink
#LINKAPP = Link -d
#MCMODLIB = MemCheck:o.MC_M
#MCAPPLIB = MemCheck:o.MC
#BASELIB = BaseLIB:o.BaseLIBZM
#FSLIB = FSLIB:o.FSLIBZM
#FSLIBDem = FSLIB:o.FSLIBZMDem

CC         = cc
LINKMOD    = Link
LINKAPP    = Link
MCMODLIB   =
MCAPPLIB   =
BASELIB    = BaseLIB:o.BaseLIBZ4
BASELIB32  = BaseLIB:o.BaseLIBZ32
FSLIB      = FSLIB:o.FSLIBZ
FSLIB32    = FSLIB:o.FSLIBZ32
FSLIBDem   = FSLIB:o.FSLIBZDem
FSLIBDem32 = FSLIB:o.FSLIBZDem32


# Toolflags:
CCflagsMod    = -c -depend !Depend -IFSLIB:,BaseLIB:,C: -throwback -zM -ff -apcs 3/26bit/fpe3 -memaccess -L22-S22
CC32flagsMod  = -c -depend !Depend -IFSLIB:,BaseLIB:,C: -throwback -zM -ff -apcs 3/32bit/fpe3 -memaccess -L22-S22
CCflagsApp    = -c -depend !Depend -IC:,PG: -throwback -ff -apcs 3/26bit/fpe3 -memaccess -L22-S22
CC32flagsApp  = -c -depend !Depend -IC:,PG: -throwback -ff -apcs 3/32bit/fpe3 -memaccess -L22-S22
LinkflagsMod  = -rmf -c++ -o $@ 
LinkflagsApp  = -aif -c++ -o $@ 
ObjAsmflags   = -throwback -NoCache -depend !Depend -PreDefine "ATPCS32 SETL {FALSE}" -apcs 3/26bit
ObjAsm32flags = -throwback -NoCache -depend !Depend -PreDefine "ATPCS32 SETL {TRUE}" -apcs 3/32bit
CMHGflags     = -26bit -depend !Depend -throwBack 
CMHG32flags   = -32bit -depend !Depend -throwBack 

#OTarget    = @.LanMan98-26
OTarget32  = @.!LanMan98.LanMan98 

#OTargetD   = @.!InstLM98.Demo26.!LanMan98.LanMan98 
#OTargetD32 = @.!InstLM98.Demo.!LanMan98.LanMan98 

#OFTarget   = @.!Filer26 
OFTarget32 = @.!LanMan98.!Filer 

#Filer98     = @.o.filer98 @.o.lm98enum PG:o.PGmod StubsG:clib.o.stubs
Filer98_32  = @.o32.filer98 @.o32.lm98enum PG:o32.PGmod StubsG:clib.o.stubsG

OMMain =			\
	@.omod.omniheader	\
	@.omod.omnimain		\
        @.omod.printer		\
	@.omod.logon		\
        @.omod.fsys		\
	@.omod.date		\
	@.omod.mapping		\
        @.omod.trans 		\
	@.omod.lm2		\
	@.omod.smb		\
	@.omod.des		\
	@.omod.md4		\
	@.omod.mb		\
	@.omod.vc 		\
        @.omod.smberr		\
	@.omod.showfree		\
	@.omod.netbios 		\
        @.omod.blocked		\
	@.omod.prod 		\
        @.omod.var		\
	@.omod.reg		\
	@.omod.word		\
	@.omod.debug		\
	@.omod.base
         
OMMain32 =			\
	@.omod32.omniheader	\
	@.omod32.omnimain	\
        @.omod32.printer	\
	@.omod32.logon		\
        @.omod32.fsys		\
	@.omod32.date		\
	@.omod32.mapping	\
        @.omod32.trans 		\
	@.omod32.lm2		\
	@.omod32.smb		\
	@.omod32.des		\
	@.omod32.md4		\
	@.omod32.mb		\
	@.omod32.vc 		\
        @.omod32.smberr		\
	@.omod32.showfree	\
	@.omod32.netbios 	\
        @.omod32.blocked	\
	@.omod32.prod 		\
        @.omod32.var		\
	@.omod32.reg		\
	@.omod32.word		\
	@.omod32.debug		\
	@.omod32.base

RLIB   = TCP4:o.socklibzm TCP4:o.inetlibzm TCP4:o.unixlibzm StubsG:clib.o.stubs
RLIB32 = TCPIPLibs:o.socklibzm TCPIPLibs:o.inetlibzm TCPIPLibs:o.unixlibzm StubsG:clib.o.stubsG

OModule      = $(OMMain) $(FSLIB) $(BASELIB) $(RLIB) 
OModule32    = $(OMMain32) $(FSLIB32) $(BASELIB32) $(RLIB32) 

OModuleDem   = $(OMMain) $(FSLIBDem) $(BASELIB) $(RLIB) 
OModuleDem32 = $(OMMain32) $(FSLIBDem32) $(BASELIB32) $(RLIB32) 

# Standard Rules
.SUFFIXES:    .o .o32 .c .s .omod .omod32
.c.o:;		$(CC) $(ccflagsApp) -o $@ $<
.c.o32:;	$(CC) $(cc32flagsApp) -o $@ $<
.c.omod:;	$(CC) $(ccflagsMod) -o $@ $<
.c.omod32:;	$(CC) $(cc32flagsMod) -o $@ $<
.s.omod:;	objasm $(objasmflags) -to $@ -from $<
.s.omod32:;	objasm $(objasm32flags) -to $@ -from $<
.s.o:;		objasm $(objasmflags) -to $@ -from $<
.s.o32:;	objasm $(objasm32flags) -to $@ -from $<
.cmhg.omod:;	cmhg $(cmhgflags) -o $@ $<
.cmhg.omod32:;	cmhg $(cmhg32flags) -o $@ $<

# Final targets:
All:  $(OTarget) $(OTargetD) $(OFTarget) $(OTarget32) $(OTargetD32) $(OFTarget32)

Clean:
	every2 "@.o.filer98 @.o.lm98enum $(OMMain)" delete %0	
	every2 "@.o32.filer98 @.o32.lm98enum $(OMMain32)" delete %0	

CleanDist: Clean
	Remove $(OTarget)
	Remove $(OTarget32)
	Remove $(OTargetD)
	Remove $(OTargetD32)
	Remove $(OFTarget)
	Remove $(OFTarget32)


# User-editable dependencies:

$(OTarget):   $(OModule)
        $(LINKMOD) $(LinkflagsMod) $(OModule) $(MCMODLIB)

$(OTarget32):   $(OModule32)
        $(LINKMOD) $(LinkflagsMod) $(OModule32) $(MCMODLIB32)

$(OTargetD):   $(OModuleDem)
        $(LINKMOD) $(LinkflagsMod) $(OModuleDem) $(MCMODLIB)

$(OTargetD32):   $(OModuleDem32)
        $(LINKMOD) $(LinkflagsMod) $(OModuleDem32) $(MCMODLIB32)

$(OFTarget):   $(Filer98)
        $(LINKAPP) $(LinkflagsApp) $(Filer98) $(MCAPPLIB)
        SetType $(OFTarget) Absolute

$(OFTarget32):   $(Filer98_32)
        $(LINKAPP) $(LinkflagsApp) $(Filer98_32) $(MCAPPLIB32)
        SetType $(OFTarget32) Absolute

omniheader.h: cmhg.omniheader
	cmhg $(cmhg32flags) cmhg.omniheader -d $@

omnimain.c: omniheader.h

# Static dependencies:


# Dynamic dependencies:
omod.printer:	c.printer
omod.printer:	C:h.swis
omod.printer:	C:h.kernel
omod.printer:	BaseLIB:h.strext
omod.printer:	BaseLIB:h.error
omod.printer:	C:h.kernel
omod.printer:	BaseLIB:h.memory
omod.printer:	BaseLIB:h.errorxxx
omod.printer:	BaseLIB:h.nsetjmp
omod.printer:	FSLIB:h.fsys_err
omod.printer:	h.netbios
omod.printer:	BaseLIB:h.tcp
omod.printer:	h.logon
omod.printer:	h.smb
omod.printer:	BaseLIB:h.tcp
omod.printer:	FSLIB:h.path
omod.printer:	h.smbbase
omod.printer:	h.printer
omod.printer:	FSLIB:h.fsys
omod.printer:	FSLIB:h.path
omod.logon:	c.logon
omod.logon:	BaseLIB:h.error
omod.logon:	C:h.kernel
omod.logon:	BaseLIB:h.memory
omod.logon:	BaseLIB:h.errorxxx
omod.logon:	BaseLIB:h.nsetjmp
omod.logon:	BaseLIB:h.memory
omod.logon:	h.word
omod.logon:	BaseLIB:h.strext
omod.logon:	h.var
omod.logon:	h.trans
omod.logon:	h.vc
omod.logon:	h.data
omod.logon:	BaseLIB:h.tcp
omod.logon:	h.smb
omod.logon:	BaseLIB:h.tcp
omod.logon:	FSLIB:h.path
omod.logon:	h.smbbase
omod.logon:	h.smbsvr
omod.logon:	h.netbios
omod.logon:	BaseLIB:h.tcp
omod.logon:	h.lm2
omod.logon:	h.smbbase
omod.logon:	h.mount
omod.logon:	h.logon
omod.fsys:	c.fsys
omod.fsys:	C:h.swis
omod.fsys:	C:h.kernel
omod.fsys:	BaseLIB:h.strext
omod.fsys:	BaseLIB:h.memory
omod.fsys:	BaseLIB:h.error
omod.fsys:	C:h.kernel
omod.fsys:	BaseLIB:h.memory
omod.fsys:	BaseLIB:h.errorxxx
omod.fsys:	BaseLIB:h.nsetjmp
omod.fsys:	BaseLIB:h.time
omod.fsys:	BaseLIB:h.callback
omod.fsys:	h.blocked
omod.fsys:	BaseLIB:h.thread
omod.fsys:	FSLIB:h.fsys_err
omod.fsys:	FSLIB:h.fspatch
omod.fsys:	FSLIB:h.fsys
omod.fsys:	FSLIB:h.path
omod.fsys:	h.date
omod.fsys:	h.var
omod.fsys:	h.mapping
omod.fsys:	h.logon
omod.fsys:	h.netbios
omod.fsys:	BaseLIB:h.tcp
omod.fsys:	h.smb
omod.fsys:	BaseLIB:h.tcp
omod.fsys:	FSLIB:h.path
omod.fsys:	h.smbbase
omod.fsys:	h.vc
omod.fsys:	h.data
omod.fsys:	BaseLIB:h.tcp
omod.fsys:	h.smbsvr
omod.fsys:	h.printer
omod.fsys:	FSLIB:h.fsys
omod.fsys:	h.nodebug
omod.fsys:	FSLIB:h.fsys
omod.fsys:	h.mount
omod.date:	c.date
omod.date:	C:h.kernel
omod.date:	C:h.swis
omod.date:	h.date
omod.trans:	c.trans
omod.trans:	BaseLIB:h.memory
omod.trans:	BaseLIB:h.error
omod.trans:	C:h.kernel
omod.trans:	BaseLIB:h.memory
omod.trans:	BaseLIB:h.errorxxx
omod.trans:	BaseLIB:h.nsetjmp
omod.trans:	h.data
omod.trans:	h.vc
omod.trans:	h.data
omod.trans:	BaseLIB:h.tcp
omod.trans:	h.smbcmd
omod.trans:	h.mb
omod.trans:	h.data
omod.trans:	h.trans
omod.trans:	h.vc
omod.lm2:	c.lm2
omod.lm2:	BaseLIB:h.error
omod.lm2:	C:h.kernel
omod.lm2:	BaseLIB:h.memory
omod.lm2:	BaseLIB:h.errorxxx
omod.lm2:	BaseLIB:h.nsetjmp
omod.lm2:	BaseLIB:h.memory
omod.lm2:	h.vc
omod.lm2:	h.data
omod.lm2:	BaseLIB:h.tcp
omod.lm2:	h.mb
omod.lm2:	h.data
omod.lm2:	h.smbcmd
omod.lm2:	h.smb
omod.lm2:	BaseLIB:h.tcp
omod.lm2:	FSLIB:h.path
omod.lm2:	h.smbbase
omod.lm2:	h.smberr
omod.lm2:	h.trans
omod.lm2:	h.vc
omod.lm2:	BaseLIB:h.strext
omod.lm2:	h.date
omod.lm2:	h.lm2
omod.lm2:	h.smbbase
omod.lm2:	h.smbsvr
omod.lm2:	h.smbobj
omod.des:	c.des
omod.des:	BaseLIB:h.memory
omod.des:	h.des
omod.md4:	c.md4
omod.md4:	h.md4
omod.mb:	c.mb
omod.mb:	h.date
omod.mb:	h.word
omod.mb:	BaseLIB:h.error
omod.mb:	C:h.kernel
omod.mb:	BaseLIB:h.memory
omod.mb:	BaseLIB:h.errorxxx
omod.mb:	BaseLIB:h.nsetjmp
omod.mb:	h.mb
omod.mb:	h.data
omod.vc:	c.vc
omod.vc:	C:h.kernel
omod.vc:	C:h.swis
omod.vc:	BaseLIB:h.error
omod.vc:	C:h.kernel
omod.vc:	BaseLIB:h.memory
omod.vc:	BaseLIB:h.errorxxx
omod.vc:	BaseLIB:h.nsetjmp
omod.vc:	BaseLIB:h.memory
omod.vc:	h.blocked
omod.vc:	BaseLIB:h.thread
omod.vc:	BaseLIB:h.tcp
omod.vc:	BaseLIB:h.time
omod.vc:	h.netbios
omod.vc:	BaseLIB:h.tcp
omod.vc:	h.vc
omod.vc:	h.data
omod.vc:	BaseLIB:h.tcp
omod.smberr:	c.smberr
omod.smberr:	BaseLIB:h.error
omod.smberr:	C:h.kernel
omod.smberr:	BaseLIB:h.memory
omod.smberr:	BaseLIB:h.errorxxx
omod.smberr:	BaseLIB:h.nsetjmp
omod.smberr:	h.smberr
omod.showfree: s.showfree
omod.showfree: h.SWINames
omod.netbios:	c.netbios
omod.netbios:	BaseLIB:h.strext
omod.netbios:	BaseLIB:h.error
omod.netbios:	C:h.kernel
omod.netbios:	BaseLIB:h.memory
omod.netbios:	BaseLIB:h.errorxxx
omod.netbios:	BaseLIB:h.nsetjmp
omod.netbios:	BaseLIB:h.memory
omod.netbios:	h.blocked
omod.netbios:	BaseLIB:h.thread
omod.netbios:	h.word
omod.netbios:	BaseLIB:h.tcp
omod.netbios:	BaseLIB:h.time
omod.netbios:	h.var
omod.netbios:	h.netbios
omod.netbios:	BaseLIB:h.tcp
omod.blocked:	c.blocked
omod.blocked:	C:h.swis
omod.blocked:	C:h.kernel
omod.blocked:	BaseLIB:h.error
omod.blocked:	C:h.kernel
omod.blocked:	BaseLIB:h.memory
omod.blocked:	BaseLIB:h.errorxxx
omod.blocked:	BaseLIB:h.nsetjmp
omod.blocked:	BaseLIB:h.time
omod.blocked:	h.var
omod.blocked:	h.prod
omod.prod: s.prod
omod.prod: h.SWINames
omod.var:	c.var
omod.var:	C:h.kernel
omod.var:	C:h.swis
omod.var:	BaseLIB:h.error
omod.var:	C:h.kernel
omod.var:	BaseLIB:h.memory
omod.var:	BaseLIB:h.errorxxx
omod.var:	BaseLIB:h.nsetjmp
omod.var:	h.var
omod.reg: s.reg
omod.word:	c.word
omod.word:	h.word
omod.debug:	c.debug
omod.debug:	C:h.kernel
omod.debug:	C:h.swis
omod.base: s.base
o.filer98:	c.filer98
o.filer98:	C:h.swis
o.filer98:	C:h.kernel
o.filer98:	h.lm_swis
o.filer98:	C:h.kernel
o.filer98:	PG:h.PGwin
o.filer98:	C:h.kernel
o.filer98:	PG:h.PGspr
o.filer98:	PG:h.PGicn
o.filer98:	PG:h.PGspr
o.filer98:	PG:h.PGwin
o.filer98:	PG:h.PGmnu
o.filer98:	PG:h.PGwin
o.filer98:	PG:h.PGerr
o.filer98:	C:h.kernel
o.filer98:	h.lm98enum
o.lm98enum:	c.lm98enum
o.lm98enum:	C:h.kernel
o.lm98enum:	PG:h.PGerr
o.lm98enum:	C:h.kernel
o.lm98enum:	h.lm_swis
o.lm98enum:	h.lm98enum
omod.smb:	c.smb
omod.smb:	h.nodebug
omod.smb:	BaseLIB:h.strext
omod.smb:	h.date
omod.smb:	h.word
omod.smb:	h.data
omod.smb:	BaseLIB:h.error
omod.smb:	C:h.kernel
omod.smb:	BaseLIB:h.memory
omod.smb:	BaseLIB:h.errorxxx
omod.smb:	BaseLIB:h.nsetjmp
omod.smb:	BaseLIB:h.memory
omod.smb:	BaseLIB:h.tcp
omod.smb:	h.smbcmd
omod.smb:	h.smberr
omod.smb:	h.vc
omod.smb:	h.data
omod.smb:	BaseLIB:h.tcp
omod.smb:	h.mb
omod.smb:	h.data
omod.smb:	h.lm2
omod.smb:	h.smbbase
omod.smb:	h.des
omod.smb:	h.md4
omod.smb:	h.smb
omod.smb:	BaseLIB:h.tcp
omod.smb:	FSLIB:h.path
omod.smb:	h.smbbase
omod.smb:	h.smbsvr
omod.smb:	h.smbobj
omod.mapping:	c.mapping
omod.mapping:	C:h.swis
omod.mapping:	C:h.kernel
omod.mapping:	C:h.kernel
omod.mapping:	h.var
omod.mapping:	BaseLIB:h.error
omod.mapping:	C:h.kernel
omod.mapping:	BaseLIB:h.memory
omod.mapping:	BaseLIB:h.errorxxx
omod.mapping:	BaseLIB:h.nsetjmp
omod.mapping:	h.mapping
omod.omnimain:	c.omnimain
omod.omnimain:	C:h.swis
omod.omnimain:	C:h.kernel
omod.omnimain:	C:h.kernel
omod.omnimain:	BaseLIB:h.error
omod.omnimain:	C:h.kernel
omod.omnimain:	BaseLIB:h.memory
omod.omnimain:	BaseLIB:h.errorxxx
omod.omnimain:	BaseLIB:h.nsetjmp
omod.omnimain:	h.nodebug
omod.omnimain:	BaseLIB:h.memory
omod.omnimain:	BaseLIB:h.callback
omod.omnimain:	h.omni_swis
omod.omnimain:	h.lm_swis
omod.omnimain:	FSLIB:h.fspatch
omod.omnimain:	FSLIB:h.fsys
omod.omnimain:	FSLIB:h.path
omod.omnimain:	h.showfree
omod.omnimain:	FSLIB:h.fsys
omod.omnimain:	h.mount
omod.omnimain:	h.netbios
omod.omnimain:	BaseLIB:h.tcp
omod.omnimain:	h.logon
omod.omnimain:	h.mapping
omod.omnimain:	h.omniheader
omod32.md4:	c.md4
omod32.md4:	h.md4
omod32.printer:	c.printer
omod32.printer:	C:h.swis
omod32.printer:	C:h.kernel
omod32.printer:	BaseLIB:h.strext
omod32.printer:	BaseLIB:h.error
omod32.printer:	C:h.kernel
omod32.printer:	BaseLIB:h.memory
omod32.printer:	BaseLIB:h.errorxxx
omod32.printer:	BaseLIB:h.nsetjmp
omod32.printer:	FSLIB:h.fsys_err
omod32.printer:	h.netbios
omod32.printer:	BaseLIB:h.tcp
omod32.printer:	h.logon
omod32.printer:	h.smb
omod32.printer:	BaseLIB:h.tcp
omod32.printer:	FSLIB:h.path
omod32.printer:	h.smbbase
omod32.printer:	h.printer
omod32.printer:	FSLIB:h.fsys
omod32.printer:	FSLIB:h.path
omod32.logon:	c.logon
omod32.logon:	BaseLIB:h.error
omod32.logon:	C:h.kernel
omod32.logon:	BaseLIB:h.memory
omod32.logon:	BaseLIB:h.errorxxx
omod32.logon:	BaseLIB:h.nsetjmp
omod32.logon:	BaseLIB:h.memory
omod32.logon:	h.word
omod32.logon:	BaseLIB:h.strext
omod32.logon:	h.var
omod32.logon:	h.trans
omod32.logon:	h.vc
omod32.logon:	h.data
omod32.logon:	BaseLIB:h.tcp
omod32.logon:	h.smb
omod32.logon:	BaseLIB:h.tcp
omod32.logon:	FSLIB:h.path
omod32.logon:	h.smbbase
omod32.logon:	h.smbsvr
omod32.logon:	h.netbios
omod32.logon:	BaseLIB:h.tcp
omod32.logon:	h.lm2
omod32.logon:	h.smbbase
omod32.logon:	h.mount
omod32.logon:	h.logon
omod32.fsys:	c.fsys
omod32.fsys:	C:h.swis
omod32.fsys:	C:h.kernel
omod32.fsys:	BaseLIB:h.strext
omod32.fsys:	BaseLIB:h.memory
omod32.fsys:	BaseLIB:h.error
omod32.fsys:	C:h.kernel
omod32.fsys:	BaseLIB:h.memory
omod32.fsys:	BaseLIB:h.errorxxx
omod32.fsys:	BaseLIB:h.nsetjmp
omod32.fsys:	BaseLIB:h.time
omod32.fsys:	BaseLIB:h.callback
omod32.fsys:	h.blocked
omod32.fsys:	BaseLIB:h.thread
omod32.fsys:	FSLIB:h.fsys_err
omod32.fsys:	FSLIB:h.fspatch
omod32.fsys:	FSLIB:h.fsys
omod32.fsys:	FSLIB:h.path
omod32.fsys:	h.date
omod32.fsys:	h.var
omod32.fsys:	h.mapping
omod32.fsys:	h.logon
omod32.fsys:	h.netbios
omod32.fsys:	BaseLIB:h.tcp
omod32.fsys:	h.smb
omod32.fsys:	BaseLIB:h.tcp
omod32.fsys:	FSLIB:h.path
omod32.fsys:	h.smbbase
omod32.fsys:	h.vc
omod32.fsys:	h.data
omod32.fsys:	BaseLIB:h.tcp
omod32.fsys:	h.smbsvr
omod32.fsys:	h.printer
omod32.fsys:	FSLIB:h.fsys
omod32.fsys:	h.nodebug
omod32.fsys:	FSLIB:h.fsys
omod32.fsys:	h.mount
omod32.date:	c.date
omod32.date:	C:h.kernel
omod32.date:	C:h.swis
omod32.date:	h.date
omod32.mapping:	c.mapping
omod32.mapping:	C:h.swis
omod32.mapping:	C:h.kernel
omod32.mapping:	C:h.kernel
omod32.mapping:	h.var
omod32.mapping:	BaseLIB:h.error
omod32.mapping:	C:h.kernel
omod32.mapping:	BaseLIB:h.memory
omod32.mapping:	BaseLIB:h.errorxxx
omod32.mapping:	BaseLIB:h.nsetjmp
omod32.mapping:	h.mapping
omod32.trans:	c.trans
omod32.trans:	BaseLIB:h.memory
omod32.trans:	BaseLIB:h.error
omod32.trans:	C:h.kernel
omod32.trans:	BaseLIB:h.memory
omod32.trans:	BaseLIB:h.errorxxx
omod32.trans:	BaseLIB:h.nsetjmp
omod32.trans:	h.data
omod32.trans:	h.vc
omod32.trans:	h.data
omod32.trans:	BaseLIB:h.tcp
omod32.trans:	h.smbcmd
omod32.trans:	h.mb
omod32.trans:	h.data
omod32.trans:	h.trans
omod32.trans:	h.vc
omod32.lm2:	c.lm2
omod32.lm2:	BaseLIB:h.error
omod32.lm2:	C:h.kernel
omod32.lm2:	BaseLIB:h.memory
omod32.lm2:	BaseLIB:h.errorxxx
omod32.lm2:	BaseLIB:h.nsetjmp
omod32.lm2:	BaseLIB:h.memory
omod32.lm2:	h.vc
omod32.lm2:	h.data
omod32.lm2:	BaseLIB:h.tcp
omod32.lm2:	h.mb
omod32.lm2:	h.data
omod32.lm2:	h.smbcmd
omod32.lm2:	h.smb
omod32.lm2:	BaseLIB:h.tcp
omod32.lm2:	FSLIB:h.path
omod32.lm2:	h.smbbase
omod32.lm2:	h.smberr
omod32.lm2:	h.trans
omod32.lm2:	h.vc
omod32.lm2:	BaseLIB:h.strext
omod32.lm2:	h.date
omod32.lm2:	h.lm2
omod32.lm2:	h.smbbase
omod32.lm2:	h.smbsvr
omod32.lm2:	h.smbobj
omod32.smb:	c.smb
omod32.smb:	h.nodebug
omod32.smb:	BaseLIB:h.strext
omod32.smb:	h.date
omod32.smb:	h.word
omod32.smb:	h.data
omod32.smb:	BaseLIB:h.error
omod32.smb:	C:h.kernel
omod32.smb:	BaseLIB:h.memory
omod32.smb:	BaseLIB:h.errorxxx
omod32.smb:	BaseLIB:h.nsetjmp
omod32.smb:	BaseLIB:h.memory
omod32.smb:	BaseLIB:h.tcp
omod32.smb:	h.smbcmd
omod32.smb:	h.smberr
omod32.smb:	h.vc
omod32.smb:	h.data
omod32.smb:	BaseLIB:h.tcp
omod32.smb:	h.mb
omod32.smb:	h.data
omod32.smb:	h.lm2
omod32.smb:	h.smbbase
omod32.smb:	h.des
omod32.smb:	h.md4
omod32.smb:	h.smb
omod32.smb:	BaseLIB:h.tcp
omod32.smb:	FSLIB:h.path
omod32.smb:	h.smbbase
omod32.smb:	h.smbsvr
omod32.smb:	h.smbobj
omod32.des:	c.des
omod32.des:	BaseLIB:h.memory
omod32.des:	h.des
omod32.mb:	c.mb
omod32.mb:	h.date
omod32.mb:	h.word
omod32.mb:	BaseLIB:h.error
omod32.mb:	C:h.kernel
omod32.mb:	BaseLIB:h.memory
omod32.mb:	BaseLIB:h.errorxxx
omod32.mb:	BaseLIB:h.nsetjmp
omod32.mb:	h.mb
omod32.mb:	h.data
omod32.vc:	c.vc
omod32.vc:	C:h.kernel
omod32.vc:	C:h.swis
omod32.vc:	BaseLIB:h.error
omod32.vc:	C:h.kernel
omod32.vc:	BaseLIB:h.memory
omod32.vc:	BaseLIB:h.errorxxx
omod32.vc:	BaseLIB:h.nsetjmp
omod32.vc:	BaseLIB:h.memory
omod32.vc:	h.blocked
omod32.vc:	BaseLIB:h.thread
omod32.vc:	BaseLIB:h.tcp
omod32.vc:	BaseLIB:h.time
omod32.vc:	h.netbios
omod32.vc:	BaseLIB:h.tcp
omod32.vc:	h.vc
omod32.vc:	h.data
omod32.vc:	BaseLIB:h.tcp
omod32.smberr:	c.smberr
omod32.smberr:	BaseLIB:h.error
omod32.smberr:	C:h.kernel
omod32.smberr:	BaseLIB:h.memory
omod32.smberr:	BaseLIB:h.errorxxx
omod32.smberr:	BaseLIB:h.nsetjmp
omod32.smberr:	h.smberr
omod32.showfree: s.showfree
omod32.showfree: h.SWINames
omod32.netbios:	c.netbios
omod32.netbios:	BaseLIB:h.strext
omod32.netbios:	BaseLIB:h.error
omod32.netbios:	C:h.kernel
omod32.netbios:	BaseLIB:h.memory
omod32.netbios:	BaseLIB:h.errorxxx
omod32.netbios:	BaseLIB:h.nsetjmp
omod32.netbios:	BaseLIB:h.memory
omod32.netbios:	h.blocked
omod32.netbios:	BaseLIB:h.thread
omod32.netbios:	h.word
omod32.netbios:	BaseLIB:h.tcp
omod32.netbios:	BaseLIB:h.time
omod32.netbios:	h.var
omod32.netbios:	h.netbios
omod32.netbios:	BaseLIB:h.tcp
omod32.blocked:	c.blocked
omod32.blocked:	C:h.swis
omod32.blocked:	C:h.kernel
omod32.blocked:	BaseLIB:h.error
omod32.blocked:	C:h.kernel
omod32.blocked:	BaseLIB:h.memory
omod32.blocked:	BaseLIB:h.errorxxx
omod32.blocked:	BaseLIB:h.nsetjmp
omod32.blocked:	BaseLIB:h.time
omod32.blocked:	h.var
omod32.blocked:	h.prod
omod32.prod: s.prod
omod32.prod: h.SWINames
omod32.var:	c.var
omod32.var:	C:h.kernel
omod32.var:	C:h.swis
omod32.var:	BaseLIB:h.error
omod32.var:	C:h.kernel
omod32.var:	BaseLIB:h.memory
omod32.var:	BaseLIB:h.errorxxx
omod32.var:	BaseLIB:h.nsetjmp
omod32.var:	h.var
omod32.reg: s.reg
omod32.word:	c.word
omod32.word:	h.word
omod32.debug:	c.debug
omod32.debug:	C:h.kernel
omod32.debug:	C:h.swis
omod32.base: s.base
o32.filer98:	c.filer98
o32.filer98:	C:h.swis
o32.filer98:	C:h.kernel
o32.filer98:	h.lm_swis
o32.filer98:	C:h.kernel
o32.filer98:	PG:h.PGwin
o32.filer98:	C:h.kernel
o32.filer98:	PG:h.PGspr
o32.filer98:	PG:h.PGicn
o32.filer98:	PG:h.PGspr
o32.filer98:	PG:h.PGwin
o32.filer98:	PG:h.PGmnu
o32.filer98:	PG:h.PGwin
o32.filer98:	PG:h.PGerr
o32.filer98:	C:h.kernel
o32.filer98:	h.lm98enum
o32.lm98enum:	c.lm98enum
o32.lm98enum:	C:h.kernel
o32.lm98enum:	PG:h.PGerr
o32.lm98enum:	C:h.kernel
o32.lm98enum:	h.lm_swis
o32.lm98enum:	h.lm98enum
omod32.omnimain:	c.omnimain
omod32.omnimain:	C:h.swis
omod32.omnimain:	C:h.kernel
omod32.omnimain:	C:h.kernel
omod32.omnimain:	BaseLIB:h.error
omod32.omnimain:	C:h.kernel
omod32.omnimain:	BaseLIB:h.memory
omod32.omnimain:	BaseLIB:h.errorxxx
omod32.omnimain:	BaseLIB:h.nsetjmp
omod32.omnimain:	h.nodebug
omod32.omnimain:	BaseLIB:h.memory
omod32.omnimain:	BaseLIB:h.callback
omod32.omnimain:	h.omni_swis
omod32.omnimain:	h.lm_swis
omod32.omnimain:	FSLIB:h.fspatch
omod32.omnimain:	FSLIB:h.fsys
omod32.omnimain:	FSLIB:h.path
omod32.omnimain:	h.showfree
omod32.omnimain:	FSLIB:h.fsys
omod32.omnimain:	h.mount
omod32.omnimain:	h.netbios
omod32.omnimain:	BaseLIB:h.tcp
omod32.omnimain:	h.logon
omod32.omnimain:	h.mapping
omod32.omnimain:	h.omniheader
