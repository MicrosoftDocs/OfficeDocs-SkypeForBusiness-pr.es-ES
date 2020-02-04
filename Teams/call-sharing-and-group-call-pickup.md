---
title: Compartir llamadas y atender llamadas grupales en Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
ms.custom:
- Phone System
description: El uso compartido de llamadas y la recogida de llamadas de Grupo permiten a los usuarios compartir llamadas entrantes con colegas para que las llamadas se puedan capturar cuando el usuario no está disponible.
ms.openlocfilehash: a39ed0a606b38a159473fbab9c35d21ae461c34b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684123"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartir llamadas y atender llamadas grupales en Microsoft Teams

Las características uso compartido de llamadas y recogida de llamadas grupales de Microsoft Teams permiten a los usuarios compartir sus llamadas entrantes con colegas para que los colegas puedan responder a llamadas que se produzcan mientras el usuario no está disponible.

La recogida de llamadas grupales es menos disruptiva para los destinatarios que otras formas de uso compartido de llamadas (como el desvío de llamadas o el timbre simultáneo) porque los usuarios pueden configurar cómo desean recibir una notificación de una llamada compartida entrante (mediante una notificación de audio y vídeo, solo visual, o banner en la aplicación de Teams) y pueden decidir si desea contestarlos.

Para compartir llamadas con otras personas, un usuario crea un grupo de llamadas y agrega los usuarios con los que desean compartir sus llamadas. Luego, eligen una configuración de llamada simultánea o de reenvío. Para obtener más información [, consulta desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .

> [!IMPORTANT]
> Los usuarios, el propietario del grupo de llamadas y los miembros del grupo de llamadas deben estar en el modo de implementación solo de Teams. Para obtener más información sobre los modos de implementación de Teams, consulte [comprender la coexistencia y la interoperabilidad de Microsoft Teams y Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licencia requerida

Los usuarios deben tener habilitada la telefonía IP empresarial para configurar y usar el uso compartido de llamadas y la recogida de llamadas grupales. Para obtener más información sobre el modelo de licencias, consulte [licencias de Office 365 para Microsoft Teams](office-365-licensing.md).

## <a name="configure-group-call-pickup"></a>Configurar la recogida de llamadas grupales

Para configurar la recogida de llamadas grupales, un usuario configura primero un grupo de llamadas (no es lo mismo que un grupo de seguridad o un grupo de Office 365) y, a continuación, agrega los usuarios con los que desea compartir las llamadas. Después, eligen una configuración de llamadas simultáneas o de desvío de llamadas. Para obtener más información y procedimientos paso a paso, consulte [desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Las preferencias de notificación y creación de grupos de llamadas son características dirigidas por el usuario; los administradores no tienen que configurar estas características para sus usuarios. No se pueden crear grupos de llamadas a partir de grupos de seguridad o grupos de Office 365; se deben crear en Teams.

Los administradores deben habilitar los grupos de llamadas a través de la configuración de **TeamsCallingPolicy AllowCallGroups** para un usuario. Los administradores también pueden habilitar esta opción a través del portal de administración de Teams.  Además, el usuario configurado también puede configurar sus grupos de llamadas a través del cliente directamente. Los usuarios finales o administradores no pueden bloquear la configuración entre sí, pero el portal de administración de equipos y el cliente de equipos deberían mostrar esta relación con precisión en ambos lugares. 

Importante: cuando los administradores desactivan los grupos de llamadas para los usuarios (una vez que se ha activado y se han configurado las relaciones entre los grupos de llamadas), los administradores deben limpiar las relaciones de los usuarios en el centro de administración de Teams para evitar el enrutamiento incorrecto de las llamadas. 

## <a name="limitations"></a>Algunas

Un inquilino puede contener un máximo de 32.768 grupos de llamadas. Puede haber un máximo de 25 usuarios en cada grupo de llamadas. 

## <a name="more-information"></a>Más información

[Desvío de llamadas y llamadas simultáneas en Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
