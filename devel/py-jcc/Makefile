# Created by: clsung@FreeBSD.org
# $FreeBSD$

PORTNAME=	jcc
PORTVERSION=	3.0
CATEGORIES=	devel java python
MASTER_SITES=	CHEESESHOP/source/J/JCC
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	JCC-${PORTVERSION}

MAINTAINER=	dbaio@FreeBSD.org
COMMENT=	C++ code generator for calling Java from C++/Python

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

BROKEN_armv6=		fails to link: /nxb-bin/usr/bin/ld: cannot find -ljava
BROKEN_armv7=		fails to link: /nxb-bin/usr/bin/ld: cannot find -ljava

USES=		python
USE_PYTHON=	distutils autoplist
PYDISTUTILS_PKGNAME=	JCC
USE_JAVA=	yes
JAVA_VERSION=	1.6+
JAVA_VENDOR=	openjdk

JCC_INCLUDES=	'${JAVA_HOME}/include;${JAVA_HOME}/include/freebsd'
JCC_CFLAGS=	'-fno-strict-aliasing;-pipe'
JCC_LFLAGS=	'-L${JAVA_HOME}/jre/lib/${ARCH};-ljava;-ljvm;-lverify;-L${JAVA_HOME}/jre/lib/${ARCH}/server;-L${JAVA_HOME}/jre/lib/${ARCH}/client;-Wl,-rpath=${JAVA_HOME}/jre/lib/${ARCH}:${JAVA_HOME}/jre/lib/${ARCH}/server:${JAVA_HOME}/jre/lib/${ARCH}/client'
JCC_DEBUG_CFLAGS=	"-O0 -g -DDEBUG"

MAKE_ENV+=	JCC_INCLUDES=${JCC_INCLUDES} JCC_CFLAGS=${JCC_CFLAGS} \
		JCC_LFLAGS=${JCC_LFLAGS} \
		JCC_JDK=${JAVA_HOME} \
		JCC_DEBUG_CFLAGS=${JCC_DEBUG_CFLAGS} \
		JCC_JAVADOC=${JAVADOC} \
		JCC_JAVAC=javac JCC_ARGSEP=";"

post-install:
	${STRIP_CMD} ${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}/jcc/_jcc${PYTHON_MAJOR_VER}.so

.include <bsd.port.mk>
