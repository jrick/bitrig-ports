# $OpenBSD: Makefile,v 1.24 2010/10/18 16:57:47 espie Exp $
# $FreeBSD: Makefile,v 1.2 1999/03/03 03:48:56 jkoshy Exp $

COMMENT=	self-scaling network benchmark

DISTNAME=	netpipe-2.4
DISTFILES=	NetPIPE_2.4.tar.gz
REVISION=	0
CATEGORIES=	benchmarks net

HOMEPAGE=	http://www.scl.ameslab.gov/netpipe/

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes
WANTLIB=		c

MASTER_SITES=	${HOMEPAGE}/code/

MAKE_FLAGS=	CC="${CC}" CFLAGS="${CFLAGS} -DHAVE_GETRUSAGE"
ALL_TARGET=	NPtcp
USE_GROFF =	Yes

NO_REGRESS=	Yes

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/NPtcp ${PREFIX}/bin
	${INSTALL_MAN} ${WRKBUILD}/netpipe.1 ${PREFIX}/man/man1
	cd ${PREFIX}/bin && ln -sf NPtcp netpipe
	
.include <bsd.port.mk>
