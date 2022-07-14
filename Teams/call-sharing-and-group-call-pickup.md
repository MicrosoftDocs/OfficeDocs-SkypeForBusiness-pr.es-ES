---
title: Compartir llamadas y atender llamadas grupales
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: El uso compartido de llamadas y la recogida de llamadas grupales permiten a los usuarios compartir las llamadas entrantes con sus compañeros para que las llamadas se puedan realizar cuando el usuario no esté disponible.
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789955"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartir llamadas y atender llamadas grupales en Microsoft Teams

Las características de uso compartido de llamadas y recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con compañeros para que los compañeros puedan responder a las llamadas que se produzcan mientras el usuario no está disponible.

La recogida de llamadas grupales es menos perjudicial para los destinatarios que otras formas de uso compartido de llamadas (como desvío de llamadas o llamadas simultáneas) porque los usuarios pueden configurar cómo quieren recibir notificaciones de una llamada compartida entrante (a través de una notificación visual y de audio, solo visual o un banner en la aplicación Teams) y pueden decidir si quieren responder a ella.

Para compartir llamadas con otras personas, un usuario crea un grupo de llamadas y agrega a los usuarios con los que quieren compartir sus llamadas. A continuación, eligen una configuración de llamada simultánea o de reenvío. Consulte [Desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obtener más información. Ten en cuenta que los dispositivos móviles solo recibirán una notificación si están configurados para el banner y el tono.

> [!IMPORTANT]
> Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar en el modo de implementación Solo teams. Para obtener más información sobre los modos de implementación de Teams, consulte [Comprender Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licencia necesaria

Los usuarios deben tener asignada una licencia del sistema Teléfono Microsoft Teams para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales. Para obtener más información sobre el modelo de licencias, consulta [Esto es lo que obtienes con Phone System](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="configure-group-call-pickup"></a>Configurar la recogida de llamadas grupales

Para configurar la recogida de llamadas grupales, un usuario configura primero un grupo de llamadas (esto no es lo mismo que un grupo de seguridad o un grupo de Microsoft 365) y, a continuación, agrega los usuarios con los que quieren compartir sus llamadas. A continuación, eligen una configuración de llamada simultánea o desvío de llamadas. Para obtener más información y procedimientos paso a paso, consulte [Desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Las preferencias de notificación y creación de grupos de llamadas son características controladas por el usuario; los administradores no tienen que configurar estas características para sus usuarios. Los grupos de llamadas no se pueden crear a partir de grupos de seguridad ni de grupos de Microsoft 365; deben crearse en Teams.

Los administradores deben habilitar los grupos de llamadas a través de la configuración **de TeamsCallingPolicy AllowCallGroups** para un usuario. Los administradores también pueden habilitar esta opción a través del portal de Administración de Teams.  Además, el usuario configurado también puede configurar sus grupos de llamadas a través del cliente directamente. Administración o los usuarios finales no pueden bloquear la configuración entre sí, pero Teams Administración portal y el cliente de Teams deben mostrar esta relación con precisión en ambos lugares. 

Importante: Cuando los administradores desactivan los grupos de llamadas para los usuarios (una vez que se han activado y se han configurado las relaciones de grupo de llamadas), los administradores tienen que limpiar las relaciones de grupo de llamadas de los usuarios del centro de administración de Teams para evitar el enrutamiento incorrecto de llamadas. 

## <a name="limitations"></a>Limitaciones

Cada grupo de llamadas configurado puede tener un máximo de 25 usuarios o 32.768 caracteres. 

## <a name="more-information"></a>Más información

[Desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
