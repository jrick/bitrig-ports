# $OpenBSD: Makefile,v 1.19 2012/06/15 08:30:20 ajacoutot Exp $

SHARED_ONLY=		Yes

COMMENT=		home media solution that allows easy media sharing

GNOME_PROJECT=		rygel
GNOME_VERSION=		0.14.2
REVISION=		1

CATEGORIES=		multimedia

HOMEPAGE=		http://live.gnome.org/Rygel

# LGPLv2.1
PERMIT_PACKAGE_CDROM= 	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB += GL X11 Xau Xcomposite Xcursor Xdamage Xdmcp Xext Xfixes
WANTLIB += Xi Xinerama Xrandr Xrender Xxf86vm atk-1.0 c cairo
WANTLIB += cairo-gobject drm e2fs-uuid expat ffi fontconfig freetype
WANTLIB += gdk-3 gdk_pixbuf-2.0 gee gio-2.0 glib-2.0 gmodule-2.0
WANTLIB += gobject-2.0 gssdp-1.0 gstapp-0.10 gstbase-0.10 gstpbutils-0.10
WANTLIB += gstreamer-0.10 gsttag-0.10 gstvideo-0.10 gthread-2.0
WANTLIB += gtk-3 gupnp-1.0 gupnp-av-1.0 gupnp-dlna-1.0 m orc-0.4
WANTLIB += pango-1.0 pangocairo-1.0 pangoft2-1.0 pcre pixman-1
WANTLIB += png pthread pthread-stubs soup-2.4 sqlite3 stdc++ unistring
WANTLIB += xcb xcb-render xcb-shm xml2 z

MODULES=		devel/gettext \
			x11/gnome

BUILD_DEPENDS=		net/gupnp/vala>=0.10.0
RUN_DEPENDS=		net/gupnp/vala>=0.10.0
LIB_DEPENDS=		converters/libunistring \
			devel/libgee06 \
			net/gupnp/av \
			net/gupnp/dlna \
			x11/gtk+3

MODGNOME_DESKTOP_FILE=	Yes
MODGNOME_ICON_CACHE=	Yes
MODGNOME_TOOLS= 	vala

LIBTOOL_FLAGS=		--tag=disable-static

CONFIGURE_ARGS+=	--disable-static \
			--enable-mpris-plugin \
			--enable-media-export-plugin \
			--enable-gst-launch-plugin \
			--enable-external-plugin \
			--enable-tracker-plugin \
			--disable-mediathek-plugin

FAKE_FLAGS+=		sysconfdir=${PREFIX}/share/examples/rygel/

.include <bsd.port.mk>
