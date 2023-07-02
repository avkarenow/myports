PORTNAME=	wp-cli
PORTVERSION=	2.8.1
CATEGORIES=	www
MASTER_SITES=	https://github.com/wp-cli/wp-cli/releases/download/v${DISTVERSION}/
PKGNAMESUFFIX=	${PHP_PKGNAMESUFFIX}
EXTRACT_SUFX=	.phar

MAINTAINER=	avkarenow@o2.pl
COMMENT=	Command line interface for WordPress
WWW=		https://wp-cli.org/

LICENSE=	MIT

USES=		php:cli,flavors
USE_PHP=	curl exif fileinfo ftp gd hash json mysqli pcre tokenizer xml zip zlib

NO_BUILD=	yes
NO_WRKSUBDIR=	yes
NO_ARCH=	yes

PLIST_FILES=	bin/wp bin/wp-cli.phar

do-extract:
	@${MKDIR} ${WRKSRC}/
	${CP} ${_DISTDIR}/wp-cli-${PORTVERSION}.phar ${WRKSRC}/wp-cli.phar

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/wp-cli.phar ${STAGEDIR}${PREFIX}/bin/
	${LN} -s wp-cli.phar ${STAGEDIR}${PREFIX}/bin/wp

.include <bsd.port.mk>
