# $NetBSD: Makefile,v 1.11 2020/01/26 05:26:15 rillig Exp $

DISTNAME=	bwa-0.7.17
CATEGORIES=	biology
PKGREVISION=	3
GITHUB_TAG=	v${PKGVERSION_NOREV}
MASTER_SITES=	${MASTER_SITE_GITHUB:=lh3/}

MAINTAINER=	bacon@NetBSD.org
HOMEPAGE=	http://bio-bwa.sourceforge.net/
COMMENT=	Map low-divergent sequences against a large reference genome
LICENSE=	gnu-gpl-v3

USE_TOOLS+=	perl:run gmake
REPLACE_PERL=	*.pl

INSTALLATION_DIRS=	bin ${PKGMANDIR}/man1

# unconditionally uses <emmintrin.h>
ONLY_FOR_PLATFORM=	*-*-x86_64 *-*-i386 *-*-ia64

CFLAGS.SunOS+=	-Du_int32_t=uint32_t
LDFLAGS.SunOS+=	-lsocket -lnsl

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bwa ${DESTDIR}${PREFIX}/bin
	${INSTALL_SCRIPT} ${WRKSRC}/*.pl ${DESTDIR}${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/*.1 ${DESTDIR}${PREFIX}/${PKGMANDIR}/man1

.include "../../devel/zlib/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
