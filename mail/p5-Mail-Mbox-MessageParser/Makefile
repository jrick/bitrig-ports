# $OpenBSD: Makefile,v 1.7 2010/12/03 11:45:39 ajacoutot Exp $

COMMENT=	fast and simple mbox folder reader

MODULES=	cpan
DISTNAME=	Mail-Mbox-MessageParser-1.5002
REVISION=	0
CATEGORIES=	mail
USE_GROFF =	Yes

MAINTAINER=	Giovanni Bechis <giovanni@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

BUILD_DEPENDS=	devel/p5-Benchmark-Timer \
		devel/p5-FileHandle-Unget
RUN_DEPENDS=	devel/p5-FileHandle-Unget \
		archivers/bzip2

REGRESS_DEPENDS=textproc/p5-Text-Diff

CONFIGURE_ARGS=	BZIP2=${LOCALBASE}/bin/bzip2

.include <bsd.port.mk>
