# $OpenBSD: Makefile,v 1.29 2011/11/17 14:42:01 ajacoutot Exp $

COMMENT=	MS Word, Excel, Powerpoint ==> ASCII or TeX

DISTNAME=	catdoc-0.94.2
REVISION=	1
CATEGORIES=	textproc
MASTER_SITES=	http://ftp.wagner.pp.ru/pub/catdoc/

HOMEPAGE=	http://wagner.pp.ru/~vitus/software/catdoc/

MAINTAINER=	Jason Ish <ish@openbsd.org>

# GPL
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes
WANTLIB=		c m 

FLAVORS=	tk
FLAVOR?=

.if ${FLAVOR:L:Mtk}
RUN_DEPENDS=	x11/tk/8.4
.else
CONFIGURE_ARGS+=--disable-wordview
.endif

CONFIGURE_STYLE=gnu dest
USE_GROFF =	Yes

NO_REGRESS=	Yes

.include <bsd.port.mk>
