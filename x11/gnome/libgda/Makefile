# $OpenBSD: Makefile,v 1.64 2012/06/15 08:30:20 ajacoutot Exp $

SHARED_ONLY=		Yes

COMMENT-main=		GNOME Data Access library
COMMENT-ldap=		LDAP backend for libgda
COMMENT-mysql=		MySQL backend for libgda
COMMENT-pgsql=		PostreSQL backend for libgda
COMMENT-ui=		GTK+ extension and tools for libgda

GNOME_PROJECT=		libgda
GNOME_VERSION=		5.0.3

# NOTE: when GDA_MAJOR changes, increment GDA_MAJOR accordingly and bump:
# x11/gnome/libgdamm
GDA_MAJOR=		${GNOME_VERSION:C/^([0-9]+\.[0-9]+).*/\1/}

PKGNAME-main=		${DISTNAME}
PKGNAME-ldap=		libgda-ldap-${GNOME_VERSION}
PKGNAME-mysql=		libgda-mysql-${GNOME_VERSION}
PKGNAME-pgsql=		libgda-pgsql-${GNOME_VERSION}
PKGNAME-ui=		libgda-ui-${GNOME_VERSION}

REVISION =		0
REVISION-ui=		3

EPOCH-main=		2
EPOCH-ldap=		0
EPOCH-mysql=		0
EPOCH-pgsql=		0

CATEGORIES=		databases

SHARED_LIBS +=  gda-5.0                   0.0 # 5.0
SHARED_LIBS +=  gda-report-5.0            0.0 # 5.0
SHARED_LIBS +=  gda-ui-5.0                0.0 # 5.0
SHARED_LIBS +=  gda-xslt-5.0              0.0 # 5.0

HOMEPAGE=		http://www.gnome-db.org/

# library: LGPLv2
# tools: GPLv2
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

WANTLIB += m pcre z gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0
WANTLIB += gthread-2.0 xml2 dbus-1 gcrypt gnome-keyring
WANTLIB += gpg-error ffi

MODULES=		devel/gettext \
			x11/gnome

MODGNOME_DESKTOP_FILE=	Yes
MODGNOME_ICON_CACHE=	Yes

SUBST_VARS=		GDA_MAJOR

# no no_ldap PSEUDO_FLAVOR because we need the headers in -main
# since some are referenced by other headers
PSEUDO_FLAVORS=		no_mysql no_pgsql no_ui
FLAVOR?=

MULTI_PACKAGES=		-main

LIB_DEPENDS=		devel/glib2 \
			textproc/libxml

BUILD_DEPENDS=		databases/db/v4

REGRESS_DEPENDS=	devel/check

# XXX check if still necessary when updating to >5.0.3:
# vala should be added but this tarball misses a few needed files
MODGNOME_TOOLS= 	goi yelp

LIBTOOL_FLAGS=		--tag=disable-static
USE_GROFF =		Yes
CONFIGURE_ARGS+=	--disable-static \
			--enable-system-sqlite \
			--with-bdb="${LOCALBASE}" \
			--without-firebird \
			--without-oracle \
			--without-mdb \
			--with-java=no
MODGNOME_CPPFLAGS=	-I${LOCALBASE}/include/db4/
MODGNOME_LDFLAGS=	-lm
CONFIGURE_ENV=		LIBCRYPTO_CFLAGS="-I/usr/include/ssl" \
			LIBCRYPTO_LIBS="-lcrypto" \
			MYSQL_CONFIG="${LOCALBASE}/bin/mysql_config"

FAKE_FLAGS=		configdir="${PREFIX}/share/examples/libgda"

WANTLIB-main += ${WANTLIB} c gcrypt gpg-error ncurses pthread
WANTLIB-main += readline soup-2.4 crypto gdk_pixbuf-2.0 png xslt

RUN_DEPENDS-main=	${MODGETTEXT_RUN_DEPENDS} \
			${MODGNOME_RUN_DEPENDS_yelp}
LIB_DEPENDS-main=	${LIB_DEPENDS} \
			devel/libsoup \
			textproc/libxslt \
			x11/gnome/libgnome-keyring \
			graphics/gdk-pixbuf2 \
			x11/dbus

.if ${FLAVOR:L:Mno_ui}
CONFIGURE_ARGS+=	--without-ui
.else
MULTI_PACKAGES+=	-ui
CONFIGURE_ARGS+=	--with-ui
# XXX graphviz depends on deprecated libgnomeui
CONFIGURE_ARGS+=	--with-graphviz=no
WANTLIB-ui += ${WANTLIB}
WANTLIB-ui += GL X11 Xau Xcomposite Xcursor Xdamage Xdmcp Xext Xfixes
WANTLIB-ui += Xi Xinerama Xrandr Xrender Xxf86vm atk-1.0 c cairo
WANTLIB-ui += cairo-gobject drm expat fontconfig freetype gda-5.0
WANTLIB-ui += gdk-3 gdk_pixbuf-2.0 goocanvas-2.0 gtk-3 gtksourceview-3.0
WANTLIB-ui += pango-1.0 pangocairo-1.0 pangoft2-1.0 pixman-1 png
WANTLIB-ui += pthread pthread-stubs xcb xcb-render xcb-shm stdc++
LIB_DEPENDS-ui=		${LIB_DEPENDS} \
			x11/gnome/libgda \
			x11/gtksourceview3 \
			graphics/goocanvas2
.endif

.if ${FLAVOR:L:Mno_mysql}
CONFIGURE_ARGS+=	--without-mysql
.else
RUN_DEPENDS-mysql=	${MODGETTEXT_RUN_DEPENDS}
MULTI_PACKAGES+=	-mysql
WANTLIB-mysql=		${WANTLIB} crypto ssl gda-${GDA_MAJOR} \
			mysqlclient
LIB_DEPENDS-mysql=	${LIB_DEPENDS} \
			x11/gnome/libgda \
			databases/mysql
CONFIGURE_ARGS+=	--with-mysql="${LOCALBASE}"
.endif

.if ${FLAVOR:L:Mno_pgsql}
CONFIGURE_ARGS+=	--without-postgres
.else
RUN_DEPENDS-pgsql=	${MODGETTEXT_RUN_DEPENDS}
MULTI_PACKAGES+=	-pgsql
WANTLIB-pgsql=		${WANTLIB} gda-${GDA_MAJOR} pq com_err crypto ssl
LIB_DEPENDS-pgsql=	${LIB_DEPENDS} \
			x11/gnome/libgda \
			databases/postgresql
CONFIGURE_ARGS+=	--with-postgres="${LOCALBASE}"
.endif

# ldap (no PSEUDO_FLAVORS, see above)
RUN_DEPENDS-ldap=	${MODGETTEXT_RUN_DEPENDS}
MULTI_PACKAGES+=	-ldap
WANTLIB-ldap=		${WANTLIB} crypto gda-${GDA_MAJOR} gssapi krb5 lber-2.4 \
			ldap-2.4 sasl2 ssl asn1 com_err
LIB_DEPENDS-ldap=	x11/gnome/libgda \
			databases/openldap
CONFIGURE_ARGS+=	--with-ldap

# XXX sync LIBdb_VERSION with databases/db/v4
LIBdb_VERSION=	5.0
SUBST_VARS+=	LIBdb_VERSION
pre-configure:
	${SUBST_CMD} ${WRKSRC}/configure

.include <bsd.port.mk>
