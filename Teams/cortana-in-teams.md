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
description: Obtenga información sobre cómo usar la asistencia de voz de Cortana con Teams
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
ms.openlocfilehash: 820689e2bcfa190afefda9d161c787c6be9a7da0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118479"
---
# <a name="cortana-voice-assistance-in-teams"></a>Asistencia de voz de Cortana en Teams

> [!Note]
> La asistencia de voz de Cortana es compatible con las aplicaciones móviles iOS y Android de Microsoft Teams, salas de Microsoft Teams en Windows y en pantallas de Microsoft Teams, solo para usuarios de Estados Unidos. Actualmente no está disponible para inquilinos de GCC, GCC-High, DoD, EDU. La expansión a idiomas y regiones adicionales se realizará como parte de futuras versiones.

> [!Note]
> La asistencia de voz de Cortana en salas de Microsoft Teams se publicó en Vista previa. En su versión preliminar, Cortana solo es compatible en EE. UU. con el idioma EN-EE. UU. en dispositivos que tienen micrófonos de Rally conectados.

La asistencia de voz de Cortana en la aplicación móvil de Teams, en salas de Microsoft Teams en Windows y en dispositivos de visualización de Microsoft Teams permite a los usuarios de Microsoft 365 Enterprise simplificar la comunicación, la colaboración y las tareas relacionadas con reuniones con el lenguaje natural hablado. Los usuarios pueden hablar con Cortana seleccionando el botón de micrófono situado en la esquina superior derecha de la aplicación móvil de Teams, o diciendo &#8220;Cortana&#8221; en el salón de Microsoft Teams o al usar una pantalla de Microsoft Teams. Para conectarse rápidamente con su equipo manos libres y mientras está en cualquier lugar, los usuarios pueden decir consultas como &#8220;llamar a Megan&#8221; o &#8220;enviar un mensaje a mi próxima reunión&#8221;. Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más. Estas experiencias de asistencia de voz se entregan con servicios de nivel empresarial de [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen completamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal como se reflejan en los Términos de servicios en línea [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

La imagen muestra el envío de un chat con Cortana en un dispositivo móvil.

![una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Control de administración y limitaciones

La asistencia de voz de Cortana en Teams se entrega con servicios que cumplen por completo las promesas de privacidad, seguridad y cumplimiento de Office 365 a nivel empresarial, tal como se reflejan en los Términos de servicios en línea (OST). La característica se habilitará de forma predeterminada para los inquilinos.

Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy). Esta directiva se puede establecer en un nivel de cuenta de usuario o en un nivel de inquilino. Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitado, habilitado solo con invocación de botón de inserción o también con invocación de palabra reactiva (aplicable a los dispositivos que lo admiten, como la presentación de Microsoft Teams).

Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta directiva (la directiva no está disponible actualmente en el Centro de administración de Microsoft Teams).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por ejemplo, el comando siguiente crea una nueva directiva con el nombre &#8220;EmployeeCortanaPolicy&#8221; donde la asistencia de voz de Cortana en Microsoft Teams está deshabilitada.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

En este ejemplo se muestra cómo actualizar una directiva existente con el nombre &#8220;EmployeeCortanaPolicy&#8221; y habilitar la asistencia de voz de Cortana en Microsoft Teams con solo invocación de botón de inserción. Los usuarios podrán invocar Cortana seleccionando el botón de micrófono Cortana en Teams. La invocación Desvía (&#8220;Hola Cortana&#8221; o &#8220;cortana&#8221;) se deshabilitará.  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

En este ejemplo se muestra la actualización de la directiva y la habilitación de la asistencia de voz de Cortana con el botón de activación y la invocación de palabras reactivas.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

En ese momento, de la versión inicial para los usuarios de Microsoft 365 Enterprise en ee. UU. en inglés, las funciones disponibles son las siguientes:

- La aplicación móvil de Teams no admite la activación de la palabra reactiva, pero será compatible en el futuro.  

- Microsoft Teams Rooms en dispositivos de pantalla de Windows y Microsoft Teams admitirá la activación de la palabra reactiva.

## <a name="user-control"></a>Control de usuario

Los usuarios individuales pueden probar la asistencia de voz de Cortana en diferentes dispositivos:

- Seleccione el botón del micrófono en la aplicación móvil de Teams.

- Seleccione el botón del micrófono o diga "Cortana" en Salas de Microsoft Teams.

- Diga "Cortana" en los dispositivos de visualización de Microsoft Teams.

Puede controlar si Cortana en Teams está habilitado para su dispositivo mediante una configuración en el dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Aplicación móvil de Teams o la pantalla de Microsoft Teams

  1. Abra la aplicación móvil de Teams.

  2. Seleccione **Configuración**  >  **Cortana**.

  3. Mueva el botón **de alternancia Activar** o **Desactivar.**

### <a name="microsoft-teams-display"></a>Pantalla de Microsoft Teams

  1. Vaya a la pantalla ambiente (inicio) de la pantalla de Microsoft Teams.

  2. Seleccione el avatar del usuario y, a continuación, **seleccione Configuración.** Si Cortana está habilitado, di "Cortana, ve a Configuración".

  3. Mueva el botón **de alternancia Activar** o **Desactivar.**
  
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

Para habilitar la asistencia de voz de Cortana durante una reunión, mueva el **botón de alternancia Activar** o **Desactivar**. Una vez que finalice la reunión, Cortana volverá a la configuración de nivel de dispositivo establecida.