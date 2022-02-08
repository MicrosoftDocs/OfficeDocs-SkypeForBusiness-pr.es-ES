---
title: Administrar anuncios de unirse y dejar conferencias en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Summary: Learn how to manage conference join and leave announcements in Skype Empresarial Server.'
ms.openlocfilehash: ac259999daaa2fed0988e59d9ab40b9370a2fba8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385788"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Administrar anuncios de unirse y dejar conferencias en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar la unión a conferencias y dejar anuncios en Skype Empresarial Server.
  
Cuando los usuarios de acceso telefónico telefónico se unen o salen de una conferencia, el aplicación Anuncio de conferencia puede anunciar su entrada o salida tocando un tono o diciendo sus nombres. Puede cambiar el modo en que funcionan los anuncios mediante Skype Empresarial Server Shell de administración y el cmdlet **Set-CsDialinConferencing** con los siguientes parámetros:
  
- EnableNameRecording: determina si se pide a los participantes anónimos que registren su nombre antes de entrar en la conferencia. El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unan a una conferencia. (Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).
    
- EntryExitAnnouncementsEnabledByDefault: indica si los anuncios están activados o desactivados de forma predeterminada. El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan. El organizador de la reunión puede invalidar esta opción cuando programa una reunión.
    
- EntryExitAnnouncementsType: indica la acción que se hace cada vez que un participante se une o sale de una conferencia para la que se habilitan los anuncios. El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.
    
Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en **Inicio, todos** los **programas,** **Skype Empresarial 2015** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Este cmdlet recupera información sobre si los participantes deben registrar su nombre al unirse a una conferencia y cómo Skype Empresarial Server responde cuando los participantes se unen o salen de una conferencia de acceso telefónico.
    
4. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

En el siguiente ejemplo, la configuración se configura en el ámbito del sitio para Redmond. Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia. Se reproduce un tono cuando los participantes entran o salen de una conferencia:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Para obtener más información, incluida la sintaxis y una lista completa de parámetros, vea [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
