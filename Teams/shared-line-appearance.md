---
title: Apariencia de línea compartida en Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
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
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Obtenga información sobre cómo enviar a los usuarios un correo electrónico con su información sobre las audioconferencias en Microsoft Teams.
ms.openlocfilehash: 7750f85e959f332832c24b60b4efafd784218f61
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583839"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Apariencia de línea compartida en Microsoft Teams

La apariencia de las líneas compartidas forma parte de la característica de delegación que permite al usuario elegir un delegado para responder o administrar llamadas en su nombre. Esta característica es útil si un usuario tiene un asistente administrativo que se encarga periódicamente de las llamadas del usuario. En el contexto de la apariencia de las líneas compartidas, un jefe es alguien que autoriza a un delegado a realizar o recibir llamadas en su nombre, y un delegado puede realizar y recibir llamadas en nombre de otra persona.

> [!IMPORTANT]
> Esta característica solo está disponible en el modo de implementación solo de Teams. Para obtener más información sobre los modos de implementación de Teams, consulte [Comprender la coexistencia](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e interoperabilidad de Microsoft Teams y Skype Empresarial

## <a name="license-required"></a>Licencia necesaria

Un usuario debe tener Sistema telefónico con conectividad RTC (ya sea una licencia de plan de llamadas o Enrutamiento directo OnlineVoiceRoutingPolicy) para ser delegado o configurar la delegación y permitir que otros usuarios realicen o reciban llamadas en su nombre.

Tanto los administradores como los delegados necesitan tener Sistema telefónico con conectividad RTC (ya sea una licencia de plan de llamadas o Direct Routing OnlineVoiceRoutingPolicy). La experiencia de línea compartida forma parte de la delegación y se incluye con Sistema telefónico. Para obtener más información sobre el modelo de licencias, vea la [descripción del servicio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurar la delegación y el aspecto de las líneas compartidas

La delegación y la apariencia de la línea compartida son características controladas por el usuario: no hay configuraciones de administrador para configurar. Para obtener información sobre cómo usar la característica, vea [Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

El administrador de inquilinos puede habilitar la delegación a través **de la configuración TeamsCallingPolicy AllowDelegation** o del portal de administración de Teams para que esta característica funcione. 

El administrador de inquilinos también puede configurar relaciones de delegación para un usuario en el Centro de administración de Teams. Además, el usuario final también puede configurar sus relaciones de delegación directamente en Teams. El administrador de inquilinos o el usuario no pueden bloquear la configuración entre sí, pero el centro de administración de Teams y el cliente de Teams deben mostrar esta relación con precisión en ambos lugares. 

> [!IMPORTANT]
> Cuando el administrador de inquilinos desactiva la delegación de un usuario (después de que se ha activado), también debe limpiar las relaciones de delegación para ese usuario en el Centro de administración de Teams para evitar un enrutamiento de llamadas incorrecto.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidad de características de apariencia de línea compartida

La apariencia de las líneas compartidas es compatible actualmente con las siguientes aplicaciones y dispositivos.

| Funcionalidad | Teams para escritorio | Aplicación Teams para Mac | Teams Web App (Edge) |Aplicación móvil de Teams para iOS/Android | Teléfono IP de Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar delegación | Sí | Sí | Sí | No | Sí |
| Recibir llamadas en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Llamar a un número de teléfono en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Llamar a un usuario de Teams en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Ver la vista de administrador de líneas compartidas | Sí | Sí | Sí | No | No |
| Ver la vista de administrador de las actividades de llamada del director | Sí | Sí | Sí | No | No |
| Ver la vista de administrador de delegados | Sí | Sí | Sí | No | No |
| El administrador puede retener o reanudar | Sí | Sí | Sí | No | No |

## <a name="limitations"></a>Limitaciones

Los administradores pueden agregar hasta 25 delegados y los delegados pueden tener hasta 25 administradores. No hay ningún límite en el número de relaciones de delegación que se pueden crear en un espacio empresarial. 
 
Si el delegado y el delegado no están en la misma ubicación geográfica, será el proveedor de RTC quien permita que el identificador de llamada se muestre desde una ubicación geográfica diferente para una llamada delegada (en nombre de). 
 
## <a name="more-information"></a>Más información

[Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
