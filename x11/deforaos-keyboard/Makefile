# $NetBSD: Makefile,v 1.25 2020/03/10 22:09:04 wiz Exp $
#

DISTNAME=	Keyboard-0.4.0
PKGNAME=	deforaos-keyboard-0.4.0
PKGREVISION=	2
CATEGORIES=	x11
MASTER_SITES=	https://ftp.defora.org/pub/DeforaOS/Apps/Desktop/src/Keyboard/

MAINTAINER=	khorben@defora.org
HOMEPAGE=	https://www.defora.org/
COMMENT=	DeforaOS desktop virtual keyboard

LICENSE=	2-clause-bsd

USE_TOOLS+=	pkg-config
USE_TOOLS+=	xgettext

MAKE_FLAGS+=	DESTDIR=${DESTDIR}
MAKE_FLAGS+=	PREFIX=${PREFIX}
MAKE_FLAGS+=	CFLAGS=${CFLAGS:Q}
MAKE_FLAGS+=	LDFLAGS=${LDFLAGS:Q}

.include "../../x11/libXtst/buildlink3.mk"
.include "../../x11/deforaos-libdesktop/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
