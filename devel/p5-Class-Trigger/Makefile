# $OpenBSD: Makefile,v 1.9 2010/12/03 11:44:28 ajacoutot Exp $

COMMENT=	add / call inheritable triggers

MODULES=	cpan
DISTNAME=	Class-Trigger-0.11
REVISION=	1
CATEGORIES=	devel
USE_GROFF =	Yes

# perl
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	devel/p5-Class-Data-Inheritable \
		devel/p5-IO-stringy

.include <bsd.port.mk>
