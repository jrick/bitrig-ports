# $OpenBSD: Makefile,v 1.10 2012/01/26 12:04:00 sthen Exp $

COMMENT =		perl module to generate random data

DISTNAME =		Data-Random-0.06

CATEGORIES =		devel

MAINTAINER =		Alexander Bluhm <bluhm@openbsd.org>

# perl
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

MODULES =		cpan
BUILD_DEPENDS =		devel/p5-YAML-Tiny
REGRESS_DEPENDS =	devel/p5-Date-Calc \
			graphics/p5-GD

.include <bsd.port.mk>
