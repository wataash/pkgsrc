# $NetBSD: Makefile,v 1.19 2019/08/11 13:19:42 wiz Exp $

DISTNAME=	Lexical-SealRequireHints-0.011
PKGNAME=	p5-${DISTNAME}
PKGREVISION=	2
CATEGORIES=	devel perl5
MASTER_SITES=	http://search.cpan.org/CPAN/authors/id/Z/ZE/ZEFRAM/

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://metacpan.org/release/Lexical-SealRequireHints
COMMENT=	Perl5 module to prevent leakage of lexical hints
LICENSE=	${PERL5_LICENSE}

USE_LANGUAGES=		c
PERL5_PACKLIST=		auto/Lexical/SealRequireHints/.packlist
PERL5_MODULE_TYPE=	Module::Build

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
