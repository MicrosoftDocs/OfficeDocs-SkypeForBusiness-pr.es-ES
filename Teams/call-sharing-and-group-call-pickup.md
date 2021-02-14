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
description: El uso compartido de llamadas y la recogida de llamadas grupales permiten a los usuarios compartir llamadas entrantes con colegas para que las llamadas se puedan capturar cuando el usuario no esté disponible.
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620731"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartir llamadas y atender llamadas grupales en Microsoft Teams

Las características de uso compartido de llamadas y recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con compañeros para que estos puedan responder a las llamadas que se producen mientras el usuario no está disponible.

La recogida de llamadas grupales es menos molesta para los destinatarios que otras formas de uso compartido de llamadas (como el reenvío de llamadas o las llamadas simultáneas) porque los usuarios pueden configurar cómo quieren que se les notifique sobre una llamada compartida entrante (a través de una notificación visual y de audio, solo visual o de banner en la aplicación Teams), y pueden decidir si responden.

Para compartir llamadas con otras personas, un usuario crea un grupo de llamadas y agrega los usuarios con los que desea compartir sus llamadas. A continuación, eligen una configuración de llamada simultánea o de reenvío. Consulte [El reenvío de llamadas y las llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) para obtener detalles. Ten en cuenta que los dispositivos móviles solo recibirán una notificación si están configurados para banner y tono.

> [!IMPORTANT]
> Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar en el modo de implementación Solo en Teams. Para obtener más información sobre los modos de implementación de Teams, consulte [Comprender la coexistencia](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e interoperabilidad de Microsoft Teams y Skype Empresarial

## <a name="license-required"></a>Licencia necesaria

Los usuarios deben estar Telefonía IP empresarial para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales. Para obtener más información sobre el modelo de licencias, consulte la [descripción del servicio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="configure-group-call-pickup"></a>Configurar la recogida de llamadas grupales

Para configurar la recogida de llamadas grupales, un usuario configura primero un grupo de llamadas (esto no es lo mismo que un grupo de seguridad o un grupo de Microsoft 365) y, a continuación, agrega a los usuarios con los que desea compartir las llamadas. A continuación, eligen una configuración de llamada simultánea o de reenvío de llamada. Para obtener más información y procedimientos paso a paso, vea El reenvío de llamadas y las llamadas [simultáneas en Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

Las preferencias de notificación y creación de grupos de llamadas son características controladas por el usuario; los administradores no tienen que configurar estas características para sus usuarios. Los grupos de llamadas no se pueden crear desde grupos de seguridad ni grupos de Microsoft 365; deben crearse en Teams.

Los administradores deben habilitar los grupos de llamadas a través de la configuración **TeamsCallingPolicy AllowCallGroups** para un usuario. Los administradores también pueden habilitar esta opción a través del Portal de administración de Teams.  Además, el usuario configurado también puede configurar sus grupos de llamadas directamente a través del cliente. El administrador o los usuarios finales no pueden bloquear la configuración entre sí, pero el Portal de administración de Teams y el cliente de Teams deben mostrar esta relación de forma precisa en ambos lugares. 

Importante: Cuando los administradores desactivan los grupos de llamadas para los usuarios (después de que se ha activado y las relaciones del grupo de llamadas están configuradas), los administradores tienen que limpiar las relaciones del grupo de llamadas para los usuarios en el centro de administración de Teams para evitar un enrutamiento de llamada incorrecto. 

## <a name="limitations"></a>Limitaciones

Un inquilino puede contener un máximo de 32.768 grupos de llamadas. Puede haber un máximo de 25 usuarios en cada grupo de llamadas. 

## <a name="more-information"></a>Más información

[Reenvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
