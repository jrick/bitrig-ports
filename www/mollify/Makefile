# $OpenBSD: Makefile,v 1.6 2011/10/16 15:20:33 ajacoutot Exp $

COMMENT=	simple and clean multi-user web file manager

DISTNAME=	mollify_1.6.5.5
REVISION=	2
PKGNAME=	${DISTNAME:S/_/-/}
EXTRACT_SUFX=	.zip
CATEGORIES=	www

HOMEPAGE=	http://www.mollify.org/

# Eclipse Public License v1.0
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=	http://mollify.googlecode.com/files/

NO_BUILD=	Yes
NO_REGRESS=	Yes
PKG_ARCH=	*

PREFIX=		/var/www
INSTDIR=	${PREFIX}/htdocs/mollify
WRKDIST=	${WRKDIR}/mollify

SUBST_VARS=	INSTDIR

MODULES=	lang/php

do-install:
	${INSTALL_DATA_DIR} ${INSTDIR}
	cd ${WRKSRC} && pax -rw * ${INSTDIR}
	mv ${INSTDIR}/index.html ${INSTDIR}/index.html.dist
	touch ${INSTDIR}/backend/configuration.php.dist

.include <bsd.port.mk>
