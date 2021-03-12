# Project:   BaseLIB

#MEMCHECK_CC = MemCheck.CC

# Toolflags:
CC4flagsMod = -c -Wp -depend !Depend -IBaseLIB:,C:,TCP4: -throwback -zM -apcs 3/26bit/fpe3 -memaccess -L22-S22
CCflagsMod = -c -Wp -depend !Depend -IBaseLIB:,C:,TCP5: -throwback -zM -DTCP5 -apcs 3/26bit/fpe3 -memaccess -L22-S22
CC32flagsMod = -c -Wp -depend !Depend -IBaseLIB:,C:,TCP32: -throwback -zM -apcs 3/32bit/fpe3 -memaccess -L22-S22
LibFileflags = -c -o $@
ObjAsmflags   = -throwback -NoCache -depend !Depend -PreDefine "ATPCS32 SETL {FALSE}" -apcs 3/26bit
ObjAsm32flags = -throwback -NoCache -depend !Depend -PreDefine "ATPCS32 SETL {TRUE}" -apcs 3/32bit

LIB =			\
	@.o.debug	\
	@.o.error	\
	@.o.gethost	\
	@.o.memory	\
	@.o.strext	\
	@.o.tcpbsd	\
	@.o.thread	\
	@.o.time	\
	@.o.blocked	\
	@.o.callback	\
	@.o.gethost_	\
	@.o.stack	\
	@.o.caller	\
	@.o.nsetjmp 

LIB4 =			\
	@.o4.debug	\
	@.o4.error	\
	@.o4.gethost	\
	@.o4.memory	\
	@.o4.strext	\
	@.o4.tcpbsd	\
	@.o4.thread	\
	@.o4.time	\
	@.o.blocked	\
	@.o.callback	\
	@.o.gethost_	\
	@.o.stack	\
	@.o.caller	\
	@.o.nsetjmp 

LIBM =			\
	@.om.debug	\
	@.om.error	\
	@.om.gethost	\
	@.om.memory	\
	@.om.strext	\
	@.om.tcpbsd	\
	@.om.thread	\
	@.om.time	\
	@.o.blocked	\
	@.o.callback	\
	@.o.gethost_	\
	@.o.stack	\
	@.o.caller	\
	@.o.nsetjmp 

LIB32 =			\
	@.o32.debug	\
	@.o32.error	\
	@.o32.gethost	\
	@.o32.memory	\
	@.o32.strext	\
	@.o32.tcpbsd	\
	@.o32.thread	\
	@.o32.time	\
	@.o32.blocked	\
	@.o32.callback	\
	@.o32.gethost_	\
	@.o32.stack	\
	@.o32.caller	\
	@.o32.nsetjmp 

LIBM32 =		\
	@.om32.debug	\
	@.om32.error	\
	@.om32.gethost	\
	@.om32.memory	\
	@.om32.strext	\
	@.om32.tcpbsd	\
	@.om32.thread	\
	@.om32.time	\
	@.o32.blocked	\
	@.o32.callback	\
	@.o32.gethost_	\
	@.o32.stack	\
	@.o32.caller	\
	@.o32.nsetjmp 


# Standard Rules
.SUFFIXES:    .om .o .o4 .o32 .om32 .c .s
.c.o:;		cc $(ccflagsMod) -o $@ $<
.c.o4:;		cc $(cc4flagsMod) -o $@ $<
.c.o32:;	cc $(cc32flagsMod) -o $@ $<
.c.om:;		$(MemCheck_CC) cc -g $(ccflagsMod) -o $@ $<
.c.om32:;	$(MemCheck_CC) cc -g $(cc32flagsMod) -o $@ $<
.s.o:;		objasm $(objasmflags) -to $@ -from $<
.s.o32:;	objasm $(objasm32flags) -to $@ -from $<


# Final targets:
All:	BaseLIB:o.BaseLIBZ	\
	BaseLIB:o.BaseLIBZ4	\
	BaseLIB:o.BaseLIBZM	\
	BaseLib:o.BaseLIBZ32	\
	BaseLib:o.BaseLIBZM32

Clean:
	every2 "@.o.* @.om.* @.o4.* @.o32.* @.om32.*" delete %0

