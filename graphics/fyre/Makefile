# $OpenBSD: Makefile,v 1.21 2012/06/15 08:32:16 ajacoutot Exp $

COMMENT=		tool for producing computational artwork
DISTNAME=		fyre-1.0.1
REVISION=		12
CATEGORIES=		graphics

HOMEPAGE=		http://fyre.navi.cx/

# GPL
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM= Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB=	Half Iex IlmThread Imath X11 Xcomposite Xcursor \
		Xdamage Xext Xfixes Xi Xinerama Xrandr Xrender \
		atk-1.0 c cairo expat fontconfig freetype gdk-x11-2.0 \
		gdk_pixbuf-2.0 glib-2.0 gmodule-2.0 gobject-2.0 \
		gthread-2.0 gtk-x11-2.0 m pango-1.0 pangocairo-1.0 \
		pangoft2-1.0 pixman-1 png pthread stdc++ xml2 z gio-2.0 \
		pthread-stubs xcb glade-2.0 IlmImf>=4 gnet-2.0 \
		GL xcb-render xcb-shm

MASTER_SITES=		http://releases.navi.cx/fyre/ \
			http://distfiles.nl/

MODULES=		devel/gettext

BUILD_DEPENDS=		textproc/rarian
LIB_DEPENDS=		devel/libglade2 \
			graphics/openexr \
			net/gnet
RUN_DEPENDS=		misc/shared-mime-info \
			x11/gtk+2,-guic

USE_GMAKE=		Yes

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS= 	--enable-openexr \
			--enable-gnet

post-patch:
	@ln -s /usr/bin/true ${WRKDIR}/bin/update-mime-database

.include <bsd.port.mk>
