---
title: Administrar anuncios de unirse y dejar conferencias en Skype Empresarial Server
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
description: 'Summary: Learn how to manage conference join and leave announcements in Skype for Business Server.'
ms.openlocfilehash: 796266dd3b571e525f657d5dbe712d1577779cae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119459"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="b4c52-103">Administrar anuncios de unirse y dejar conferencias en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b4c52-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="b4c52-104">**Resumen:** Obtenga información sobre cómo administrar los anuncios de unirse y dejar conferencias en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b4c52-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="b4c52-105">Cuando los usuarios de acceso telefónico local se unen o salen de una conferencia, la aplicación de anuncio de conferencia puede anunciar su entrada o salida reproduciendo un tono o diciendo sus nombres.</span><span class="sxs-lookup"><span data-stu-id="b4c52-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="b4c52-106">Puede cambiar el modo en que funcionan los anuncios mediante el Shell de administración de Skype Empresarial Server y el cmdlet **Set-CsDialinConferencing** con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="b4c52-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="b4c52-107">EnableNameRecording: determina si se pide a los participantes anónimos que registren su nombre antes de entrar en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="b4c52-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="b4c52-108">El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unan a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="b4c52-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="b4c52-109">(Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).</span><span class="sxs-lookup"><span data-stu-id="b4c52-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="b4c52-110">EntryExitAnnouncementsEnabledByDefault: indica si los anuncios están activados o desactivados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b4c52-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="b4c52-111">El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan.</span><span class="sxs-lookup"><span data-stu-id="b4c52-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="b4c52-112">El organizador de la reunión puede invalidar esta opción cuando programa una reunión.</span><span class="sxs-lookup"><span data-stu-id="b4c52-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="b4c52-113">EntryExitAnnouncementsType: indica la acción que se hace cada vez que un participante se une o sale de una conferencia para la que se habilitan los anuncios.</span><span class="sxs-lookup"><span data-stu-id="b4c52-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="b4c52-114">El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.</span><span class="sxs-lookup"><span data-stu-id="b4c52-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="b4c52-p105">Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="b4c52-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="b4c52-117">Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias</span><span class="sxs-lookup"><span data-stu-id="b4c52-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="b4c52-118">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b4c52-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="b4c52-119">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="b4c52-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b4c52-120">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b4c52-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="b4c52-121">Este cmdlet recupera información sobre si los participantes deben registrar su nombre al unirse a una conferencia y cómo responde Skype Empresarial Server cuando los participantes se unen o salen de una conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b4c52-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="b4c52-122">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b4c52-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="b4c52-123">En el siguiente ejemplo, la configuración se configura en el ámbito del sitio para Redmond.</span><span class="sxs-lookup"><span data-stu-id="b4c52-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="b4c52-124">Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="b4c52-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="b4c52-125">Se reproduce un tono cuando los participantes entran o salen de una conferencia:</span><span class="sxs-lookup"><span data-stu-id="b4c52-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="b4c52-126">Para obtener más información, incluida la sintaxis y una lista completa de parámetros, vea [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b4c52-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
