# $OpenBSD: Makefile,v 1.36 2012/03/29 13:38:31 sthen Exp $
# Uses pthreads

COMMENT=	General Input Library (used by libggi)
DISTNAME=	libgii-0.9.0
REVISION =	3
SHARED_LIBS=	gg	0.9	\
		gii	0.9

CATEGORIES=	graphics

MAINTAINER=	Todd T. Fries <todd@openbsd.org>

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB=	X11 c m pthread xcb

MASTER_SITES=	http://www.ggi-project.org/ftp/ggi/v2.1/
EXTRACT_SUFX=	.src.tar.bz2

USE_GMAKE=	Yes
USE_LIBTOOL=	Yes
USE_GROFF =	Yes

CFLAGS+=	-pthread
SEPARATE_BUILD= Yes
CONFIGURE_STYLE= gnu
CONFIGURE_ARGS+= ${CONFIGURE_SHARED}
CONFIGURE_ARGS+= --enable-static --enable-mutexes="int"

CONFDIR=	${SYSCONFDIR}/ggi
SUBST_VARS=	CONFDIR

DOCS=	README

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/gii
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/gii
	cd ${WRKSRC}; ${INSTALL_DATA} ${DOCS} ${PREFIX}/share/doc/gii
	${INSTALL_DATA} ${WRKBUILD}/libgii.conf \
		${PREFIX}/share/examples/gii/libgii.conf.example
	${INSTALL_DATA} ${WRKDIST}/filter/mouse/mouse \
		${PREFIX}/share/examples/gii/filter_mouse.example
	${INSTALL_DATA} ${WRKDIST}/filter/keytrans/keytrans \
		${PREFIX}/share/examples/gii/filter_keytrans.example

.include <bsd.port.mk>
