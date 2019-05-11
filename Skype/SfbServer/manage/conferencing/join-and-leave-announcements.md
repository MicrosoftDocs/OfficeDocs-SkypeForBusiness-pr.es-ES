---
title: Administrar unirse a conferencia y dejar anuncios en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumen: Obtenga información sobre cómo administrar unirse a conferencia y dejar anuncios en Skype para Business Server.'
ms.openlocfilehash: ace07fdc3325d97e443297265892e7bcc4bce562
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919524"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Administrar unirse a conferencia y dejar anuncios en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo administrar unirse a conferencia y dejar anuncios en Skype para Business Server.
  
Cuando los usuarios de acceso telefónico unirse o abandonar una conferencia, la aplicación de anuncio de conferencia puede anunciar su entrada o salir de reproducir un tono o diciendo sus nombres. Puede cambiar el funcionan de los anuncios mediante el uso de Skype para Shell de administración de servidor empresarial y el cmdlet **Set-CsDialinConferencing** con los siguientes parámetros:
  
- EnableNameRecording: determina si se pedirá a los participantes anónimos que graben su nombre antes de unirse a la conferencia. El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unen a una conferencia. (Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).
    
- EntryExitAnnouncementsEnabledByDefault: indica si los anuncios están activados o desactivados de forma predeterminada. El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan. El organizador de la reunión puede invalidar esta opción cuando programa una reunión.
    
- EntryExitAnnouncementsType: indica la acción que se realiza siempre que un participante se une a una conferencia para la que tiene habilitados los anuncios o la abandona. El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.
    
Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

Este cmdlet recupera información acerca de si los participantes deben grabar su nombre al unirse a una conferencia y cómo Skype para Business Server responde cuando los participantes unirse o abandonar una conferencia de acceso telefónico.
    
4. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

En este ejemplo, las opciones están configuradas en el ámbito del sitio de Redmond. Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia. Suena un tono cuando los participantes se unen a una conferencia o la abandonan:
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Para obtener más información, incluida la sintaxis y una lista completa de los parámetros, consulte [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

