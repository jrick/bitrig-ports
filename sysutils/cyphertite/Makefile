# $OpenBSD: Makefile,v 1.16 2012/05/09 14:36:15 ajacoutot Exp $

COMMENT =		tar-like secure remote deduplicating archiver

DISTNAME =		cyphertite-1.2.2
CATEGORIES =		sysutils archivers security

HOMEPAGE =		https://www.cyphertite.com/
MAINTAINER =		David Hill <dhill@mindcry.org>

# ISC
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

WANTLIB =		assl>=4 c clog crypto curl edit event_core expat \
			exude>=2 ncurses pthread shrink>=2 sqlite3 ssl util \
			xmlsd>=2

MASTER_SITES =		https://opensource.conformal.com/snapshots/cyphertite/

LIB_DEPENDS =		archivers/libshrink>=0.5.0	\
			devel/libclog>=0.6.0		\
			devel/libevent2			\
			devel/libexude>=0.7.0		\
			net/curl			\
			security/assl>=1.0.0		\
			textproc/libxmlsd>=0.8.0

NO_REGRESS =		Yes

FAKE_FLAGS=		MANDIR=${PREFIX}/man/man

.include <bsd.port.mk>
