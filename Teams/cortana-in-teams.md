---
title: Asistencia de voz de Cortana en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Obtener información sobre cómo usar el asistente de voz Cortana con Teams
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
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686446"
---
# <a name="cortana-voice-assistance-in-teams"></a>Asistencia de voz de Cortana en Teams

> [!Note]
> La asistencia de voz de Cortana se admite en las aplicaciones móviles para iOS y Android de Microsoft Teams, salas de Microsoft Teams en Windows y en pantallas de Microsoft Teams, solo para los usuarios de Estados Unidos. No está disponible actualmente para inquilinos de GCC, GCC-High, DoD, EDU. La expansión a idiomas y regiones adicionales se realizará como parte de las futuras versiones.

> [!Note]
> La asistencia de voz de Cortana en salas de Microsoft Teams se ofrece en versión preliminar. En su versión preliminar, Cortana solo es compatible en EE. UU. con idioma EN-US en dispositivos que tienen micrófonos Móviles conectados.

La asistencia de voz de Cortana en la aplicación móvil de Teams, en Salas de Microsoft Teams en Windows y en los dispositivos de visualización de Microsoft Teams permite a los usuarios de Microsoft 365 Enterprise simplificar la comunicación, la colaboración y las tareas relacionadas con las reuniones usando lenguaje natural hablado. Los usuarios pueden hablar con Cortana seleccionando el botón del micrófono situado en la esquina superior derecha de la aplicación móvil de Teams o diciendo &#8220;Cortana&#8221; en la sala de Microsoft Teams o cuando se usa una pantalla de Microsoft Teams. Para conectarse rápidamente con el equipo manos libres y mientras está fuera, los usuarios pueden decir consultas como &#8220;llamar&#8221; O &#8220;enviar un mensaje a mi próxima reunión&#8221;. Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar asistencia de voz para compartir archivos, comprobar su calendario y mucho más. Estas experiencias de asistencia de voz se entregan con servicios de nivel empresarial de [Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen completamente las promesas de privacidad, seguridad y cumplimiento de Office 365, tal y como se reflejan en los Términos de servicios en línea [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

La imagen muestra cómo enviar un chat con Cortana en un dispositivo móvil.

![Una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Control de administración y limitaciones

La asistencia de voz de Cortana en Teams se entrega con servicios que cumplen completamente las promesas de cumplimiento, seguridad y privacidad de nivel empresarial de Office 365, tal y como se reflejan en los Términos de servicios en línea (OST). La característica se habilitará de forma predeterminada para los inquilinos.

Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy). Esta directiva se puede establecer en un nivel de cuenta de usuario o en el nivel de inquilino. Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitada, habilitada solo con invocación de botón rápido o con la invocación de activar palabra también (aplicable a los dispositivos que la admiten, como la presentación de Microsoft Teams).

Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta directiva (la directiva no está disponible actualmente en el Centro de administración de Microsoft Teams).

- [New-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por ejemplo, el comando siguiente crea una nueva directiva con el nombre &#8220;EmployeeCortanaPolicy&#8221; donde se deshabilita la asistencia de voz de Cortana en Microsoft Teams.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

En este ejemplo se muestra cómo actualizar una directiva existente con el nombre &#8220;EmployeeCortanaPolicy&#8221; y habilitar la asistencia de voz de Cortana en Microsoft Teams solo con invocación de botones de comando. Los usuarios podrán invocar Cortana seleccionando el botón de micrófono Cortana en Teams. La invocación de reactivación (&#8220;Hola Cortana&#8221; o &#8220;cortana&#8221;) se deshabilitará.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

En este ejemplo se muestra cómo actualizar la directiva y habilitar la asistencia de voz de Cortana con el botón de presionar y reactivar la invocación de palabras.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

En el momento de la versión inicial para los usuarios de Microsoft 365 Enterprise en Estados Unidos en inglés, las siguientes son funciones disponibles:

- La aplicación móvil de Teams no admite la activación de Word, pero será compatible en el futuro.  

- Los salas de Microsoft Teams en windows y los dispositivos de visualización de Microsoft Teams admitirán la activación de Word.

## <a name="user-control"></a>Control de usuario

Los usuarios individuales pueden probar la asistencia de voz de Cortana en diferentes dispositivos:

- Seleccione el botón del micrófono en la aplicación móvil de Teams.

- Seleccione el botón del micrófono o diga "Cortana" en salas de Microsoft Teams.

- Di "Cortana" en los dispositivos de visualización de Microsoft Teams.

Puede controlar si Cortana en Teams está habilitada para su dispositivo mediante una configuración en el dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Aplicación móvil de Teams o la pantalla de Microsoft Teams

  1. Abra la aplicación móvil de Teams.

  2. Selecciona **Configuración**  >  **cortana.**

  3. Mueva el botón **de alternancia para activarlo** o **desactivarlo.**

### <a name="microsoft-teams-display"></a>Pantalla de Microsoft Teams

  1. Vaya a la pantalla ambiente (principal) de la pantalla de Microsoft Teams.

  2. Selecciona el avatar del usuario y, a continuación, selecciona **Configuración.** Si Cortana está habilitada, di "Cortana, ve a Configuración".

  3. Mueva el botón **de alternancia para activarlo** o **desactivarlo.**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Salas de Microsoft Teams en Windows

La realización de cambios en el nivel del dispositivo está disponible si Cortana está habilitada en el nivel de inquilino. Cortana se desactivará de forma predeterminada.

Para habilitar Cortana en el nivel del dispositivo, estos atributos XML deben agregarse al archivo XML de SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

La realización de cambios en el nivel de reunión está disponible si Cortana está habilitada en el nivel del dispositivo.

Para habilitar la asistencia de voz de Cortana durante una reunión, activa **o** desactiva el botón de **alternancia.** Una vez que finaliza la reunión, Cortana vuelve a la configuración de nivel de dispositivo establecida.
