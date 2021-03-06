# Created by: archfan <mail_me@riseup.net>
# $FreeBSD$

PORTNAME=	gtk-arc-themes
DISTVERSION=	20201013
CATEGORIES=	x11-themes

MAINTAINER=	Alexander88207@protonmail.com
COMMENT=	Arc-themes for GTK-2.0 and GTK-3.0 based desktop environments

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/COPYING

BUILD_DEPENDS=	inkscape:graphics/inkscape \
		optipng:graphics/optipng \
		sassc:textproc/sassc
RUN_DEPENDS=	gtk-murrine-engine>0:x11-themes/gtk-murrine-engine \
		gnome-themes-extra>0:x11-themes/gnome-themes-extra

USES=		autoreconf gmake gnome pkgconfig

USE_GITHUB=	yes
GH_ACCOUNT=	jnsh
GH_PROJECT=	arc-theme

GNU_CONFIGURE=	yes
USE_GNOME=	gtk20 gtk30
NO_ARCH=	yes

OPTIONS_DEFINE=	CINNAMON GNOMESHELL METACITY PLANK UNITY XFCE
OPTIONS_DEFAULT=	GNOMESHELL METACITY PLANK UNITY XFCE
OPTIONS_SUB=	yes

CINNAMON_BROKEN=	Current version of Cinnamon in ports is not supported.
CINNAMON_DESC=	Support for Cinnamon desktop environment
CINNAMON_IMPLIES=	METACITY
CINNAMON_CONFIGURE_ENABLE=	cinnamon
CINNAMON_BUILD_DEPENDS=	cinnamon>0:x11/cinnamon

GNOMESHELL_DESC=	Support for Gnome Shell
GNOMESHELL_CONFIGURE_ENABLE=	gnome-shell
GNOMESHELL_BUILD_DEPENDS=	gnome-shell:x11/gnome-shell

METACITY_DESC=	Support for Metacity window manager
METACITY_CONFIGURE_ENABLE=	metacity

PLANK_DESC=	Support for Plank dock
PLANK_CONFIGURE_ENABLE=	plank

UNITY_DESC=	Support for Unity desktop environment
UNITY_CONFIGURE_ENABLE=	unity

XFCE_DESC=	Support for Xfce desktop environment
XFCE_CONFIGURE_ENABLE=	xfwm

post-patch:
	${REINPLACE_CMD} -E 's|^(IconTheme=).*|\1Adwaita|; \
				s|^(CursorTheme=).*|\1Adwaita|' \
		${WRKSRC}/common/index/*/index.theme

.include <bsd.port.mk>
