# $OpenBSD: Makefile,v 1.11 2010/11/20 09:48:38 espie Exp $

COMMENT=		tool for synchronizing PalmOS devices

DISTNAME=		coldsync-3.0-pre4
PKGNAME=		coldsync-3.0pre4
REVISION=		2
CATEGORIES=		palm comms

MASTER_SITES=		http://www.coldsync.org/download/

# artistic
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB=		c stdc++ m

MODULES=		devel/gettext
CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS=		--without-usb --without-libusb
USE_GROFF =		Yes

# DESTDIR bugs the fake process, so make sure it does not get set
DESTDIRNAME=		none
FAKE_FLAGS=		INFODIR=${WRKINST}${PREFIX}/info \
			MANDIR=${WRKINST}${PREFIX}/man

.include <bsd.port.mk>
