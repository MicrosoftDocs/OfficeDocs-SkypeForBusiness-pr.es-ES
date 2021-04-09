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
ms.openlocfilehash: 88c8d41eb0cf58413df995274bb9accd50b897c9
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637832"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartir llamadas y atender llamadas grupales en Microsoft Teams

Las características de uso compartido de llamadas y de recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con compañeros para que los compañeros puedan responder a las llamadas que se producen mientras el usuario no está disponible.

La recogida de llamadas grupales es menos perjudicial para los destinatarios que otras formas de uso compartido de llamadas (como el reenvío de llamadas o la llamada simultánea), ya que los usuarios pueden configurar cómo quieren que se les notifique de una llamada compartida entrante (a través de una notificación visual y de audio, solo visual o banner en la aplicación de Teams) y pueden decidir si la responden.

Para compartir llamadas con otros usuarios, un usuario crea un grupo de llamadas y agrega los usuarios con los que desea compartir sus llamadas. A continuación, eligen una configuración de llamada o reenvío simultánea. Vea [Reenvío de llamadas y llamada simultánea en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obtener más información. Ten en cuenta que los dispositivos móviles solo recibirán notificaciones si están configurados para banner y tono de llamada.

> [!IMPORTANT]
> Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar en modo de implementación solo de Teams. Para obtener más información sobre los modos de implementación de Teams, vea Comprender la coexistencia e [interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md) de Microsoft Teams y Skype Empresarial

## <a name="license-required"></a>Licencia necesaria

Se debe asignar a los usuarios una licencia de Microsoft Teams Phone System para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales. Para obtener más información sobre el modelo de licencias, vea [Esto es lo que obtiene con Sistema telefónico.](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)

## <a name="configure-group-call-pickup"></a>Configurar la recogida de llamadas grupales

Para configurar la recogida de llamadas grupales, un usuario configura primero un grupo de llamadas (esto no es lo mismo que un grupo de seguridad o un grupo de Microsoft 365) y, a continuación, agrega los usuarios con los que desea compartir sus llamadas. Después, eligen una configuración de llamada simultánea o de reenvío de llamada. Para obtener más información y procedimientos paso a paso, vea Reenvío de llamadas y llamada [simultánea en Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

Las preferencias de notificación y creación de grupos de llamadas son características controladas por el usuario; los administradores no tienen que configurar estas características para sus usuarios. Los grupos de llamadas no se pueden crear a partir de grupos de seguridad o grupos de Microsoft 365; deben crearse en Teams.

Los administradores deben habilitar los grupos de llamadas a través de la configuración **TeamsCallingPolicy AllowCallGroups** para un usuario. Los administradores también pueden habilitar esto a través del portal de administración de Teams.  Además, el usuario configurado también puede configurar sus grupos de llamadas a través del cliente directamente. Los administradores o los usuarios finales no pueden bloquear la configuración entre sí, pero el portal de administración de Teams y el cliente de Teams deben mostrar esta relación con precisión en ambos lugares. 

Importante: Cuando los administradores desactivan los grupos de llamadas para los usuarios (después de que se haya activado y se hayan configurado las relaciones del grupo de llamadas), los administradores tienen que limpiar las relaciones de grupo de llamadas para los usuarios del Centro de administración de Teams para evitar un enrutamiento incorrecto de llamadas. 

## <a name="limitations"></a>Limitaciones

Un espacio empresarial puede contener un máximo de 32.768 grupos de llamadas. Puede haber un máximo de 25 usuarios en cada grupo de llamadas. 

## <a name="more-information"></a>Más información

[Reenvío de llamadas y llamada simultánea en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
