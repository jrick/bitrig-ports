# $OpenBSD: Makefile,v 1.6 2011/09/16 10:31:22 espie Exp $

COMMENT=	perl interface to the graphviz graphing tool

MODULES=	cpan
DISTNAME=	GraphViz-2.02
REVISION=	2
CATEGORIES=	math
USE_GROFF =	Yes

# perl
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	devel/p5-IPC-Run \
		devel/p5-Graph \
		math/graphviz \
		math/p5-Math-Bezier

.include <bsd.port.mk>
