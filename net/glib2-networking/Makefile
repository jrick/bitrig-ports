# $OpenBSD: Makefile,v 1.16 2012/05/15 14:02:46 ajacoutot Exp $

SHARED_ONLY=	Yes

COMMENT=	network-related gio modules for glib2

GNOME_VERSION=	2.32.3
GNOME_PROJECT=	glib-networking

PKGNAME=	glib2-networking-${GNOME_VERSION}

REVISION=	0

CATEGORIES=	net

HOMEPAGE=	http://www.gtk.org/

MAINTAINER=	Antoine Jacoutot <ajacoutot@openbsd.org>

# GLPLv2
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB += c ffi gio-2.0 glib-2.0 gmodule-2.0 gmp gnutls gobject-2.0
WANTLIB += gthread-2.0 hogweed m nettle p11-kit pcre proxy pthread
WANTLIB += stdc++ tasn1 z

MODULES=	devel/gettext \
		x11/gnome

BUILD_DEPENDS=	devel/gsettings-desktop-schemas
RUN_DEPENDS=	devel/gsettings-desktop-schemas

LIB_DEPENDS=	net/libproxy>=0.4.6 \
		security/gnutls \
		devel/glib2>=2.32.0

LIBTOOL_FLAGS=	--tag=disable-static

CONFIGURE_STYLE=gnu
CONFIGURE_ARGS=	--disable-static \
		--with-ca-certificates=/etc/ssl/cert.pem

REGRESS_IS_INTERACTIVE=	x11

.include <bsd.port.mk>
