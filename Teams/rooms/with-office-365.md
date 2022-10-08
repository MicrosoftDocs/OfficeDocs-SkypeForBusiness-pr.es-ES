---
title: Crear cuentas de recursos para salas y dispositivos compartidos de Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este artículo para obtener información sobre cómo crear cuentas de recursos para salas y dispositivos compartidos, incluidos Salas de Microsoft Teams, Salas de Teams en Surface Hub y escritorio caliente en pantallas de Teams.
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475502"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Crear y configurar cuentas de recursos para salas y dispositivos compartidos de Teams

En este artículo se proporcionan pasos para crear cuentas de recursos para espacios compartidos y dispositivos, e incluye pasos para configurar cuentas de recursos para Salas de Microsoft Teams en Windows, Salas de Teams en Android, Salas de Teams en Surface Hub y pantallas de escritorio caliente en Teams.

Las cuentas de recursos de Microsoft 365 son cuentas de buzón y de Teams dedicadas a recursos específicos, como una sala o un proyector. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones con reglas que defina cuando se creen. Por ejemplo, si tiene un recurso común, como una sala de conferencias, puede configurar una cuenta de recursos para esa sala de conferencias que aceptará o rechazará automáticamente invitaciones a reuniones en función de su disponibilidad del calendario. 

Cada cuenta de recursos es única para una única instalación Salas de Microsoft Teams o teams muestra la implementación de escritorio rápido.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> Si usa paneles de Microsoft Teams, el Salas de Teams cuenta de recursos inicia sesión en Salas de Teams y en los paneles de Teams asociados.

> [!NOTE]
> **Skype Empresarial** <br><br>
> Si necesita habilitar la cuenta de recursos para que funcione con Skype Empresarial, vea [Implementar Salas de Microsoft Teams con Skype Empresarial Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Antes de empezar

### <a name="requirements"></a>Requirements

En función de su entorno, necesita uno o más roles para crear cuentas de recursos.

|**Ambiente**|**Roles necesarios**|
|-----|-----|
|Azure Active Directory  <br/> |Administrador global o administrador de usuarios  <br/> |
|Active Directory  <br/> |Los administradores de empresa de Active Directory, los administradores de dominio o tienen derechos delegados para crear usuarios. Derechos de sincronización de Azure Active Directory Connect.  <br/> |
|Exchange Online  <br/> |Administrador global o administrador de Exchange   <br/> |
|Exchange Server  <br/> |Administración de la organización de Exchange o Administración de destinatarios   <br/> |

Si está creando cuentas de recursos para Salas de Teams, el UPN debe coincidir con la dirección SMTP de la cuenta de recursos. Consulte [Salas de Microsoft Teams requisitos](requirements.md) antes de implementar Salas de Teams.

### <a name="what-license-do-you-need"></a>¿Qué licencia necesita?

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>Configurar las propiedades del buzón

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>Desactivar la expiración de la contraseña

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>Asignar una licencia de sala de reuniones

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>Pasos siguientes

### <a name="meeting-policies"></a>Directivas de reunión

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>Llamadas

No hay requisitos únicos para habilitar las llamadas con cuentas de recursos. Habilite la cuenta de recursos para llamar de la misma manera que habilita un usuario normal.

> [!NOTE]
> Se recomienda desactivar el correo de voz para dispositivos compartidos asignando una directiva de llamada a las cuentas de recursos de dispositivo. Consulte [Llamadas y desvío de llamadas en Teams](../teams-calling-policy.md) para obtener más información.

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>Artículos relacionados

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Licencias de Salas de Microsoft Teams](rooms-licensing.md)
