#	$NetBSD: Makefile,v 1.8 2020/03/01 18:08:13 christos Exp $
#

.include <bsd.own.mk>

TESTSDIR=	${TESTSBASE}/dev/scsipi

TESTS_C=	t_cd

CPPFLAGS+=	-I${.CURDIR}/libscsitest -D_KERNTYPES

# kernel component required by test
SUBDIR=	libscsitest
SCSITESTDIR!= cd ${.CURDIR}/libscsitest && ${PRINTOBJDIR}
LDFLAGS+= -L${SCSITESTDIR}
LDADD+=	-Wl,--whole-archive -lrumpdev_scsitest -Wl,--no-whole-archive

LDADD+= -lrumpdev_scsipi -lrumpdev_disk -lrumpdev ${LIBRUMPBASE}
LDADD+=	-lutil

WARNS=	4

.include <bsd.test.mk>
