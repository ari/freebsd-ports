# Created by: Wen Heping <wenheping@gmail.com>
# $FreeBSD$

PORTNAME=	astLib
PORTVERSION=	0.9.2
CATEGORIES=	astro python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Astronomy modules for Python

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYNUMPY} \
		${PKGNAMEPREFIX}scipy>=0.7.0:science/py-scipy@${FLAVOR} \
		${PKGNAMEPREFIX}pillow>0:graphics/py-pillow@${FLAVOR} \
		${PKGNAMEPREFIX}pyfits>=1.1:astro/py-pyfits@${FLAVOR} \
		${PKGNAMEPREFIX}matplotlib>=0.98:math/py-matplotlib@${FLAVOR}
RUN_DEPENDS:=	${BUILD_DEPENDS}

PORTSCOUT=	skipv:0.15,0.17,0.17.1 # incorrect versioning upstream

USES=		python:2.7
USE_PYTHON=	autoplist distutils

post-install:
	${STRIP_CMD} ${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}/PyWCSTools/*.so

.include <bsd.port.mk>
