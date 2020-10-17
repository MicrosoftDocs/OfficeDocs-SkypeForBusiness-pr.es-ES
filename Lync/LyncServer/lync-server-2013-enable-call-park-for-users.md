---
title: 'Lync Server 2013: habilitar el estacionamiento de llamadas para los usuarios'
description: 'Lync Server 2013: habilitar el estacionamiento de llamadas para los usuarios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7f9ab23b9fa71943efafd588b8c57a2af781b08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561036"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="08f73-103">Habilitar el estacionamiento de llamadas para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f73-103">Enable Call Park for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08f73-104">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="08f73-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="08f73-105">Los usuarios no pueden estacionar llamadas ni recuperar llamadas estacionadas hasta que estén habilitadas para estacionamiento de llamadas en la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="08f73-105">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08f73-106">De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="08f73-106">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="08f73-107">Puede habilitar el estacionamiento de llamadas en el ámbito global o en el ámbito de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="08f73-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="08f73-108">El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="08f73-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="08f73-109">Si tiene varias directivas de voz, revise todas las directivas para habilitar el estacionamiento de llamadas, no solo la directiva global.</span><span class="sxs-lookup"><span data-stu-id="08f73-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="08f73-110">Para usar el panel de control de Lync Server para habilitar el estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="08f73-110">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="08f73-111">Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins**, o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="08f73-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="08f73-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08f73-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="08f73-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="08f73-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="08f73-114">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="08f73-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="08f73-115">Haga clic en la pestaña **Directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="08f73-115">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="08f73-116">Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="08f73-116">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="08f73-117">En **Características de llamada**, seleccione **Habilitar Estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="08f73-117">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="08f73-118">Haga clic en **Aceptar** para guardar la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="08f73-118">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="08f73-119">Para usar cmdlets para habilitar el estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="08f73-119">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="08f73-120">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="08f73-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="08f73-121">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="08f73-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="08f73-122">Realizar</span><span class="sxs-lookup"><span data-stu-id="08f73-122">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="08f73-123">Por ejemplo, para habilitar el estacionamiento de llamadas de la Directiva de voz global predeterminada:</span><span class="sxs-lookup"><span data-stu-id="08f73-123">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="08f73-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08f73-124">See Also</span></span>


[<span data-ttu-id="08f73-125">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f73-125">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

