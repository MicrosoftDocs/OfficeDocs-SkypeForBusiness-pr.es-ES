---
title: Compartir llamadas y atender llamadas grupales
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: El uso compartido de llamadas y la recogida de llamadas grupales permiten a los usuarios compartir llamadas entrantes con compañeros de trabajo para que las llamadas se puedan capturar cuando el usuario no esté disponible.
ms.openlocfilehash: 98094ff0b4b5d7b037915273b2c2730d42517c22
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717841"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartir llamadas y atender llamadas grupales en Microsoft Teams

Las características de uso compartido de llamadas y de recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con compañeros para que los compañeros puedan responder a las llamadas que se producen mientras el usuario no está disponible.

La recogida de llamadas grupales es menos perjudicial para los destinatarios que otras formas de uso compartido de llamadas (como el reenvío de llamadas o la llamada simultánea), ya que los usuarios pueden configurar cómo quieren que se les notifique de una llamada compartida entrante (a través de una notificación visual y de audio, solo visual o banner en la aplicación de Teams) y pueden decidir si la responden.

Para compartir llamadas con otros usuarios, un usuario crea un grupo de llamadas y agrega los usuarios con los que desea compartir sus llamadas. A continuación, eligen una configuración de llamada o reenvío simultánea. Vea [Reenvío de llamadas y llamada simultánea en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obtener más información. Ten en cuenta que los dispositivos móviles solo recibirán notificaciones si están configurados para banner y tono de llamada.

> [!IMPORTANT]
> Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar Teams modo de implementación solo. Para obtener más información sobre Teams de implementación, vea Comprender [Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licencia necesaria

Los usuarios deben tener asignada una Microsoft Teams Sistema telefónico para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales. Para obtener más información sobre el modelo de licencias, vea Esto es lo [que obtiene](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)con Sistema telefónico .

## <a name="configure-group-call-pickup"></a>Configurar la recogida de llamadas grupales

Para configurar la recogida de llamadas grupales, un usuario configura primero un grupo de llamadas (esto no es lo mismo que un grupo de seguridad o un grupo de Microsoft 365) y, a continuación, agrega los usuarios con los que desea compartir sus llamadas. Después, eligen una configuración de llamada simultánea o de reenvío de llamada. Para obtener más información y procedimientos paso a [paso,](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)vea Reenvío de llamadas y llamada simultánea en Teams .

Las preferencias de notificación y creación de grupos de llamadas son características controladas por el usuario; los administradores no tienen que configurar estas características para sus usuarios. Los grupos de llamadas no se pueden crear a partir de grupos de seguridad Microsoft 365 grupos; deben crearse en Teams.

Los administradores deben habilitar los grupos de llamadas a través de la configuración **TeamsCallingPolicy AllowCallGroups** para un usuario. Los administradores también pueden habilitar esta opción Teams portal de administración.  Además, el usuario configurado también puede configurar sus grupos de llamadas a través del cliente directamente. Los administradores o los usuarios finales no pueden bloquear la configuración entre sí, pero Teams portal de administración y Teams cliente deben mostrar esta relación con precisión en ambos lugares. 

Importante: Cuando los administradores desactivan los grupos de llamadas para los usuarios (después de que se haya activado y se hayan configurado las relaciones del grupo de llamadas), los administradores tienen que limpiar las relaciones de grupo de llamadas para los usuarios del centro de administración de Teams para evitar un enrutamiento incorrecto de llamadas. 

## <a name="limitations"></a>Limitaciones

Cada grupo de llamadas configurado puede tener un máximo de 25 usuarios o 32.768 caracteres. 

## <a name="more-information"></a>Más información

[Reenvío de llamadas y llamada simultánea en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
