# $NetBSD: Makefile,v 1.4 2020/07/03 20:41:36 nia Exp $

DISTNAME=	lua-arc4random-1.3.4
PKGNAME=	${DISTNAME:S/lua-/${LUA_PKGPREFIX}-/1}
CATEGORIES=	security lua
MASTER_SITES=	${MASTER_SITE_GITHUB:=mikejsavage/}
GITHUB_PROJECT=	lua-arc4random
GITHUB_TAG=	v1.3-4

MAINTAINER=	nia@NetBSD.org
HOMEPAGE=	https://github.com/mikejsavage/lua-arc4random
COMMENT=	Lua wrapper for arc4random(3)
LICENSE=	isc

USE_TOOLS+=	gmake

INSTALLATION_DIRS+=	${LUA_CDIR}

do-install:
	${INSTALL_LIB} ${WRKSRC}/arc4random.so ${DESTDIR}${PREFIX}/${LUA_CDIR}

.include "../../lang/lua/module.mk"
.include "../../mk/bsd.prefs.mk"
.if ${OPSYS} == "Linux" || ${OPSYS} == "SunOS"
.  include "../../security/openssl/buildlink3.mk"
.endif
.include "../../mk/bsd.pkg.mk"
