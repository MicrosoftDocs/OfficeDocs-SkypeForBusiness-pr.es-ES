---
title: 'Restricciones de llamadas salientes: Audioconferencia & llamadas RTC'
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Los administradores pueden controlar el tipo de audioconferencia y las llamadas RTC del usuario final que pueden realizar los usuarios.
ms.openlocfilehash: fd7dc24d7a920e5fb2c151600c3a6604381044e6
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674812"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restricción de llamadas salientes para Audioconferencia y las llamadas RTC de usuario

Como administrador, puede usar controles de llamadas salientes para restringir el tipo de audioconferencia y las llamadas de red telefónica conmutada (RTC) del usuario final que pueden realizar los usuarios de su organización.

Los controles de llamadas salientes se pueden aplicar por usuario o en función de inquilinos y proporcionan los dos siguientes controles para restringir independientemente cada tipo de llamadas salientes. De forma predeterminada, ambos controles están establecidos para permitir llamadas salientes nacionales e internacionales.

|Control|Descripción|Opciones de control|
|:-----|:-----|:-----|
|Audioconferencia llamadas RTC|Restringe el tipo de salida </br>llamadas que se permiten desde dentro de </br>reuniones organizadas por un usuario.|Cualquier destino (predeterminado)</br>En el mismo país o región que el organizador </br> Solo [países o regiones de la Zona A](audio-conferencing-zones.md) </br>No permitir|
|Llamadas RTC de usuario final|Restringe el tipo de llamadas </br>que puede realizar un usuario.|Internacionales y nacionales (predeterminado)</br>Nacionales</br>Ninguna|

Para averiguar qué países y regiones se consideran zona A, consulte [Zonas de país y región para Audioconferencia](audio-conferencing-zones.md).

   > [!NOTE]
   > Una llamada se considera nacional si el número marcado se encuentra en el mismo país donde se ha configurado Microsoft 365 o Office 365 para el organizador de la reunión (en el caso de las audioconferencias) o el usuario final (en el caso de las llamadas RTC del usuario final).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir las llamadas salientes de audioconferencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, seleccione **Usuarios** y, después, seleccione el nombre para mostrar del usuario en la lista de usuarios disponibles.

2. A continuación, vaya a **Audioconferencia** y seleccione **Editar**.

3. En **Llamar desde reuniones**, seleccione la opción de restricción de salida que desee.

4. Seleccione **Guardar**.

### <a name="using-powershell"></a>Con PowerShell

Las restricciones de llamadas salientes se controlan mediante una sola directiva denominada OnlineDialOutPolicy, que tiene un atributo de restricción para cada una. La directiva no se puede personalizar, en lugar de haber instancias de directiva predefinidas para cada combinación de la configuración.

Puede usar el cmdlet Get-CSOnlineDialOutPolicy para ver las directivas de llamadas salientes y usar el siguiente comando para la configuración.

**Establezca la directiva en un nivel por usuario con el siguiente cmdlet**. (El cmdlet Grant no contiene la palabra "Online" como lo hace el cmdlet Get).

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**Establezca la directiva en el nivel de inquilino con el siguiente cmdlet**.

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

Todos los usuarios del inquilino que no tengan asignada ninguna directiva de marcado recibirán esta directiva. Otros usuarios permanecen con su directiva actual.

**Compruebe la directiva actual en el nivel de inquilino con el siguiente cmdlet**.

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

En la tabla siguiente se proporciona información general sobre cada directiva.

|Cmdlet de PowerShell|Descripción|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario también puede realizar llamadas salientes a números nacionales e internacionales.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    El usuario de la conferencia solo puede llamar a números nacionales y este usuario puede realizar llamadas salientes a números nacionales e internacionales.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    El usuario de la conferencia no puede llamar. Este usuario puede realizar llamadas salientes a números nacionales e internacionales.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario solo puede realizar llamadas salientes a números RTC nacionales.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    El usuario de la conferencia puede llamar a números nacionales e internacionales, y este usuario no puede realizar llamadas salientes a números RTC además de números de emergencia.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    El usuario de la conferencia solo puede llamar a números nacionales y este usuario solo puede realizar llamadas salientes a números RTC nacionales.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    El usuario de la conferencia solo puede llamar a números nacionales y este usuario no puede realizar llamadas salientes a números RTC además de números de emergencia.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    El usuario de la conferencia no puede llamar y este usuario solo puede realizar llamadas salientes a números RTC nacionales.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    El usuario de la conferencia no puede llamar y este usuario no puede realizar llamadas salientes al número RTC además de los números de emergencia.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    El usuario de la conferencia solo puede llamar a [países y regiones de la zona A](audio-conferencing-zones.md), y este usuario puede realizar llamadas salientes a números nacionales e internacionales.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    El usuario de la conferencia solo puede llamar a [países y regiones de la zona A](audio-conferencing-zones.md), y este usuario solo puede realizar llamadas salientes a un número RTC nacional.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    El usuario de la conferencia solo puede llamar a [países y regiones de la zona A](audio-conferencing-zones.md), y este usuario no puede realizar llamadas salientes a números de RTC además de números de emergencia.    |
