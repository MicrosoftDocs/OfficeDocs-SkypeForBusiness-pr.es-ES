---
title: Cortana asistencia por voz en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Obtenga información sobre cómo usar la asistencia por voz Cortana con Teams
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f888e36d9c0cdd19a0fdd8184d72eeee5ad2a45
ms.sourcegitcommit: 9f7372f7568b4275169590510d2b7a0c0ad7577b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "65171706"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana asistencia de voz en Teams

> [!Note]
> Cortana asistencia de voz se admite en Microsoft Teams aplicaciones móviles para iOS y Android, y en pantallas de Microsoft Teams para usuarios de Estados Unidos, Reino Unido, Canadá, India y Australia. Salas de Microsoft Teams en Windows solo se admite para los dispositivos con configuración regional establecida en en-us. Cortana asistencia por voz no está disponible actualmente para inquilinos de GCC, GCC High, DoD y no US EDU. Cortana asistencia de voz en la aplicación móvil Teams ya está disponible para los clientes de educación en en-US. La expansión a idiomas y regiones adicionales se producirá como parte de futuras versiones.


Cortana la asistencia de voz en la aplicación móvil Teams, en Salas de Microsoft Teams en Windows y en Microsoft Teams dispositivos de pantalla permite Microsoft 365 Enterprise  usuarios para simplificar la comunicación, la colaboración y las tareas relacionadas con las reuniones mediante lenguaje natural hablado. Los usuarios pueden hablar con Cortana seleccionando el botón del micrófono situado en la esquina superior derecha de la aplicación móvil de Teams, o diciendo "Cortana" en la sala de Microsoft Teams o al usar una pantalla de Microsoft Teams. Para conectar rápidamente con el equipo sin manos y mientras se desplaza, los usuarios pueden decir consultas como "llamar a Megan" o "enviar un mensaje a mi próxima reunión". Los usuarios también pueden unirse a reuniones diciendo "unirse a mi próxima reunión" y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más. Estas experiencias de asistencia por voz se entregan con [Cortana servicios de nivel empresarial](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal y como se refleja en los [Términos de servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)).

## <a name="admin-control-and-limitations"></a>Limitaciones y control de administración

Cortana asistencia por voz en Teams se entrega mediante servicios que cumplen plenamente con los Office 365 promesas de privacidad, seguridad y cumplimiento a nivel empresarial, tal y como se refleja en los Términos de servicios en línea (OST). La característica se habilitará de forma predeterminada para los inquilinos.

Los administradores de inquilinos pueden controlar quién en su inquilino puede usar Cortana asistencia por voz en Teams mediante una directiva (TeamsCortanaPolicy). Esta directiva se establece en un nivel de cuenta de usuario o nivel de inquilino. Los administradores pueden usar el campo CortanaVoiceInvocationMode de este control de directiva para determinar si Cortana está deshabilitado, habilitado solo con invocación de botones de presionar o con invocación de reactivación de palabra (aplicable a dispositivos que lo admiten, como la pantalla Microsoft Teams).

Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta directiva (la directiva no está disponible actualmente en Microsoft Teams centro de administración).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por ejemplo, el siguiente comando crea una nueva directiva con el nombre "EmployeeCortanaPolicy" donde se deshabilita Cortana asistencia de voz en Microsoft Teams.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

En este ejemplo se muestra la actualización de una directiva existente con el nombre "EmployeeCortanaPolicy" y la habilitación de Cortana asistencia de voz en Microsoft Teams solo con invocación de botones de pulsar. Los usuarios podrán invocar Cortana seleccionando el botón del micrófono Cortana en Teams. Se deshabilitará la invocación de Palabra de activación ("Hola Cortana" o "Cortana").  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

En este ejemplo se muestra la actualización de la directiva y la habilitación de Cortana asistencia por voz con pulsar y activar la invocación de palabra.

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

En el momento, de la versión inicial para los usuarios de Microsoft 365 Enterprise en estados Unidos en inglés, las siguientes funciones están disponibles:

- La aplicación móvil Teams no admitirá la activación de reactivar palabras, pero se admitirá en el futuro.  

- Salas de Microsoft Teams en los dispositivos de pantalla Windows y Microsoft Teams admitirá la activación de palabras de activación.

## <a name="user-control"></a>Control de usuario

Los usuarios individuales pueden probar Cortana asistencia de voz en diferentes dispositivos:

- Selecciona el botón micrófono en la aplicación móvil Teams.

- Selecciona el botón del micrófono o di "Cortana" en Salas de Microsoft Teams.

- Di "Cortana" en Microsoft Teams muestra dispositivos.

Puede controlar si Cortana en Teams está habilitado para el dispositivo mediante una configuración del dispositivo.

![muestra la progresión de las ventanas móviles al habilitar Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salas de Microsoft Teams en Windows

Realizar cambios en el nivel de dispositivo solo está disponible si Cortana está habilitado en el nivel de inquilino. 

En el nivel de dispositivo, puedes configurar Cortana para que se usen de dos maneras diferentes. Puede habilitar cualquiera de las dos opciones o ambas al mismo tiempo: 
- Pulsando en un micrófono, que se denomina Cortana _Pulsar para hablar_
- Diciendo "Hola, Cortana", que se denomina _activación por voz Cortana_

Cortana _Pulsar para hablar_ está habilitado de forma predeterminada si la sala está configurada con cualquiera de los siguientes idiomas: en-au (Australia), en-ca (Canadá), en-gb (Reino Unido), en-in (India), en-us (Estados Unidos). [Aprende más.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana icono desplazará el botón _Presentar_ debajo de _Más..._ en la consola de sala de Teams. Para deshabilitar Cortana _Usar Push to talk_ con PowerShell.[ Aprende más.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Para habilitar Cortana _activación por voz_, deben cumplirse estas condiciones:
- un dispositivo certificado Cortana debe estar conectado a su sala de Teams. Puede encontrar una lista de dispositivos certificados al final de este artículo.
- la Sala Teams debe estar configurada con cualquiera de los siguientes idiomas: en-au (Australia), en-ca (Canadá), en-gb (Reino Unido), en-in (India), en-us (Estados Unidos). Más idiomas estarán disponibles en una fecha posterior.
- debe realizarse uno de los siguientes cambios de configuración:
  - active la característica en Teams centro de administración [Más información.](/microsoftteams/rooms/rooms-manage)
  - agregue el siguiente atributo XML al archivo XML de SkypeSettings:

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
En el nivel de reunión, realizar cambios solo está disponible si Cortana activación por _voz_ está habilitada en el nivel de dispositivo.  Para habilitar Cortana _activación por voz_ durante una reunión, mueva el botón de alternancia **a Activado** o **Desactivado** para deshabilitarlo. Una vez que finalice la reunión, Cortana vuelva a la configuración de nivel de dispositivo establecida.


Realizar cambios en el nivel de reunión está disponible si Cortana está habilitado en el nivel de dispositivo.

Para habilitar Cortana _activación por voz_ durante una reunión, mueva el botón de alternancia **a Activado** o **Desactivado**. Una vez que finalice la reunión, Cortana vuelva a la configuración de nivel de dispositivo establecida.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana dispositivos certificados para Salas de Teams
Cortana _activación por voz_ puede habilitarse si usa un Lenovo Hub 500 o si tiene alguno de estos dispositivos conectados a su habitación:
- Jabra Panacast 50 
- Micrófonos de Rally
- Barra de vídeo Bose VB1
- EPOS EXPAND Capture 5
- Yealink MSpeech  

