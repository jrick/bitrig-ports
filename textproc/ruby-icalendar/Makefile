# $OpenBSD: Makefile,v 1.10 2011/09/16 11:41:41 espie Exp $

COMMENT=		iCalendar support for Ruby

DISTNAME=		icalendar-1.1.0
REVISION =		4
CATEGORIES=		textproc

HOMEPAGE=		http://icalendar.rubyforge.org/

# Ruby license
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MODULES=		lang/ruby

CONFIGURE_STYLE=	ruby gem

MODRUBY_REGRESS=	rake

do-regress:
	@cd ${WRKDIST} && ${SETENV} TZ=GMT ${RAKE} test

.include <bsd.port.mk>
