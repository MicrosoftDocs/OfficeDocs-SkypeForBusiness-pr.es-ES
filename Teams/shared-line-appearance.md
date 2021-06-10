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
description: Obtenga información sobre cómo enviar a los usuarios un correo electrónico con su información de audioconferencia en Microsoft Teams.
ms.openlocfilehash: b6a9e8dfba0db32eb4f02f1f4d4e9ea5f2c4be3e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117048"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Apariencia de línea compartida en Microsoft Teams

La apariencia de línea compartida forma parte de la característica de delegación que permite al usuario elegir un delegado para responder o administrar llamadas en su nombre. Esta característica es útil si un usuario tiene un asistente administrativo que controla periódicamente las llamadas del usuario. En el contexto de la apariencia de línea compartida, un administrador es alguien que autoriza a un delegado a realizar o recibir llamadas en su nombre, y un delegado puede realizar y recibir llamadas en nombre de otra persona.

> [!IMPORTANT]
> Esta característica solo está disponible en Teams de implementación solo. Para obtener más información sobre Teams de implementación, vea Comprender [Microsoft Teams y Skype Empresarial coexistencia e interoperabilidad](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licencia necesaria

Un usuario debe tener Sistema telefónico conectividad RTC (ya sea una licencia de Plan de llamadas o Direct Routing OnlineVoiceRoutingPolicy) para ser delegado o configurar una delegación y permitir que otros usuarios realicen o reciban llamadas en su nombre.

Tanto los administradores como los delegados deben tener Sistema telefónico con conectividad RTC (ya sea una licencia de Plan de llamadas o Direct Routing OnlineVoiceRoutingPolicy). La experiencia de línea compartida forma parte de la delegación y se incluye con Sistema telefónico. Para obtener más información sobre el modelo de licencias, [vea Microsoft Teams descripción del servicio](/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurar la delegación y la apariencia de la línea compartida

La delegación y la apariencia de línea compartida son características controladas por el usuario: no hay ninguna configuración de administrador que configurar. Para obtener información sobre cómo usar la característica, vea [Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

El administrador de inquilinos puede habilitar la delegación a través de la configuración **TeamsCallingPolicy AllowDelegation** o Teams Portal de administración para que esta característica funcione. 

El administrador de inquilinos también puede configurar relaciones de delegación para un usuario en el Teams de administración. Además, el usuario final también puede configurar sus relaciones de delegación directamente en Teams. El administrador de inquilinos o el usuario no pueden bloquear la configuración entre sí, pero el centro de administración de Teams y el cliente Teams deben mostrar esta relación con precisión en ambos lugares. 

> [!IMPORTANT]
> Cuando el administrador de inquilinos desactiva la delegación de un usuario (después de que se haya activado), también necesitan limpiar las relaciones de delegación para ese usuario en el centro de administración de Teams para evitar un enrutamiento de llamadas incorrecto.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidad de características de apariencia de línea compartida

La apariencia de línea compartida es compatible actualmente con las siguientes aplicaciones y dispositivos.

| Funcionalidad | Teams Escritorio | Teams Aplicación para Mac | Teams Web App (Edge) |Teams aplicación móvil iOS/Android | Teams Teléfono IP |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar la delegación | Sí | Sí | Sí | No | Sí |
| Recibir llamadas en nombre de otro usuario | Sí | Sí | Sí | Sí | Sí |
| Llamar a un número de teléfono en nombre de otro | Sí | Sí | Sí | Sí | Sí |
| Llamar a Teams usuario en nombre de otro usuario | Sí | Sí | Sí | Sí | Sí |
| Ver la vista de administrador de líneas compartidas | Sí | Sí | Sí | No | No |
| Ver la vista de administrador de las actividades de llamada del administrador | Sí | Sí | Sí | No | No |
| Ver la vista de administrador de delegados | Sí | Sí | Sí | No | No |
| Administrador o administrador puede retener o reanudar | Sí | Sí | Sí | No | No |

## <a name="limitations"></a>Limitaciones

Los administradores pueden sumar hasta 25 delegados y los delegados pueden tener hasta 25 administradores. No hay ningún límite para el número de relaciones de delegación que se pueden crear en un espacio empresarial. 
 
Si el delegado y el delegado no están en la misma ubicación geográfica, es el proveedor RTC quien permite que el identificador de llamada se muestre desde una ubicación geográfica diferente para una llamada delegada (en nombre de). 
 
## <a name="more-information"></a>Más información

[Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)