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
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785394"
---
# <a name="cortana-voice-assistance-in-teams"></a>Asistencia de voz de Cortana en Teams

> [!Note]
> La asistencia de voz de Cortana es compatible con las aplicaciones móviles iOS y Android de Microsoft Teams, y en Microsoft Teams se muestra solo para los usuarios de los Estados Unidos. Actualmente no está disponible para los inquilinos GCC, GCC-High, DoD, EDU. La expansión de las regiones y los idiomas adicionales se realizará como parte de las versiones futuras.

La asistencia por voz de Cortana en la aplicación móvil de Teams y en los dispositivos de visualización de Microsoft Teams permite a los usuarios empresariales de Microsoft 365 mejorar la comunicación, la colaboración y las tareas relacionadas con la reunión usando el lenguaje natural hablado. Los usuarios pueden hablar con Cortana seleccionando el botón de micrófono situado en la parte superior derecha de la aplicación móvil de Teams o diciendo &#8220;Cortana&#8221; en la pantalla de Microsoft Teams. Para conectarse rápidamente con sus manos libres de su equipo y mientras se desplazan, los usuarios pueden decir consultas como &#8220;llamar a Nuria&#8221; o &#8220;enviar un mensaje a la próxima reunión&#8221;. Los usuarios también pueden unirse a reuniones diciendo &#8220;unirse a mi próxima reunión&#8221; y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más. Estas experiencias de asistencia por voz se proporcionan con los [servicios de calidad empresarial de Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal como se refleja en las condiciones de los [servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

La imagen muestra el envío de una conversación con Cortana en un dispositivo móvil.

![La imagen muestra una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Control y limitaciones de administración

La asistencia de voz de Cortana en Teams se ofrece con servicios que cumplen con las promesas de privacidad, seguridad y cumplimiento normativo de Office 365, tal como se refleja en las condiciones de los servicios en línea (OST). La característica se habilitará de forma predeterminada para los inquilinos.

Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy). Esta Directiva se puede establecer a nivel de cuenta de usuario o nivel de inquilino. Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitada, está habilitada solamente con la invocación del botón de comando o con la invocación de reactivación de Word (aplicable a dispositivos que lo admiten, como la presentación de Microsoft Teams).

Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta Directiva (la Directiva no está disponible en este momento en el centro de administración de Microsoft Teams).

- [Nuevo: CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

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

> [!Note]
> En el momento de la versión inicial para los usuarios de Microsoft 365 Enterprise en Estados Unidos, la aplicación móvil de Teams no admitirá la activación de reactivación de Word, pero será admitida en el futuro. La activación de Word Wake funciona en dispositivos de pantalla de Microsoft Teams en la versión inicial.

## <a name="user-control"></a>Control de usuario

Los usuarios individuales pueden probar la asistencia de voz de Cortana en la aplicación móvil de Teams seleccionando el botón del micrófono. Pueden probar la asistencia de voz de Cortana en dispositivos de visualización de Microsoft Teams simplemente diciendo &#8220;Cortana. &#8221; también pueden controlar si Cortana de Teams está habilitado para su dispositivo con una configuración de la aplicación móvil de Teams o de Microsoft Teams.

1. Abra la aplicación móvil de Teams o vaya a la pantalla ambiente (Inicio) de la pantalla de Microsoft Teams.

2. En la aplicación móvil de Teams, vaya a **configuración** . En la pantalla de Microsoft Teams, seleccione el avatar de usuario y, a continuación, seleccione Configuración. Si Cortana está habilitada, diga &#8220;Cortana, vaya a configuración. &#8221;

3. Seleccione **Cortana** .

4. Mueva el botón de alternancia a **activado** o **desactivado** , en función de si quiere usar la asistencia de voz de Cortana en el dispositivo.
