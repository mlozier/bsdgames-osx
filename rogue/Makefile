#	@(#)Makefile	8.1 (Berkeley) 5/31/93
# $FreeBSD: src/games/rogue/Makefile,v 1.4.2.5 2002/08/07 16:31:42 ru Exp $
# $DragonFly: src/games/rogue/Makefile,v 1.5 2006/10/08 16:22:36 pavalos Exp $

PROG=	rogue
CFLAGS+=-DUNIX
SRCS=	hit.c init.c inventory.c level.c machdep.c main.c \
	message.c monster.c move.c object.c pack.c play.c random.c ring.c \
	room.c save.c score.c spec_hit.c throw.c trap.c use.c zap.c
DPADD=	${LIBCURSES}
LDADD=	-lcurses
HIDEGAME=hidegame
MAN=	rogue.6

beforeinstall:
.if !exists(${BINDIR})
	mkdir -p ${BINDIR}
.endif
.if !exists(${VARDIR})
	mkdir -p ${VARDIR}
.endif
.if !exists(${VARDIR}/rogue.scores)
	${INSTALL} -o ${BINOWN} -g ${BINGRP} -m 664 /dev/null \
	    ${VARDIR}/rogue.scores
.endif
.if !exists(${MANDIR}6)
	mkdir -p ${MANDIR}6
.endif

.include <bsd.prog.mk>
