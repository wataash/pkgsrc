# $NetBSD: Makefile,v 1.40 2019/08/11 13:21:52 wiz Exp $

DISTNAME=		udunits-1.12.1
PKGREVISION=		12
CATEGORIES=		math devel
MASTER_SITES=		ftp://ftp.unidata.ucar.edu/pub/udunits/
EXTRACT_SUFX=		.tar.Z

MAINTAINER=		pkgsrc-users@NetBSD.org
HOMEPAGE=		https://www.unidata.ucar.edu/software/udunits/
COMMENT=		Library and program for manipulating units of physical quantities

MAKE_JOBS_SAFE=		no

USE_TOOLS+=		perl soelim
WRKSRC=			${WRKDIR}/${PKGNAME_NOREV}/src

GNU_CONFIGURE=		yes
CONFIGURE_ARGS+=	--sysconfdir=${PKG_SYSCONFDIR:Q}

CPPFLAGS+=		-Df2cFortran -Dunix
PERL5_CONFIGURE=	no
PERL5_PACKLIST=		auto/UDUNITS/.packlist

EGDIR=			${PREFIX}/share/examples/udunits
CONF_FILES=		${EGDIR}/udunits.dat ${PKG_SYSCONFDIR}/udunits.dat

INSTALL_MAKE_FLAGS+=	MANDIR=${DESTDIR}${PREFIX}/${PKGMANDIR} \
			BINDIR=${DESTDIR}${PREFIX}/bin \
			INCDIR=${DESTDIR}${PREFIX}/include \
			LIBDIR=${DESTDIR}${PREFIX}/lib

post-install:
	${RM} -rf ${WRKSRC}/perl/blib/lib

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
