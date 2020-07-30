---
title: Asistente de voz de Cortana en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Más información sobre cómo usar el Asistente de voz de Cortana con Teams
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522326"
---
# <a name="cortana-voice-assistance-in-teams"></a>Asistencia de voz de Cortana en Teams

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> La asistencia de voz de Cortana solo se admite en aplicaciones móviles iOS y Android de Microsoft Teams para usuarios de Estados Unidos. Actualmente no está disponible para los inquilinos GCC, GCC-High, DoD, EDU. La expansión de las regiones y los idiomas adicionales se realizará como parte de las versiones futuras.

La asistencia de voz de Cortana de la aplicación móvil de Teams permite a los usuarios empresariales de Microsoft 365 mejorar la comunicación, la colaboración y las tareas relacionadas con la reunión usando el lenguaje natural hablado. Los usuarios pueden hablar con Cortana haciendo clic en el botón del micrófono situado en la esquina superior derecha de la aplicación móvil de Teams. Para conectarse rápidamente con su equipo mientras está de viaje, los usuarios pueden decir consultas como "llamar a Nuria" o "enviar un mensaje a mi próxima reunión". Los usuarios también pueden unirse a reuniones diciendo "unirse a mi próxima reunión" y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más. Estas experiencias de asistencia por voz se proporcionan con los [servicios de calidad empresarial de Cortana](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal como se refleja en las condiciones de los [servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).

La imagen muestra el envío de una conversación en Cortana en un dispositivo móvil.

![La imagen muestra una secuencia de pantallas móviles que muestran una sesión de chat de Cortana](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>Control y limitaciones de administración

La asistencia de voz de Cortana en Teams se ofrece con servicios que cumplen con las promesas de privacidad, seguridad y cumplimiento normativo de Office 365, tal como se refleja en las condiciones de los servicios en línea (OST). La característica se habilitará de forma predeterminada para los inquilinos.

Los administradores de inquilinos pueden controlar quién en su inquilino puede usar la asistencia de voz de Cortana en Teams mediante una directiva (TeamsCortanaPolicy). Esta Directiva se puede establecer a nivel de cuenta de usuario o nivel de inquilino. Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitada, está habilitada solo con la invocación del botón de comando o con la invocación de activación de Word (aplicable a los dispositivos que lo admiten).

Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta Directiva (la Directiva no está disponible en este momento en el centro de administración de Microsoft Teams).

- [Nuevo: CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por ejemplo, el siguiente comando crea una nueva directiva con el nombre "EmployeeCortanaPolicy" donde el Asistente de voz de Cortana de Microsoft Teams está deshabilitado.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

En este ejemplo se muestra cómo actualizar una directiva existente con el nombre "EmployeeCortanaPolicy" y cómo habilitar el Asistente de voz de Cortana en Microsoft Teams con solo la llamada del botón de comando. Los usuarios podrán invocar a Cortana pulsando en el botón de micrófono de Cortana en Teams. Se deshabilitará la invocación de reactivar Word ("Hola Cortana").  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

En este ejemplo se muestra cómo actualizar la Directiva y habilitar el Asistente de voz de Cortana con el botón de comando y la invocación de Wake-Word.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> En el momento de la versión inicial para los usuarios de Microsoft 365 Enterprise en Estados Unidos, la aplicación móvil de Teams no admitirá la activación de reactivación de Word, pero será admitida en el futuro.

## <a name="user-control"></a>Control de usuario

Los usuarios individuales pueden probar la asistencia de voz de Cortana en la aplicación móvil de Teams haciendo clic en el botón micrófono. También pueden controlar si Cortana de Teams está habilitada para su dispositivo con una configuración de la aplicación móvil de Teams.

1. Abra la aplicación móvil de Teams.

2. Vaya a **configuración**.

3. Seleccione **Cortana**.

4. Mueva el botón de alternancia a **activado** o **desactivado**, en función de si quiere usar la asistencia de voz de Cortana en el dispositivo.
