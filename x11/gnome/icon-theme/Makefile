# $OpenBSD: Makefile,v 1.52 2012/06/15 08:30:19 ajacoutot Exp $

COMMENT=	base icon theme for GNOME

GNOME_PROJECT=	gnome-icon-theme
GNOME_VERSION=	3.4.0
REVISION=	0

CATEGORIES=	x11

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MODULES=	x11/gnome

BUILD_DEPENDS=	x11/icon-naming-utils>=0.8.90

# gtk-update-icon-cache is used at build time
BUILD_DEPENDS +=x11/gtk+2,-guic

# If we have svg icons without their png counterpart and librsvg is not
# part of the dependency chain then we explicitely add it.
# gnome-icon-theme is the inherited theme for most icon themes so we
# make sure we have gtk-update-icon-cache and can display svg icons.
MODGNOME_ICON_CACHE=	Yes
RUN_DEPENDS +=		x11/gnome/librsvg

PKG_ARCH=	*

USE_LIBTOOL=	No
CONFIGURE_ARGS=	--enable-icon-mapping \
		--disable-nls

EXAMPLEDIR=	${PREFIX}/share/examples/${GNOME_PROJECT}

post-install:
# Unbreak gtk+2 applications that use gnome-icon-theme, when 
# executed outside of a Desktop Environment
	${INSTALL_DATA_DIR} ${EXAMPLEDIR}/gtk-2.0
	@echo 'gtk-icon-theme-name = "gnome"' > \
		${EXAMPLEDIR}/gtk-2.0/gtkrc

.include <bsd.port.mk>
