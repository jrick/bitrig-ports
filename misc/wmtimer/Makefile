# $OpenBSD: Makefile,v 1.29 2011/09/16 10:31:23 espie Exp $

COMMENT=		wm-dockapp; alarm clock

DISTNAME=		wmtimer-2.92
REVISION=		2
CATEGORIES=		misc x11 x11/windowmaker

HOMEPAGE=		http://www.darkops.net/wmtimer/

MAINTAINER=		Peter Stromberg <wilfried@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=		${HOMEPAGE}

MODULES=		devel/gettext

WANTLIB += X11 Xau Xcomposite Xcursor Xdamage Xdmcp Xext Xfixes
WANTLIB += Xi Xinerama Xpm Xrandr Xrender atk-1.0 c cairo expat
WANTLIB += fontconfig freetype gio-2.0 glib-2.0 gmodule-2.0
WANTLIB += gobject-2.0 m pango-1.0 pangocairo-1.0 pangoft2-1.0
WANTLIB += pixman-1 png pthread pthread-stubs xcb z gdk_pixbuf-2.0
WANTLIB += gdk-x11-2.0 gtk-x11-2.0

LIB_DEPENDS=		x11/gtk+2

NO_REGRESS=		Yes

WRKSRC=			${WRKDIST}/wmtimer

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/wmtimer ${PREFIX}/bin

.include <bsd.port.mk>
