---
title: Configurar y administrar la moderación del canal
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo configurar canales para la moderación en Microsoft Teams, incluido cómo agregar miembros del equipo como moderadores de canal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52fb88d6371c033713c5b14d96ecf2a9211420b0
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562369"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurar y administrar la moderación de canales en Microsoft Teams

En Microsoft Teams, los propietarios de equipos pueden activar la moderación de un canal estándar para controlar quién puede iniciar nuevas publicaciones y responder a las publicaciones de ese canal.

Los propietarios de equipos también pueden agregar miembros del equipo como moderadores. Es posible que el propietario de un equipo no tenga la experiencia en la materia en el nivel de canal para admitir mejor la moderación del canal. Al permitir que determinados miembros del equipo moderen un canal, la responsabilidad de administrar el contenido y el contexto dentro de un canal se comparte entre los propietarios del equipo y los moderadores de canales. Por ejemplo, un propietario de equipo puede agregar propietarios de empresa o propietarios de contenido como moderadores, lo que les permite controlar el uso compartido de información en ese canal.

> [!NOTE]
> La moderación de canales está disponible para los canales estándar. No está disponible para el canal General ni para canales privados o compartidos.

## <a name="what-can-a-channel-moderator-do"></a>¿Qué puede hacer un moderador de canal?

Los moderadores de canal pueden:

- Iniciar nuevas publicaciones en el canal. Cuando la moderación está activada en un canal, solo los moderadores pueden iniciar nuevas publicaciones en ese canal.
- Agregue y quite miembros del equipo como moderadores a un canal. Tenga en cuenta que, de forma predeterminada, los propietarios de equipos son moderadores de canal y no se pueden quitar.
- Controlar si los miembros del equipo pueden responder a los mensajes existentes del canal y si los bots y conectores pueden enviar mensajes de canal.

## <a name="scenarios"></a>Escenarios

Estos son algunos ejemplos de cómo su organización puede usar la moderación de canal en Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Usar un canal como canal de anuncios

El equipo de marketing usa un canal específico para compartir los anuncios y entregas clave del proyecto. A veces, los miembros del equipo publican contenido en el canal que pertenece más adecuadamente a otros canales. El propietario del equipo quiere restringir el uso compartido de información en el canal a solo los anuncios para que los miembros del equipo puedan usar ese canal para mantenerse al tanto de lo que es importante.

En este escenario, el propietario del equipo agrega clientes potenciales de marketing como moderadores para que puedan publicar anuncios en el canal y desactiva la posibilidad de que los miembros del equipo respondan a los mensajes de ese canal.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Usar un canal para las discusiones de clase en Teams para Educación

En Teams para Educación, un profesor de ciencias quiere usar un canal para involucrar a los alumnos en discusiones centradas en temas específicos del aula.

En este escenario, el profesor permite a sus profesores asistentes moderar el canal. Los profesores asistentes pueden entonces crear nuevas publicaciones para iniciar e impulsar discusiones con los alumnos.

## <a name="manage-channel-moderation"></a>Administrar la moderación del canal

En Teams, vaya al canal, haga clic en **Más opciones...** >  **Administrar canal**. Desde aquí puede activar y desactivar la moderación, agregar miembros del equipo como moderadores y establecer preferencias.

La moderación del canal es una configuración por canal. No hay ninguna configuración a nivel de inquilino para la moderación del canal. Si desea que agreguemos una configuración de moderación de canal a nivel de inquilino, solicitelo en el [Portal de comentarios de Teams](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![preferencias para administrar los equipos con moderación de canal.](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Activar o desactivar la moderación para un canal

De forma predeterminada, la moderación está desactivada, lo que significa que la configuración de canal habitual se aplica a los propietarios del equipo y a los miembros del equipo. Por ejemplo, puede restringir las nuevas publicaciones a solo los miembros del equipo o permitir que todos, incluidos los invitados, puedan iniciar nuevas publicaciones.

Para activar la moderación de un canal, en **Moderación** de canal, haga clic en **Activado**. Cuando la moderación del canal está activada, solo los moderadores pueden iniciar nuevas publicaciones. 

### <a name="add-or-remove-channel-moderators"></a>Agregar o quitar moderadores de canales

En **¿Quiénes son los moderadores?**, haga clic en **Administrar** y, a continuación, agregue o quite miembros del equipo como moderadores. Los propietarios y moderadores de equipos pueden agregar y quitar otros moderadores.  

### <a name="set-team-member-permissions"></a>Establecer permisos de miembros del equipo

En **Permisos de los miembros del equipo**, active las casillas junto a las actividades que desea permitir.

## <a name="related-topics"></a>Temas relacionados

- [Información general de los equipos y canales en Microsoft Teams](teams-channels-overview.md)
