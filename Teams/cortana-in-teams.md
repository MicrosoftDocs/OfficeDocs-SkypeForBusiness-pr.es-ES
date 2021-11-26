---
title: Cortana de voz en Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Obtenga información sobre cómo usar Cortana de voz con Teams
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
ms.openlocfilehash: fe6434fe874367757dfb7ad954aacaf8d3755041
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205500"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana de voz en Teams

> [!Note]
> Cortana de voz es compatible con las aplicaciones móviles de Microsoft Teams para iOS y Android y Microsoft Teams para usuarios de Estados Unidos, Reino Unido, Canadá, India y Australia. Salas de Microsoft Teams en Windows solo es compatible con dispositivos con configuración regional establecida en en-us. Cortana asistencia de voz no está disponible actualmente para los inquilinos GCC, GCC-High, DoD y otros inquilinos edu. Cortana asistencia de voz en la Teams móvil ya está disponible para los clientes de EDU en Ee. UU. La expansión a idiomas y regiones adicionales se realizará como parte de futuras versiones.


Cortana de voz en la aplicación móvil Teams, en Salas de Microsoft Teams en Windows y en Microsoft Teams dispositivos de Microsoft 365 Enterprise  usuarios para simplificar la comunicación, la colaboración y las tareas relacionadas con reuniones con el lenguaje natural hablado. Los usuarios pueden hablar con Cortana seleccionando el botón del micrófono situado en la esquina superior derecha de la aplicación móvil de Teams o diciendo "Cortana" en la sala de Microsoft Teams o al usar una pantalla Microsoft Teams pantalla. Para conectarse rápidamente con su equipo manos libres y mientras están en cualquier lugar, los usuarios pueden decir consultas como "llamar a Megan" o "enviar un mensaje a mi próxima reunión". Los usuarios también pueden unirse a reuniones diciendo "unirse a mi próxima reunión" y usar la asistencia de voz para compartir archivos, comprobar su calendario y mucho más. Estas experiencias de asistencia de voz se entregan [Cortana con](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) servicios de nivel empresarial que cumplen plenamente con las promesas de privacidad, seguridad y cumplimiento de Office 365, tal y como se reflejan en los Términos de servicios en línea [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)

## <a name="admin-control-and-limitations"></a>Control de administración y limitaciones

Cortana de voz en Teams se entrega con servicios que cumplen completamente con las promesas de privacidad, seguridad y cumplimiento de Office 365 nivel empresarial, tal como se reflejan en los Términos de servicios en línea (OST). La característica se habilitará de forma predeterminada para los inquilinos.

Los administradores de inquilinos pueden controlar quién en su espacio empresarial puede usar Cortana de voz en Teams una directiva (TeamsCortanaPolicy). Esta directiva se establece en un nivel de cuenta de usuario o de inquilino. Los administradores pueden usar el campo CortanaVoiceInvocationMode dentro de este control de directiva para determinar si Cortana está deshabilitado, habilitado solo con la invocación de botón de inserción o también con la invocación de palabra reactiva (aplicable a los dispositivos que lo admiten, como la pantalla Microsoft Teams).

Los administradores pueden usar los siguientes cmdlets de PowerShell para administrar esta directiva (la directiva no está disponible actualmente en Microsoft Teams centro de administración).

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

Por ejemplo, el comando siguiente crea una nueva directiva con el nombre "EmployeeCortanaPolicy" donde Cortana de voz en Microsoft Teams está deshabilitado.  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

En este ejemplo se muestra la actualización de una directiva existente con el nombre "EmployeeCortanaPolicy" y la habilitación de Cortana de voz en Microsoft Teams solo con invocación de botón. Los usuarios podrán invocar el Cortana seleccionando el Cortana de micrófono en Teams. Se deshabilitará la invocación wake word ("Hola Cortana" o "Cortana") .  

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

![muestra la progresión de las ventanas móviles al habilitar Cortana.](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Salas de Microsoft Teams en Windows

Realizar cambios en el nivel de dispositivo solo está disponible si Cortana está habilitado en el nivel de inquilino. 

En el nivel de dispositivo, puede configurar Cortana que se utilicen de dos maneras diferentes. Puede habilitar cualquiera de las dos opciones o ambas al mismo tiempo: 
- Pulsando en un micrófono, que se denomina Cortana _Pulsar para hablar_
- Al decir "Hola, Cortana", que se denomina _Cortana activación de voz_

Cortana Push _to talk_ está habilitado de forma predeterminada si su sala está configurada con cualquiera de los siguientes idiomas: en-au (Australia), en-ca (Canadá), en-gb (Reino Unido), en-in (India), en-us (Estados Unidos). [Aprende más.](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana icono desplazará el botón _Presentar_ en _más..._ en la consola Teams sala. Para deshabilitar Cortana _Usar La conversación use_ PowerShell.[ Aprende más.](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

Para habilitar Cortana _activación de voz,_ deben cumplirse estas condiciones:
- un Cortana certificado debe estar conectado a su Teams sala. Puede encontrar una lista de dispositivos certificados al final de este artículo.
- la sala Teams debe configurarse con cualquiera de los siguientes idiomas: en-au (Australia), en-ca (Canadá), en-gb (Reino Unido), en-in (India), en-us (Estados Unidos). Más idiomas estarán disponibles más adelante.
- uno de los siguientes cambios de configuración debe realizarse:
  - activa la característica en Teams centro de administración [más información.](/microsoftteams/rooms/rooms-manage)
  - agregue el siguiente atributo XML al archivo XML de SkypeSettings:

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
En el nivel de reunión, realizar cambios solo está disponible si Cortana _activación_ de voz está habilitada en el nivel de dispositivo.  Para habilitar Cortana _activación de voz_ durante una reunión, mueva el botón de alternancia **Activado** o **Desactivado** para deshabilitar. Una vez que finalice la reunión, Cortana volverá a la configuración de nivel de dispositivo establecida.


Realizar cambios en el nivel de reunión está disponible si Cortana está habilitado en el nivel de dispositivo.

Para habilitar Cortana _de voz_ durante una reunión, mueva el botón de alternancia **Activado** o **Desactivado.** Una vez que finalice la reunión, Cortana volverá a la configuración de nivel de dispositivo establecida.


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana dispositivos certificados para Salas de Teams
Cortana _activación_ por voz se puede habilitar si usa un Lenovo Hub 500 o si tiene alguno de estos dispositivos conectados a su sala:
- Jabra Panacast 50 
- Micrófonos de reunión
- Barra de vídeo de Bose VB1

