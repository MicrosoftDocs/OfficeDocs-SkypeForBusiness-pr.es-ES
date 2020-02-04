---
title: (Opcional) Habilitar y deshabilitar los anuncios de participación y abandono de conferencias
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b8e75a0d2ed81a515540f2a8a1811998a85d44c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="31bda-102">(Opcional) Habilitar y deshabilitar los anuncios de participación y abandono de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31bda-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31bda-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="31bda-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="31bda-104">Cuando los usuarios de acceso telefónico se unen o salen de una conferencia, la aplicación de anuncio de conferencia puede anunciar su entrada o salida reproduciendo un tono o diciendo sus nombres.</span><span class="sxs-lookup"><span data-stu-id="31bda-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="31bda-105">Puede cambiar la forma en que funcionan los anuncios ejecutando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="31bda-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="31bda-106">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="31bda-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="31bda-107">Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias</span><span class="sxs-lookup"><span data-stu-id="31bda-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="31bda-108">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="31bda-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="31bda-109">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="31bda-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="31bda-110">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="31bda-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="31bda-111">Este cmdlet recupera información sobre si los participantes deben grabar su nombre al unirse a una conferencia y cómo responde Lync Server cuando los participantes se unen o salen de la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="31bda-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="31bda-112">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="31bda-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="31bda-113">**EnableNameRecording**   determina si se pide a los participantes anónimos que registren su nombre antes de entrar en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="31bda-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="31bda-114">El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unen a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="31bda-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="31bda-115">(Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).</span><span class="sxs-lookup"><span data-stu-id="31bda-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="31bda-116">**EntryExitAnnouncementsEnabledByDefault**   indica si los anuncios están activados o desactivados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="31bda-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="31bda-117">El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan.</span><span class="sxs-lookup"><span data-stu-id="31bda-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="31bda-118">El organizador de la reunión puede invalidar esta opción cuando programa una reunión.</span><span class="sxs-lookup"><span data-stu-id="31bda-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="31bda-119">**EntryExitAnnouncementsType**   indica la acción que se realiza cuando un participante se une a una conferencia o sale de ella para la cual se han habilitado los anuncios.</span><span class="sxs-lookup"><span data-stu-id="31bda-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="31bda-120">El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.</span><span class="sxs-lookup"><span data-stu-id="31bda-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="31bda-p105">Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="31bda-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="31bda-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="31bda-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="31bda-124">En este ejemplo, la configuración se establece en el ámbito del sitio de Redmond.</span><span class="sxs-lookup"><span data-stu-id="31bda-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="31bda-125">Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="31bda-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="31bda-126">Un tono se reproduce cuando los participantes entran o salen de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="31bda-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

