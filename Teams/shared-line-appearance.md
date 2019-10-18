---
title: Apariencia de línea compartida en Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
f1keywords:
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
ms.custom:
- Phone System
description: La apariencia de la línea compartida permite que el usuario elija un delegado para responder o controlar las llamadas en su nombre.
ms.openlocfilehash: aed55d29f2b9fc45c66040390d4d698acaf25258
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571763"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Apariencia de línea compartida en Microsoft Teams

La apariencia de la línea compartida forma parte de la característica de delegación que permite a un usuario elegir un delegado para responder o controlar las llamadas en su nombre. Esta característica es útil si un usuario tiene un asistente administrativo que controla regularmente las llamadas del usuario. En el contexto de la apariencia de línea compartida, un administrador es alguien que autoriza a un delegado a realizar o recibir llamadas en su nombre, y un delegado puede realizar y recibir llamadas en nombre de otra persona.

> [!IMPORTANT]
> Esta característica solo está disponible en el modo de implementación solo para equipos. Para obtener más información sobre los modos de implementación de Teams, consulte [comprender la coexistencia y la interoperabilidad de Microsoft Teams y Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licencia requerida

Un usuario debe ser un usuario de Enterprise Voice para ser delegado o configurar la delegación y permitir que otros usuarios realicen o reciban llamadas en su nombre.

Tanto los administradores como los delegados deben tener habilitada la telefonía IP empresarial. La experiencia de línea compartida es parte de la delegación y no requiere ninguna licencia adicional. Para obtener más información sobre el modelo de licencias, consulte [licencias de Office 365 para Microsoft Teams](office-365-licensing.md).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurar la delegación y la apariencia de las líneas compartidas

La delegación y la apariencia de la línea compartida son características dirigidas por el usuario: no hay ninguna configuración de administrador para configurar. Para obtener más información sobre cómo usar la característica, consulte [compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

El administrador de inquilinos puede habilitar la delegación a través de la opción de **TeamsCallingPolicy AllowDelegation** o a través del portal de administración de Teams para que esta característica funcione. 

El administrador de inquilinos también puede configurar las relaciones de delegación para un usuario en el centro de administración de Teams. Además, el usuario final también puede configurar sus relaciones de delegación directamente en Teams. El administrador de inquilinos o el usuario no pueden bloquear la configuración entre sí, pero el centro de administración de equipos y el cliente de equipos deberían mostrar esta relación con precisión en ambos lugares. 

> [!IMPORTANT]
> Cuando el administrador del inquilino desactiva la delegación para un usuario (después de que se ha activado), también necesita limpiar las relaciones de delegación de ese usuario en el centro de administración de equipos para evitar el enrutamiento incorrecto de las llamadas.

## <a name="shared-line-appearance-feature-availability"></a>Características de apariencia de línea compartida

La apariencia de línea compartida es compatible actualmente con las siguientes aplicaciones y dispositivos.

| Capacidades | Equipo de escritorio | Aplicación de equipos Mac | Teams Web App (Edge) |Teams Mobile iOS/aplicación para Android | Teléfono IP de Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar delegación | Sí  | Sí  | Sí | No | No |
| Recibir llamadas en nombre de otro | Sí  | Sí  | Sí  | Sí  | Sí |
| Llamar a un número de teléfono en nombre de otro | Sí  | Sí  | Sí  | Sí  | Sí |
| Llamar a un usuario de Teams en nombre de otro | Sí  | Sí  | Sí  | Sí  | Sí |
| Ver la vista de administrador de líneas compartidas | Sí  | Sí  | Sí | No | No |
| Ver la vista de administración de las actividades de llamadas de Manager | Sí  | Sí  | Sí | No | No |
| Ver la vista de administrador de delegados | Sí  | Sí  | Sí | No | No |
| El administrador o el administrador pueden retener o reanudar | Sí  | Sí  | Sí | No | No |

## <a name="limitations"></a>Algunas

Los administradores pueden agregar hasta 25 delegados y los delegados pueden tener hasta 25 administradores. No hay ningún límite en el número de relaciones de delegación que se pueden crear en un inquilino. 
 
Si los delegados y los delegados no se encuentran en la misma ubicación geográfica, es el proveedor de RTC quien permite que la identificación de llamadas se muestre desde una ubicación geográfica diferente para una llamada delegada (en nombre de). 
 
## <a name="more-information"></a>Más información

[Compartir una línea telefónica con un delegado](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
