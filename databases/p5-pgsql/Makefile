# $OpenBSD: Makefile,v 1.13 2011/09/16 08:48:03 espie Exp $

SHARED_ONLY=	Yes

COMMENT=	access to PostgreSQL databases perl

VERSION=	1.9.0
DISTNAME=	pgsql_perl5-${VERSION}
PKGNAME=	p5-pgsql-${VERSION}
REVISION=	2
CATEGORIES=	databases perl5
MASTER_SITES=	${MASTER_SITE_PERL_CPAN:=Pg/}
USE_GROFF =	Yes

LIB_DEPENDS =	databases/postgresql
WANTLIB +=	pq>=3

MAINTAINER=	Markus Friedl <markus@openbsd.org>

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

CONFIGURE_ENV+=	POSTGRES_HOME="${LOCALBASE}" \
		POSTGRES_LIB="${LOCALBASE}/lib" \
		POSTGRES_INCLUDE="${LOCALBASE}/include/postgresql"

CONFIGURE_STYLE=perl

# needs a database properly set up
NO_REGRESS=	Yes

.include <bsd.port.mk>
