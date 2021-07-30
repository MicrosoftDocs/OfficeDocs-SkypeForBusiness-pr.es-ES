---
title: Cortana de voz en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Obtenga información sobre cómo usar Cortana de voz con Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 368cb8b0c2d34e985d10adf11a405fb0603f1aff
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646421"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana de voz en Teams

> [!Note]
> Cortana de voz es compatible con las aplicaciones móviles de Microsoft Teams para iOS y Android y Microsoft Teams para usuarios de Estados Unidos, Reino Unido, Canadá, India y Australia. Salas de Microsoft Teams en Windows solo es compatible con los usuarios de Estados Unidos. Cortana asistencia de voz no está disponible actualmente para los inquilinos GCC, GCC-High, DoD y otros inquilinos edu. Cortana asistencia de voz en la Teams móvil ya está disponible para los clientes de EDU en Ee. UU. La expansión a idiomas y regiones adicionales se realizará como parte de futuras versiones.

> [!Note]
> Cortana asistencia de voz en Salas de Microsoft Teams se publicó en Vista previa. En su versión preliminar, Cortana solo se admite en los Estados Unidos con el idioma EN-EE. UU. en dispositivos que tienen micrófonos de Rally conectados.

Cortana de voz en la aplicación móvil de Teams, en Salas de Microsoft Teams en Windows y en dispositivos de visualización de Microsoft Teams permite Microsoft 365 Enterprise los usuarios simplificar las tareas relacionadas con la comunicación, la colaboración y las reuniones con el lenguaje natural hablado. Los usuarios pueden hablar con Cortana seleccionando el botón del micrófono situado en la esquina superior derecha de la aplicación móvil de Teams, o diciendo &#8220;Cortana&#8221; en la sala de Microsoft Teams o al usar una pantalla Microsoft Teams pantalla. Para conectarse rápidamente con su equipo manos libres y mientras está en cualquier lugar, los usuarios pueden decir consultas como &#8220;llamar a Megan&#8221; o &#8220;enviar un mensaje a mi próxima reunión&#8221;. Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más. Estas experiencias de asistencia de voz se entregan [Cortana con](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) servicios de nivel empresarial que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal y como se reflejan en los Términos de servicios en línea [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Control de administración y limitaciones

Cortana de voz en Teams se entrega con servicios que cumplen completamente con las promesas de privacidad, seguridad y cumplimiento de Office 365 nivel empresarial, tal como se reflejan en los Términos de servicios en línea (OST). La característica se habilitará de forma predeterminada para los inquilinos.

Los administradores de inquilinos pueden controlar quién en su espacio empresarial puede usar Cortana de voz en Teams una directiva (TeamsCortanaPolicy). Esta directiva se establece en un nivel de cuenta de usuario o de inquilino. Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitado, habilitado solo con la invocación de botón de inserción o también con la invocación de palabra reactiva (aplicable a los dispositivos que lo admiten, como la pantalla Microsoft Teams).

Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta directiva (la directiva no está disponible actualmente en Microsoft Teams centro de administración).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por ejemplo, el comando siguiente crea una nueva directiva con el nombre &#8220;EmployeeCortanaPolicy&#8221; donde Cortana de voz en Microsoft Teams está deshabilitado.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

En este ejemplo se muestra cómo actualizar una directiva existente con el nombre &#8220;EmployeeCortanaPolicy&#8221; y habilitar Cortana asistencia de voz en Microsoft Teams solo con invocación de botón. Los usuarios podrán invocar el Cortana seleccionando el Cortana de micrófono en Teams. Se deshabilitará &#8220;la invocación de Cortana&#8221; o &#8220;Cortana&#8221;).  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

En este ejemplo se muestra la actualización de la directiva y la habilitación Cortana de voz con el botón de activación y la invocación de palabras reactivas.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

En ese momento, de la versión inicial para Microsoft 365 Enterprise usuarios en ee. UU. en inglés, las siguientes son funciones disponibles:

- La Teams móvil no admite la activación de la palabra reactiva, pero será compatible en el futuro.  

- Salas de Microsoft Teams en Windows y Microsoft Teams dispositivos de visualización admitirán la activación de las palabras reactivas.

## <a name="user-control"></a>Control de usuario

Los usuarios individuales pueden Cortana asistencia de voz en diferentes dispositivos:

- Seleccione el botón del micrófono en la Teams móvil.

- Seleccione el botón del micrófono o diga "Cortana" en Salas de Microsoft Teams.

- Di "Cortana" en Microsoft Teams muestra dispositivos.

Puede controlar si Cortana en Teams está habilitado para el dispositivo mediante una configuración en el dispositivo.

![muestra la progresión de las ventanas móviles al habilitar Cortana](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salas de Microsoft Teams en Windows

Realizar cambios en el nivel de dispositivo está disponible si Cortana está habilitado en el nivel de inquilino. Cortana se liberará desactivado de forma predeterminada.

Para habilitar Cortana en el nivel de dispositivo, estos atributos XML deben agregarse en el archivo XML de SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Realizar cambios en el nivel de reunión está disponible si Cortana está habilitado en el nivel de dispositivo.

Para habilitar Cortana de voz durante una reunión, mueva el botón de alternancia **Activar** o **Desactivar**. Una vez que finalice la reunión, Cortana volverá a la configuración de nivel de dispositivo establecida.
