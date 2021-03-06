# $FreeBSD$

PORTNAME=	scli
DISTVERSIONPREFIX=	v
DISTVERSION=	0.2.1
PORTREVISION=	1
CATEGORIES=	net-im python

MAINTAINER=	0mp@FreeBSD.org
COMMENT=	Simple terminal user interface for the Signal messenger (using signal-cli)

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}urwid>=0:devel/py-urwid@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}urwid-readline>=0:devel/py-urwid-readline@${PY_FLAVOR} \
		signal-cli>=0.6.8_1:net-im/signal-cli

USES=		python:run,3.5+ shebangfix
USE_GITHUB=	yes
GH_ACCOUNT=	isamert
SHEBANG_FILES=	${PORTNAME}

NO_ARCH=	yes
NO_BUILD=	yes

PLIST_FILES=	bin/${PORTNAME}

PORTDOCS=	README.md screenshots/1.png screenshots/2.png screenshots/3.png

OPTIONS_DEFINE=	DOCS

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README.md ${STAGEDIR}${DOCSDIR}
	(cd ${WRKSRC} && ${COPYTREE_SHARE} screenshots ${STAGEDIR}${DOCSDIR})

.include <bsd.port.mk>
