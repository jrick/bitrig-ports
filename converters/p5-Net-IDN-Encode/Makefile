# $OpenBSD: Makefile,v 1.6 2010/12/03 11:44:23 ajacoutot Exp $

SHARED_ONLY=	Yes

COMMENT=	Internationalizing Domain Names in Applications

DISTNAME=	Net-IDN-Encode-1.100
REVISION=	1
CATEGORIES=	net converters

# perl
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

MODULES=		cpan

CONFIGURE_STYLE=	modbuild
USE_GROFF =	Yes

RUN_DEPENDS=	converters/p5-Net-IDN-Nameprep>=1.100
REGRESS_DEPENDS=devel/p5-Test-NoWarnings

.include <bsd.port.mk>
