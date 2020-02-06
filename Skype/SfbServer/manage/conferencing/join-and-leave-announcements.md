---
title: Administrar la combinación de conferencia y dejar anuncios en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumen: Aprenda a administrar la combinación de conferencia y a abandonar anuncios en Skype empresarial Server.'
ms.openlocfilehash: 5f975637ca1d85e11c6889a07ff90055ef79ffc5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818551"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="d73a4-103">Administrar la combinación de conferencia y dejar anuncios en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73a4-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="d73a4-104">**Resumen:** Obtenga información sobre cómo administrar la combinación de conferencia y abandonar anuncios en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d73a4-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="d73a4-105">Cuando los usuarios de acceso telefónico se unen o salen de una conferencia, la aplicación de anuncio de conferencia puede anunciar su entrada o salida reproduciendo un tono o diciendo sus nombres.</span><span class="sxs-lookup"><span data-stu-id="d73a4-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="d73a4-106">Puede cambiar el funcionamiento de los anuncios con el shell de administración de Skype empresarial Server y el cmdlet **set-CsDialinConferencing** con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="d73a4-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="d73a4-p102">EnableNameRecording: determina si se pedirá a los participantes anónimos que graben su nombre antes de unirse a la conferencia. El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unen a una conferencia. (Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).</span><span class="sxs-lookup"><span data-stu-id="d73a4-p102">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference. The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference. (Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="d73a4-p103">EntryExitAnnouncementsEnabledByDefault: indica si los anuncios están activados o desactivados de forma predeterminada. El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan. El organizador de la reunión puede invalidar esta opción cuando programa una reunión.</span><span class="sxs-lookup"><span data-stu-id="d73a4-p103">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default. The default value is "$false," which means that by default there are no announcements when participants join or leave a conference. The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="d73a4-p104">EntryExitAnnouncementsType: indica la acción que se realiza siempre que un participante se une a una conferencia para la que tiene habilitados los anuncios o la abandona. El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.</span><span class="sxs-lookup"><span data-stu-id="d73a4-p104">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled. The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="d73a4-p105">Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="d73a4-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="d73a4-117">Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias</span><span class="sxs-lookup"><span data-stu-id="d73a4-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="d73a4-118">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d73a4-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="d73a4-119">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="d73a4-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d73a4-120">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d73a4-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="d73a4-121">Este cmdlet recupera información sobre si los participantes deben grabar su nombre al unirse a una conferencia y cómo responde Skype empresarial Server cuando un participante se une a una conferencia de acceso telefónico local o sale de ella.</span><span class="sxs-lookup"><span data-stu-id="d73a4-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="d73a4-122">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d73a4-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="d73a4-p106">En este ejemplo, las opciones están configuradas en el ámbito del sitio de Redmond. Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia. Suena un tono cuando los participantes se unen a una conferencia o la abandonan:</span><span class="sxs-lookup"><span data-stu-id="d73a4-p106">In the following example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="d73a4-126">Para obtener más información, incluida la sintaxis y una lista completa de parámetros, consulte [set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d73a4-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

