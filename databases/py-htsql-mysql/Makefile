# Created by: Kubilay Kocak <koobs@FreeBSD.org>
# $FreeBSD$

PORTNAME=	htsql-mysql
PORTVERSION=	2.3.3
PORTREVISION=	1
CATEGORIES=	databases python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	${PORTNAME:tu}-${PORTVERSION}

MAINTAINER=	koobs@FreeBSD.org
COMMENT=	Database Query Language (MySQL Backend for HTSQL)

LICENSE=	AGPLv3

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}htsql>2.3:databases/py-htsql@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}MySQLdb>0:databases/py-MySQLdb@${FLAVOR}

USES=		python:2
USE_PYTHON=	distutils autoplist

.include <bsd.port.mk>
