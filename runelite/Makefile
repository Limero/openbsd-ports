COMMENT =	open source OldSchool RuneScape client

V =		2.6.1
DISTNAME =	RuneLite
PKGNAME =	runelite-${V}
REVISION =	1

MASTER_SITES =	https://github.com/runelite/launcher/releases/download/${V}/

CATEGORIES =	games

EXTRACT_ONLY =
EXTRACT_SUFX =	.jar

NO_BUILD =	Yes
NO_TEST =	Yes

MODULES =	java
MODJAVA_VER =	1.8+

# BSD 2-Clause
PERMIT_PACKAGE =	Yes

RUN_DEPENDS =	devel/desktop-file-utils \
		java/javaPathHelper \
		x11/gtk+3,-guic

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/icons/hicolor/128x128/apps/ \
		${PREFIX}/share/applications/ \
		${PREFIX}/share/java/classes/
	${SUBST_PROGRAM} ${FILESDIR}/runelite.png \
		${PREFIX}/share/icons/hicolor/128x128/apps/runelite.png
	${SUBST_PROGRAM} ${FILESDIR}/runelite.desktop \
		${PREFIX}/share/applications/runelite.desktop
	${SUBST_PROGRAM} ${FILESDIR}/runelite.sh \
		${PREFIX}/bin/runelite
	cp -r ${FULLDISTDIR}/${DISTNAME}${EXTRACT_SUFX} \
		${PREFIX}/share/java/classes/runelite.jar

.include <bsd.port.mk>
