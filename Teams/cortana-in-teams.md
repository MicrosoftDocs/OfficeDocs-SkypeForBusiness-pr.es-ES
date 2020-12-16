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
description: Más información sobre cómo usar la asistencia de voz de Cortana con Teams
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
> La asistencia de voz de Cortana es compatible con las aplicaciones móviles iOS y Android de Microsoft Teams, las salas de Microsoft Teams en Windows y Microsoft Teams muestra, solo para los usuarios de los Estados Unidos. Actualmente no está disponible para los inquilinos GCC, GCC-High, DoD, EDU. La expansión de las regiones y los idiomas adicionales se realizará como parte de las versiones futuras.

> [!Note]
> La asistencia de voz de Cortana en Microsoft Team salas está publicada en vista previa. En su versión preliminar, Cortana solo se admite en los Estados Unidos con el idioma en-es en los dispositivos que han conectado micrófonos Rally.

La asistencia de voz de Cortana en la aplicación móvil de Microsoft Teams, en salas de Microsoft Teams en Windows, y en los dispositivos de visualización de Microsoft Teams permite a los usuarios de Microsoft 365 Enterprise optimizar la comunicación, la colaboración y las tareas relacionadas con la reunión usando el lenguaje natural hablado. Los usuarios pueden hablar con Cortana seleccionando el botón de micrófono situado en la esquina superior derecha de la aplicación móvil de Teams o diciendo &#8220;Cortana&#8221; en la sala de Microsoft Teams o al usar una presentación de Microsoft Teams. Para conectarse rápidamente con sus manos libres de su equipo y mientras se desplazan, los usuarios pueden decir consultas como &#8220;llamar a Nuria&#8221; o &#8220;enviar un mensaje a la próxima reunión&#8221;. Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más. Estas experiencias de asistencia por voz se proporcionan con los [servicios de calidad empresarial de Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal como se refleja en las condiciones de los [servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

La imagen muestra el envío de una conversación con Cortana en un dispositivo móvil.

![una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Control y limitaciones de administración

La asistencia de voz de Cortana en Teams se ofrece con servicios que cumplen con las promesas de privacidad, seguridad y cumplimiento normativo de Office 365, tal como se refleja en las condiciones de los servicios en línea (OST). La característica se habilitará de forma predeterminada para los inquilinos.

Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy). Esta Directiva se puede establecer a nivel de cuenta de usuario o nivel de inquilino. Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitada, habilitada solo con la invocación del botón de comando o con la invocación de reactivación de Word (aplicable a los dispositivos que lo admiten, como la pantalla de Microsoft Teams).

Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta Directiva (la Directiva no está disponible en este momento en el centro de administración de Microsoft Teams).

- [Nuevo: CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por ejemplo, el siguiente comando crea una nueva directiva con el nombre &#8220;EmployeeCortanaPolicy&#8221; donde la asistencia de voz Cortana en Microsoft Teams está deshabilitada.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

En este ejemplo se muestra cómo actualizar una directiva existente con nombre &#8220;EmployeeCortanaPolicy&#8221; y habilitar la asistencia de voz de Cortana en Microsoft Teams solo con la llamada del botón de comando. Los usuarios podrán invocar a Cortana seleccionando el botón de micrófono de Cortana en Teams. Activar Word (&#8220;se deshabilitará la invocación de Cortana&#8221; o &#8220;Cortana&#8221;).  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

En este ejemplo se muestra cómo actualizar la Directiva y habilitar la asistencia de voz de Cortana con la llamada de activación de Word y el botón Insertar.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

En el momento, la versión inicial para los usuarios de Microsoft 365 Enterprise en Estados Unidos en inglés, las siguientes son funciones disponibles:

- La aplicación móvil de Teams no admitirá la activación de la aplicación para activar Word, pero será compatible en el futuro.  

- Salas de Microsoft Teams en Windows y Microsoft Teams los dispositivos de visualización admitirán la activación de la activación de Word.

## <a name="user-control"></a>Control de usuario

Los usuarios individuales pueden probar la asistencia de voz de Cortana en diferentes dispositivos:

- Seleccione el botón micrófono en la aplicación móvil de Teams.

- Seleccione el botón micrófono o diga "Cortana" en salas de Microsoft Teams.

- Di "Cortana" en dispositivos de visualización de Microsoft Teams.

Puede controlar si Cortana de Teams está habilitada para el dispositivo mediante una configuración en el dispositivo.

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>La aplicación móvil de Teams o la pantalla de Microsoft Teams

  1. Abra la aplicación móvil de Teams.

  2. Seleccione **configuración**  >  **Cortana**.

  3. Activar o **desactivar** el botón **de** alternancia.

### <a name="microsoft-teams-display"></a>Pantalla de Microsoft Teams

  1. Vaya a la pantalla ambiente (Inicio) de la pantalla de Microsoft Teams.

  2. Seleccione el avatar del usuario y, a continuación, seleccione **configuración**. Si Cortana está habilitada, diga "Cortana, ir a configuración".

  3. Activar o **desactivar** el botón **de** alternancia.
  
### <a name="microsoft-teams-rooms-on-windows"></a>Salas de Microsoft Teams en Windows

La realización de cambios en el nivel de dispositivo está disponible si Cortana está habilitada en el nivel de inquilino. Cortana se desactivará de forma predeterminada.

Para habilitar Cortana en el nivel de dispositivo, estos atributos XML deben agregarse en el archivo XML SkypeSettings:

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

Puede realizar cambios en el nivel de reunión si Cortana está habilitada en el nivel del dispositivo.

Para habilitar la asistencia de voz de Cortana durante una reunión, mueva el botón **de alternancia a activado** o **desactivado**. Una vez finalizada la reunión, Cortana vuelve a la configuración de nivel de dispositivo establecida.
