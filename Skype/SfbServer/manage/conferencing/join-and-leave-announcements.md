---
title: Administrar anuncios de unirse y abandonar conferencias en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumen: obtenga información sobre cómo administrar anuncios de unión y salida a conferencias en Skype Empresarial Server.'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828110"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Administrar anuncios de unirse y abandonar conferencias en Skype Empresarial Server
 
**Resumen:** Learn how to manage conference join and leave announcements in Skype for Business Server.
  
Cuando los usuarios de acceso telefónico local se unen a una conferencia o la abandonan, la aplicación de anuncio de conferencia puede anunciar su entrada o salida reproduciendo un tono o diciendo su nombre. Puede cambiar el modo en que funcionan los anuncios mediante el Shell de administración de Skype Empresarial Server y el cmdlet **Set-CsDialinConferencing** con los siguientes parámetros:
  
- EnableNameRecording: determina si se pide a los participantes anónimos que graben su nombre antes de entrar en la conferencia. El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unan a una conferencia. (Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).
    
- EntryExitAnnouncementsEnabledByDefault: indica si los anuncios están activados o desactivados de forma predeterminada. El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan. El organizador de la reunión puede invalidar esta opción cuando programa una reunión.
    
- EntryExitAnnouncementsType: indica la acción que se toma cada vez que un participante se une a una conferencia o la abandona para la que están habilitados los anuncios. El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.
    
Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Este cmdlet recupera información sobre si los participantes deben registrar su nombre al unirse a una conferencia y cómo responde Skype Empresarial Server cuando los participantes se unen a una conferencia de acceso telefónico o la abandonan.
    
4. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

En el siguiente ejemplo, la configuración se configura en el ámbito de sitio de Redmond. Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia. Se reproduce un tono cuando los participantes entran o salen de una conferencia:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Para obtener más información, incluida la sintaxis y una lista completa de parámetros, vea [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

