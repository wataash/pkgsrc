# $NetBSD: Makefile,v 1.95 2020/07/04 05:12:51 ryoon Exp $
#

TB_VER=		68.10.0
PKGNAME=	thunderbird-l10n-${TB_VER}
DISTNAME=	# empty
CATEGORIES=	mail
MASTER_SITES=	${MASTER_SITE_MOZILLA:=thunderbird/releases/${TB_VER}/linux-i686/xpi/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://www.mozillamessaging.com/en-US/thunderbird/
COMMENT=	Language packs for mail/thunderbird

SUPERSEDES+=	thunderbird60-l10n-[0-9]*

DEPENDS+=	thunderbird>=${PKGVERSION_NOREV}:../../mail/thunderbird

DIST_SUBDIR=	${PKGNAME_NOREV}
DISTFILES=	${XPI_FILES}

NO_BUILD=	yes

INSTALLATION_DIRS=	lib/thunderbird/extensions

TB_LOCALES=		ar ast be bg br ca cs cy		\
                        da de dsb el en-GB en-US es-AR es-ES et	\
                        eu fi fr fy-NL ga-IE gd gl he hr hsb	\
                        hy-AM hu id is it ja ko			\
                        lt nb-NO nl nn-NO pl 			\
                        pt-BR pt-PT rm ro ru si sk		\
                        sl sq sr sv-SE tr uk vi			\
                        zh-CN zh-TW

EXTENSIONS_DIR=		${PREFIX}/lib/thunderbird/extensions
XPI_FILES=		${TB_LOCALES:=.xpi}

do-install:
.for f in ${TB_LOCALES}
	${INSTALL_DATA} ${DISTDIR}/${DIST_SUBDIR}/${f}.xpi \
	${DESTDIR}${EXTENSIONS_DIR}/langpack-${f}@thunderbird.mozilla.org.xpi
.endfor

.include "../../mk/bsd.pkg.mk"