Cleandist:
	every2 "@.o.* @.om.* BaseLIB:o.* @.o32.* @.om32.*" delete %0


# User-editable dependencies:

BaseLIB:o.BaseLIBZ4:   $(LIB4)
        LibFile $(LibFileFlags) $(LIB4)

BaseLIB:o.BaseLIBZ:   $(LIB)
        LibFile $(LibFileFlags) $(LIB)

BaseLIB:o.BaseLIBZM:   $(LIBM)
        LibFile $(LibFileFlags) $(LIBM)

BaseLIB:o.BaseLIBZ32:   $(LIB32)
        LibFile $(LibFileFlags) $(LIB32)

BaseLIB:o.BaseLIBZM32:   $(LIBM32)
        LibFile $(LibFileFlags) $(LIBM32)

@.o.tcpbsd: @.c.tcpbsd
	cc $(ccflagsMod) -Wd -Wp -o @.o.tcpbsd @.c.tcpbsd

@.o.gethost: @.c.gethost
	cc $(ccflagsMod) -Wd -Wp -o @.o.gethost @.c.gethost

@.om.tcpbsd: @.c.tcpbsd
	$(MemCheck_CC) cc -g $(ccflagsMod) -Wd -Wp -o @.om.tcpbsd @.c.tcpbsd

@.om.gethost: @.c.gethost
	$(MemCheck.CC) cc -g $(ccflagsMod) -Wd -Wp -o @.om.gethost @.c.gethost



# Static dependencies:


