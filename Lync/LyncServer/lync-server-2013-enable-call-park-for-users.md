---
title: 'Lync Server 2013: habilitar el parque de llamadas para los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16538ba00571c429493a2bc0ce1ef14b0a331305
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="630b1-102">Habilitar el parque de llamadas para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="630b1-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="630b1-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="630b1-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="630b1-104">Los usuarios no pueden detener llamadas ni recuperar llamadas estacionadas hasta que estén habilitadas para el parque de llamadas en la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="630b1-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="630b1-105">De forma predeterminada, el parque de llamadas está deshabilitado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="630b1-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="630b1-106">Puede habilitar el parque de llamadas en el ámbito global o en el ámbito del sitio o ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="630b1-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="630b1-107">El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="630b1-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="630b1-108">Si tiene varias directivas de voz, revise todas las directivas para habilitar el parque de llamadas, no solo la directiva global.</span><span class="sxs-lookup"><span data-stu-id="630b1-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="630b1-109">Para usar el panel de control de Lync Server para habilitar el parque de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="630b1-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="630b1-110">Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="630b1-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="630b1-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="630b1-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="630b1-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="630b1-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="630b1-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="630b1-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="630b1-114">Haga clic en la pestaña **Directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="630b1-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="630b1-115">Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="630b1-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="630b1-116">En **Características de llamada**, seleccione **Habilitar estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="630b1-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="630b1-117">Haga clic en **Aceptar** para guardar la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="630b1-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="630b1-118">Para usar cmdlets para habilitar el parque de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="630b1-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="630b1-119">Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="630b1-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="630b1-120">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="630b1-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="630b1-121">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="630b1-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="630b1-122">Por ejemplo, para habilitar el parque de llamadas para la Directiva de voz global predeterminada:</span><span class="sxs-lookup"><span data-stu-id="630b1-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="630b1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="630b1-123">See Also</span></span>


[<span data-ttu-id="630b1-124">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="630b1-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

