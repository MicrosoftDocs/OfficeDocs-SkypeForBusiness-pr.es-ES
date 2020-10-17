---
title: Opcional Habilitar y deshabilitar la Unión de conferencia y dejar anuncios
description: Opcional Habilitar y deshabilitar los anuncios de unirse a Conferencia y dejarlos.
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
ms.openlocfilehash: 70cd6b452a44d7d40f23d5ca96b6e4b7b063d2ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565786"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="a3bbf-103">Opcional Habilitar y deshabilitar la Unión a Conferencia y dejar anuncios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3bbf-103">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3bbf-104">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="a3bbf-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="a3bbf-105">Cuando los usuarios de acceso telefónico local se unen a una conferencia o la abandonan, la aplicación de anuncio de conferencia puede anunciar su entrada o salida reproduciendo un tono o diciendo sus nombres.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="a3bbf-106">Puede cambiar el funcionamiento de los anuncios ejecutando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-106">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="a3bbf-107">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-107">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="a3bbf-108">Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias</span><span class="sxs-lookup"><span data-stu-id="a3bbf-108">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="a3bbf-109">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="a3bbf-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a3bbf-111">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="a3bbf-111">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="a3bbf-112">Este cmdlet recupera información sobre si los participantes deben grabar su nombre al unirse a una conferencia y cómo responde Lync Server cuando los participantes se unen a una conferencia de acceso telefónico local o la abandonan.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-112">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="a3bbf-113">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="a3bbf-113">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="a3bbf-114">**EnableNameRecording**     Determina si se pide a los participantes anónimos que registren su nombre antes de entrar en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-114">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="a3bbf-115">El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unan a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-115">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="a3bbf-116">(Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).</span><span class="sxs-lookup"><span data-stu-id="a3bbf-116">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="a3bbf-117">**EntryExitAnnouncementsEnabledByDefault**     Indica si los anuncios están activados o desactivados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-117">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="a3bbf-118">El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-118">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="a3bbf-119">El organizador de la reunión puede invalidar esta opción cuando programa una reunión.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-119">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="a3bbf-120">**EntryExitAnnouncementsType**     Indica la acción que se realiza siempre que un participante se une a una conferencia en la que los anuncios están habilitados o sale de la misma.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-120">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="a3bbf-121">El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-121">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="a3bbf-p105">Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="a3bbf-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a3bbf-124">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="a3bbf-p106">En este ejemplo, las opciones están configuradas en el ámbito del sitio de Redmond. Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia. Suena un tono cuando los participantes se unen a una conferencia o la abandonan.</span><span class="sxs-lookup"><span data-stu-id="a3bbf-p106">In this example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