# Dynamic dependencies:
o32.callback: s.callback
o32.callback: h.SWINames
o32.gethost_: s.gethost_
o32.gethost_: h.RegNames
o32.stack: s.stack
o32.caller: s.caller
o32.nsetjmp: s.nsetjmp
o.debug:	c.debug
o.debug:	BaseLIB:h.error
o.debug:	C:h.kernel
o.debug:	BaseLIB:h.memory
o.debug:	BaseLIB:h.errorxxx
o.debug:	BaseLIB:h.nsetjmp
o.debug:	BaseLIB:h.memory
o.debug:	BaseLIB:h.debug
o.error:	c.error
o.error:	C:h.kernel
o.error:	C:h.swis
o.error:	BaseLIB:h.error
o.error:	C:h.kernel
o.error:	BaseLIB:h.memory
o.error:	BaseLIB:h.errorxxx
o.error:	BaseLIB:h.nsetjmp
o.error:	BaseLIB:h.memory
o.gethost:	c.gethost
o.gethost:	C:MemCheck.h.MemCheck
o.gethost:	TCP5:h.inetlib
o.gethost:	TCP5:sys.h.types
o.gethost:	TCP5:sys.h.cdefs
o.gethost:	TCP5:machine.h.endian
o.gethost:	TCP5:machine.h.ansi
o.gethost:	TCP5:machine.h.types
o.gethost:	TCP5:netinet.h.in
o.gethost:	TCP5:h.netdb
o.gethost:	TCP5:sys.h.cdefs
o.gethost:	TCP5:sys.h.types
o.gethost:	TCP5:sys.h.socket
o.gethost:	TCP5:sys.h.cdefs
o.gethost:	h.gethost_
o.gethost:	C:h.kernel
o.memory:	c.memory
o.memory:	MemCheck:h.MemCheck
o.memory:	C:h.kernel
o.memory:	C:h.swis
o.memory:	BaseLIB:h.error
o.memory:	C:h.kernel
o.memory:	BaseLIB:h.memory
o.memory:	BaseLIB:h.errorxxx
o.memory:	BaseLIB:h.nsetjmp
o.memory:	BaseLIB:h.memory
o.strext:	c.strext
o.strext:	BaseLIB:h.memory
o.strext:	BaseLIB:h.strext
o.tcpbsd:	c.tcpbsd
o.tcpbsd:	MemCheck:h.MemCheck
o.tcpbsd:	C:TCPIPLibs.h.errno
o.tcpbsd:	TCP5:sys.h.errno
o.tcpbsd:	C:h.kernel
o.tcpbsd:	TCP5:h.socklib
o.tcpbsd:	TCP5:sys.h.types
o.tcpbsd:	TCP5:sys.h.cdefs
o.tcpbsd:	TCP5:machine.h.endian
o.tcpbsd:	TCP5:machine.h.ansi
o.tcpbsd:	TCP5:machine.h.types
o.tcpbsd:	TCP5:sys.h.socket
o.tcpbsd:	TCP5:sys.h.cdefs
o.tcpbsd:	TCP5:sys.h.stat
o.tcpbsd:	TCP5:sys.h.time
o.tcpbsd:	TCP5:sys.h.cdefs
o.tcpbsd:	TCP5:sys.h.cdefs
o.tcpbsd:	TCP5:sys.h.time
o.tcpbsd:	TCP5:sys.h.uio
o.tcpbsd:	TCP5:sys.h.cdefs
o.tcpbsd:	C:h.kernel
o.tcpbsd:	TCP5:sys.h.ioctl
o.tcpbsd:	TCP5:sys.h.ttycom
o.tcpbsd:	TCP5:sys.h.ioccom
o.tcpbsd:	TCP5:sys.h.ioccom
o.tcpbsd:	TCP5:sys.h.filio
o.tcpbsd:	TCP5:sys.h.ioccom
o.tcpbsd:	TCP5:sys.h.sockio
o.tcpbsd:	TCP5:sys.h.ioccom
o.tcpbsd:	TCP5:sys.h.cdefs
o.tcpbsd:	TCP5:netinet.h.tcp
o.tcpbsd:	TCP5:h.netdb
o.tcpbsd:	TCP5:sys.h.cdefs
o.tcpbsd:	TCP5:h.unixlib
o.tcpbsd:	TCP5:h.inetlib
o.tcpbsd:	TCP5:sys.h.types
o.tcpbsd:	TCP5:netinet.h.in
o.tcpbsd:	h.gethost
o.tcpbsd:	C:h.swis
o.tcpbsd:	C:h.kernel
o.tcpbsd:	BaseLIB:h.debug
o.tcpbsd:	BaseLIB:h.error
o.tcpbsd:	C:h.kernel
o.tcpbsd:	BaseLIB:h.memory
o.tcpbsd:	BaseLIB:h.errorxxx
o.tcpbsd:	BaseLIB:h.nsetjmp
o.tcpbsd:	BaseLIB:h.memory
o.tcpbsd:	BaseLIB:h.thread
o.tcpbsd:	BaseLIB:h.tcp
o.thread:	c.thread
o.thread:	MemCheck:h.MemCheck
o.thread:	BaseLIB:h.nsetjmp
o.thread:	BaseLIB:h.debug
o.thread:	BaseLIB:h.error
o.thread:	C:h.kernel
o.thread:	BaseLIB:h.memory
o.thread:	BaseLIB:h.errorxxx
o.thread:	BaseLIB:h.nsetjmp
o.thread:	BaseLIB:h.memory
o.thread:	BaseLIB:h.time
o.thread:	BaseLIB:h.thread
o.time:	c.time
o.time:	C:h.kernel
o.time:	C:h.swis
o.time:	BaseLIB:h.time
o4.debug:	c.debug
o4.debug:	BaseLIB:h.error
o4.debug:	C:h.kernel
o4.debug:	BaseLIB:h.memory
o4.debug:	BaseLIB:h.errorxxx
o4.debug:	BaseLIB:h.nsetjmp
o4.debug:	BaseLIB:h.memory
o4.debug:	BaseLIB:h.debug
o4.error:	c.error
o4.error:	C:h.kernel
o4.error:	C:h.swis
o4.error:	BaseLIB:h.error
o4.error:	C:h.kernel
o4.error:	BaseLIB:h.memory
o4.error:	BaseLIB:h.errorxxx
o4.error:	BaseLIB:h.nsetjmp
o4.error:	BaseLIB:h.memory
o4.gethost:	c.gethost
o4.gethost:	C:MemCheck.h.MemCheck
o4.gethost:	TCP4:h.inetlib
o4.gethost:	TCP4:sys.h.types
o4.gethost:	TCP4:netinet.h.in
o4.gethost:	TCP4:h.netdb
o4.gethost:	TCP4:sys.h.types
o4.gethost:	TCP4:sys.h.socket
o4.gethost:	h.gethost_
o4.gethost:	C:h.kernel
o4.memory:	c.memory
o4.memory:	MemCheck:h.MemCheck
o4.memory:	C:h.kernel
o4.memory:	C:h.swis
o4.memory:	BaseLIB:h.error
o4.memory:	C:h.kernel
o4.memory:	BaseLIB:h.memory
o4.memory:	BaseLIB:h.errorxxx
o4.memory:	BaseLIB:h.nsetjmp
o4.memory:	BaseLIB:h.memory
o4.strext:	c.strext
o4.strext:	BaseLIB:h.memory
o4.strext:	BaseLIB:h.strext
o4.tcpbsd:	c.tcpbsd
o4.tcpbsd:	MemCheck:h.MemCheck
o4.tcpbsd:	C:TCPIPLibs.h.errno
o4.tcpbsd:	TCP4:sys.h.errno
o4.tcpbsd:	TCP4:sys.^.h.errno
o4.tcpbsd:	C:h.kernel
o4.tcpbsd:	TCP4:h.socklib
o4.tcpbsd:	TCP4:sys.h.types
o4.tcpbsd:	TCP4:sys.h.socket
o4.tcpbsd:	TCP4:sys.h.stat
o4.tcpbsd:	TCP4:sys.h.time
o4.tcpbsd:	TCP4:sys.h.time
o4.tcpbsd:	TCP4:sys.h.uio
o4.tcpbsd:	C:h.kernel
o4.tcpbsd:	TCP4:sys.h.ioctl
o4.tcpbsd:	TCP4:sys.h.ttychars
o4.tcpbsd:	TCP4:sys.h.ttydev
o4.tcpbsd:	TCP4:netinet.h.tcp
o4.tcpbsd:	TCP4:h.netdb
o4.tcpbsd:	TCP4:h.unixlib
o4.tcpbsd:	TCP4:h.inetlib
o4.tcpbsd:	TCP4:sys.h.types
o4.tcpbsd:	TCP4:netinet.h.in
o4.tcpbsd:	h.gethost
o4.tcpbsd:	C:h.swis
o4.tcpbsd:	C:h.kernel
o4.tcpbsd:	BaseLIB:h.debug
o4.tcpbsd:	BaseLIB:h.error
o4.tcpbsd:	C:h.kernel
o4.tcpbsd:	BaseLIB:h.memory
o4.tcpbsd:	BaseLIB:h.errorxxx
o4.tcpbsd:	BaseLIB:h.nsetjmp
o4.tcpbsd:	BaseLIB:h.memory
o4.tcpbsd:	BaseLIB:h.thread
o4.tcpbsd:	BaseLIB:h.tcp
o4.thread:	c.thread
o4.thread:	MemCheck:h.MemCheck
o4.thread:	BaseLIB:h.nsetjmp
o4.thread:	BaseLIB:h.debug
o4.thread:	BaseLIB:h.error
o4.thread:	C:h.kernel
o4.thread:	BaseLIB:h.memory
o4.thread:	BaseLIB:h.errorxxx
o4.thread:	BaseLIB:h.nsetjmp
o4.thread:	BaseLIB:h.memory
o4.thread:	BaseLIB:h.time
o4.thread:	BaseLIB:h.thread
o4.time:	c.time
o4.time:	C:h.kernel
o4.time:	C:h.swis
o4.time:	BaseLIB:h.time
om.debug:	c.debug
om.debug:	BaseLIB:h.error
om.debug:	C:h.kernel
om.debug:	BaseLIB:h.memory
om.debug:	BaseLIB:h.errorxxx
om.debug:	BaseLIB:h.nsetjmp
om.debug:	BaseLIB:h.memory
om.debug:	BaseLIB:h.debug
om.error:	c.error
om.error:	C:h.kernel
om.error:	C:h.swis
om.error:	BaseLIB:h.error
om.error:	C:h.kernel
om.error:	BaseLIB:h.memory
om.error:	BaseLIB:h.errorxxx
om.error:	BaseLIB:h.nsetjmp
om.error:	BaseLIB:h.memory
om.gethost:	c.gethost
om.gethost:	C:MemCheck.h.MemCheck
om.gethost:	TCP5:h.inetlib
om.gethost:	TCP5:sys.h.types
om.gethost:	TCP5:sys.h.cdefs
om.gethost:	TCP5:machine.h.endian
om.gethost:	TCP5:machine.h.ansi
om.gethost:	TCP5:machine.h.types
om.gethost:	TCP5:netinet.h.in
om.gethost:	TCP5:h.netdb
om.gethost:	TCP5:sys.h.cdefs
om.gethost:	TCP5:sys.h.types
om.gethost:	TCP5:sys.h.socket
om.gethost:	TCP5:sys.h.cdefs
om.gethost:	h.gethost_
om.gethost:	C:h.kernel
om.memory:	c.memory
om.memory:	MemCheck:h.MemCheck
om.memory:	C:h.kernel
om.memory:	C:h.swis
om.memory:	BaseLIB:h.error
om.memory:	C:h.kernel
om.memory:	BaseLIB:h.memory
om.memory:	BaseLIB:h.errorxxx
om.memory:	BaseLIB:h.nsetjmp
om.memory:	BaseLIB:h.memory
om.strext:	c.strext
om.strext:	BaseLIB:h.memory
om.strext:	BaseLIB:h.strext
om.tcpbsd:	c.tcpbsd
om.tcpbsd:	MemCheck:h.MemCheck
om.tcpbsd:	C:TCPIPLibs.h.errno
om.tcpbsd:	TCP5:sys.h.errno
om.tcpbsd:	C:h.kernel
om.tcpbsd:	TCP5:h.socklib
om.tcpbsd:	TCP5:sys.h.types
om.tcpbsd:	TCP5:sys.h.cdefs
om.tcpbsd:	TCP5:machine.h.endian
om.tcpbsd:	TCP5:machine.h.ansi
om.tcpbsd:	TCP5:machine.h.types
om.tcpbsd:	TCP5:sys.h.socket
om.tcpbsd:	TCP5:sys.h.cdefs
om.tcpbsd:	TCP5:sys.h.stat
om.tcpbsd:	TCP5:sys.h.time
om.tcpbsd:	TCP5:sys.h.cdefs
om.tcpbsd:	TCP5:sys.h.cdefs
om.tcpbsd:	TCP5:sys.h.time
om.tcpbsd:	TCP5:sys.h.uio
om.tcpbsd:	TCP5:sys.h.cdefs
om.tcpbsd:	C:h.kernel
om.tcpbsd:	TCP5:sys.h.ioctl
om.tcpbsd:	TCP5:sys.h.ttycom
om.tcpbsd:	TCP5:sys.h.ioccom
om.tcpbsd:	TCP5:sys.h.ioccom
om.tcpbsd:	TCP5:sys.h.filio
om.tcpbsd:	TCP5:sys.h.ioccom
om.tcpbsd:	TCP5:sys.h.sockio
om.tcpbsd:	TCP5:sys.h.ioccom
om.tcpbsd:	TCP5:sys.h.cdefs
om.tcpbsd:	TCP5:netinet.h.tcp
om.tcpbsd:	TCP5:h.netdb
om.tcpbsd:	TCP5:sys.h.cdefs
om.tcpbsd:	TCP5:h.unixlib
om.tcpbsd:	TCP5:h.inetlib
om.tcpbsd:	TCP5:sys.h.types
om.tcpbsd:	TCP5:netinet.h.in
om.tcpbsd:	h.gethost
om.tcpbsd:	C:h.swis
om.tcpbsd:	C:h.kernel
om.tcpbsd:	BaseLIB:h.debug
om.tcpbsd:	BaseLIB:h.error
om.tcpbsd:	C:h.kernel
om.tcpbsd:	BaseLIB:h.memory
om.tcpbsd:	BaseLIB:h.errorxxx
om.tcpbsd:	BaseLIB:h.nsetjmp
om.tcpbsd:	BaseLIB:h.memory
om.tcpbsd:	BaseLIB:h.thread
om.tcpbsd:	BaseLIB:h.tcp
om.thread:	c.thread
om.thread:	MemCheck:h.MemCheck
om.thread:	BaseLIB:h.nsetjmp
om.thread:	BaseLIB:h.debug
om.thread:	BaseLIB:h.error
om.thread:	C:h.kernel
om.thread:	BaseLIB:h.memory
om.thread:	BaseLIB:h.errorxxx
om.thread:	BaseLIB:h.nsetjmp
om.thread:	BaseLIB:h.memory
om.thread:	BaseLIB:h.time
om.thread:	BaseLIB:h.thread
om.time:	c.time
om.time:	C:h.kernel
om.time:	C:h.swis
om.time:	BaseLIB:h.time
o.blocked: s.blocked
o.blocked: h.SWINames
o.callback: s.callback
o.callback: h.SWINames
o.gethost_: s.gethost_
o.gethost_: h.RegNames
o.stack: s.stack
o.caller: s.caller
o.nsetjmp: s.nsetjmp
o32.debug:	c.debug
o32.debug:	BaseLIB:h.error
o32.debug:	C:h.kernel
o32.debug:	BaseLIB:h.memory
o32.debug:	BaseLIB:h.errorxxx
o32.debug:	BaseLIB:h.nsetjmp
o32.debug:	BaseLIB:h.memory
o32.debug:	BaseLIB:h.debug
o32.error:	c.error
o32.error:	C:h.kernel
o32.error:	C:h.swis
o32.error:	BaseLIB:h.error
o32.error:	C:h.kernel
o32.error:	BaseLIB:h.memory
o32.error:	BaseLIB:h.errorxxx
o32.error:	BaseLIB:h.nsetjmp
o32.error:	BaseLIB:h.memory
o32.gethost:	c.gethost
o32.gethost:	C:MemCheck.h.MemCheck
o32.gethost:	TCP32:h.inetlib
o32.gethost:	TCP32:sys.h.types
o32.gethost:	TCP32:sys.h.cdefs
o32.gethost:	TCP32:machine.h.endian
o32.gethost:	TCP32:machine.h.ansi
o32.gethost:	TCP32:machine.h.types
o32.gethost:	TCP32:netinet.h.in
o32.gethost:	TCP32:h.netdb
o32.gethost:	TCP32:sys.h.cdefs
o32.gethost:	TCP32:sys.h.types
o32.gethost:	TCP32:sys.h.socket
o32.gethost:	TCP32:sys.h.cdefs
o32.gethost:	h.gethost_
o32.gethost:	C:h.kernel
o32.memory:	c.memory
o32.memory:	MemCheck:h.MemCheck
o32.memory:	C:h.kernel
o32.memory:	C:h.swis
o32.memory:	BaseLIB:h.error
o32.memory:	C:h.kernel
o32.memory:	BaseLIB:h.memory
o32.memory:	BaseLIB:h.errorxxx
o32.memory:	BaseLIB:h.nsetjmp
o32.memory:	BaseLIB:h.memory
o32.strext:	c.strext
o32.strext:	BaseLIB:h.memory
o32.strext:	BaseLIB:h.strext
o32.tcpbsd:	c.tcpbsd
o32.tcpbsd:	MemCheck:h.MemCheck
o32.tcpbsd:	C:TCPIPLibs.h.errno
o32.tcpbsd:	TCP32:sys.h.errno
o32.tcpbsd:	C:h.kernel
o32.tcpbsd:	TCP32:h.socklib
o32.tcpbsd:	TCP32:sys.h.types
o32.tcpbsd:	TCP32:sys.h.cdefs
o32.tcpbsd:	TCP32:machine.h.endian
o32.tcpbsd:	TCP32:machine.h.ansi
o32.tcpbsd:	TCP32:machine.h.types
o32.tcpbsd:	TCP32:sys.h.socket
o32.tcpbsd:	TCP32:sys.h.cdefs
o32.tcpbsd:	TCP32:sys.h.stat
o32.tcpbsd:	TCP32:sys.h.time
o32.tcpbsd:	TCP32:sys.h.cdefs
o32.tcpbsd:	TCP32:sys.h.cdefs
o32.tcpbsd:	TCP32:sys.h.time
o32.tcpbsd:	TCP32:sys.h.uio
o32.tcpbsd:	TCP32:sys.h.cdefs
o32.tcpbsd:	C:h.kernel
o32.tcpbsd:	TCP32:sys.h.ioctl
o32.tcpbsd:	TCP32:sys.h.ttycom
o32.tcpbsd:	TCP32:sys.h.ioccom
o32.tcpbsd:	TCP32:sys.h.ioccom
o32.tcpbsd:	TCP32:sys.h.filio
o32.tcpbsd:	TCP32:sys.h.ioccom
o32.tcpbsd:	TCP32:sys.h.sockio
o32.tcpbsd:	TCP32:sys.h.ioccom
o32.tcpbsd:	TCP32:sys.h.cdefs
o32.tcpbsd:	TCP32:netinet.h.tcp
o32.tcpbsd:	TCP32:h.netdb
o32.tcpbsd:	TCP32:sys.h.cdefs
o32.tcpbsd:	TCP32:h.unixlib
o32.tcpbsd:	TCP32:h.inetlib
o32.tcpbsd:	TCP32:sys.h.types
o32.tcpbsd:	TCP32:netinet.h.in
o32.tcpbsd:	h.gethost
o32.tcpbsd:	C:h.swis
o32.tcpbsd:	C:h.kernel
o32.tcpbsd:	BaseLIB:h.debug
o32.tcpbsd:	BaseLIB:h.error
o32.tcpbsd:	C:h.kernel
o32.tcpbsd:	BaseLIB:h.memory
o32.tcpbsd:	BaseLIB:h.errorxxx
o32.tcpbsd:	BaseLIB:h.nsetjmp
o32.tcpbsd:	BaseLIB:h.memory
o32.tcpbsd:	BaseLIB:h.thread
o32.tcpbsd:	BaseLIB:h.tcp
o32.thread:	c.thread
o32.thread:	MemCheck:h.MemCheck
o32.thread:	BaseLIB:h.nsetjmp
o32.thread:	BaseLIB:h.debug
o32.thread:	BaseLIB:h.error
o32.thread:	C:h.kernel
o32.thread:	BaseLIB:h.memory
o32.thread:	BaseLIB:h.errorxxx
o32.thread:	BaseLIB:h.nsetjmp
o32.thread:	BaseLIB:h.memory
o32.thread:	BaseLIB:h.time
o32.thread:	BaseLIB:h.thread
o32.time:	c.time
o32.time:	C:h.kernel
o32.time:	C:h.swis
o32.time:	BaseLIB:h.time
om32.debug:	c.debug
om32.debug:	BaseLIB:h.error
om32.debug:	C:h.kernel
om32.debug:	BaseLIB:h.memory
om32.debug:	BaseLIB:h.errorxxx
om32.debug:	BaseLIB:h.nsetjmp
om32.debug:	BaseLIB:h.memory
om32.debug:	BaseLIB:h.debug
om32.error:	c.error
om32.error:	C:h.kernel
om32.error:	C:h.swis
om32.error:	BaseLIB:h.error
om32.error:	C:h.kernel
om32.error:	BaseLIB:h.memory
om32.error:	BaseLIB:h.errorxxx
om32.error:	BaseLIB:h.nsetjmp
om32.error:	BaseLIB:h.memory
om32.gethost:	c.gethost
om32.gethost:	C:MemCheck.h.MemCheck
om32.gethost:	TCP32:h.inetlib
om32.gethost:	TCP32:sys.h.types
om32.gethost:	TCP32:sys.h.cdefs
om32.gethost:	TCP32:machine.h.endian
om32.gethost:	TCP32:machine.h.ansi
om32.gethost:	TCP32:machine.h.types
om32.gethost:	TCP32:netinet.h.in
om32.gethost:	TCP32:h.netdb
om32.gethost:	TCP32:sys.h.cdefs
om32.gethost:	TCP32:sys.h.types
om32.gethost:	TCP32:sys.h.socket
om32.gethost:	TCP32:sys.h.cdefs
om32.gethost:	h.gethost_
om32.gethost:	C:h.kernel
om32.memory:	c.memory
om32.memory:	MemCheck:h.MemCheck
om32.memory:	C:h.kernel
om32.memory:	C:h.swis
om32.memory:	BaseLIB:h.error
om32.memory:	C:h.kernel
om32.memory:	BaseLIB:h.memory
om32.memory:	BaseLIB:h.errorxxx
om32.memory:	BaseLIB:h.nsetjmp
om32.memory:	BaseLIB:h.memory
om32.strext:	c.strext
om32.strext:	BaseLIB:h.memory
om32.strext:	BaseLIB:h.strext
om32.tcpbsd:	c.tcpbsd
om32.tcpbsd:	MemCheck:h.MemCheck
om32.tcpbsd:	C:TCPIPLibs.h.errno
om32.tcpbsd:	TCP32:sys.h.errno
om32.tcpbsd:	C:h.kernel
om32.tcpbsd:	TCP32:h.socklib
om32.tcpbsd:	TCP32:sys.h.types
om32.tcpbsd:	TCP32:sys.h.cdefs
om32.tcpbsd:	TCP32:machine.h.endian
om32.tcpbsd:	TCP32:machine.h.ansi
om32.tcpbsd:	TCP32:machine.h.types
om32.tcpbsd:	TCP32:sys.h.socket
om32.tcpbsd:	TCP32:sys.h.cdefs
om32.tcpbsd:	TCP32:sys.h.stat
om32.tcpbsd:	TCP32:sys.h.time
om32.tcpbsd:	TCP32:sys.h.cdefs
om32.tcpbsd:	TCP32:sys.h.cdefs
om32.tcpbsd:	TCP32:sys.h.time
om32.tcpbsd:	TCP32:sys.h.uio
om32.tcpbsd:	TCP32:sys.h.cdefs
om32.tcpbsd:	C:h.kernel
om32.tcpbsd:	TCP32:sys.h.ioctl
om32.tcpbsd:	TCP32:sys.h.ttycom
om32.tcpbsd:	TCP32:sys.h.ioccom
om32.tcpbsd:	TCP32:sys.h.ioccom
om32.tcpbsd:	TCP32:sys.h.filio
om32.tcpbsd:	TCP32:sys.h.ioccom
om32.tcpbsd:	TCP32:sys.h.sockio
om32.tcpbsd:	TCP32:sys.h.ioccom
om32.tcpbsd:	TCP32:sys.h.cdefs
om32.tcpbsd:	TCP32:netinet.h.tcp
om32.tcpbsd:	TCP32:h.netdb
om32.tcpbsd:	TCP32:sys.h.cdefs
om32.tcpbsd:	TCP32:h.unixlib
om32.tcpbsd:	TCP32:h.inetlib
om32.tcpbsd:	TCP32:sys.h.types
om32.tcpbsd:	TCP32:netinet.h.in
om32.tcpbsd:	h.gethost
om32.tcpbsd:	C:h.swis
om32.tcpbsd:	C:h.kernel
om32.tcpbsd:	BaseLIB:h.debug
om32.tcpbsd:	BaseLIB:h.error
om32.tcpbsd:	C:h.kernel
om32.tcpbsd:	BaseLIB:h.memory
om32.tcpbsd:	BaseLIB:h.errorxxx
om32.tcpbsd:	BaseLIB:h.nsetjmp
om32.tcpbsd:	BaseLIB:h.memory
om32.tcpbsd:	BaseLIB:h.thread
om32.tcpbsd:	BaseLIB:h.tcp
om32.thread:	c.thread
om32.thread:	MemCheck:h.MemCheck
om32.thread:	BaseLIB:h.nsetjmp
om32.thread:	BaseLIB:h.debug
om32.thread:	BaseLIB:h.error
om32.thread:	C:h.kernel
om32.thread:	BaseLIB:h.memory
om32.thread:	BaseLIB:h.errorxxx
om32.thread:	BaseLIB:h.nsetjmp
om32.thread:	BaseLIB:h.memory
om32.thread:	BaseLIB:h.time
om32.thread:	BaseLIB:h.thread
om32.time:	c.time
om32.time:	C:h.kernel
om32.time:	C:h.swis
om32.time:	BaseLIB:h.time
o32.blocked: s.blocked
o32.blocked: h.SWINames
