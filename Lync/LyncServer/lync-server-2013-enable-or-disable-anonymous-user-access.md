---
title: 'Lync Server 2013: Habilitar y deshabilitar el acceso anónimo de usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d07bf27f5424f121c5dcf070f5231e2fd8c324f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="58fa6-102">Habilitar y deshabilitar el acceso anónimo de usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58fa6-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58fa6-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="58fa6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="58fa6-104">Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de su organización o en un dominio federado admitido, pero se les puede invitar a participar de forma remota en una conferencia local.</span><span class="sxs-lookup"><span data-stu-id="58fa6-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="58fa6-105">Al permitir la participación anónima en las reuniones, habilita los usuarios anónimos (es decir, los usuarios cuya identidad se comprueba a través de la reunión o de la clave de conferencia) para unirse a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="58fa6-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="58fa6-106">Permitir la participación anónima requiere habilitarlo para su organización.</span><span class="sxs-lookup"><span data-stu-id="58fa6-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="58fa6-107">Si posteriormente desea impedir de forma temporal o permanente el acceso de usuarios anónimos, puede deshabilitarlo para su organización.</span><span class="sxs-lookup"><span data-stu-id="58fa6-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="58fa6-108">Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios anónimos a su organización.</span><span class="sxs-lookup"><span data-stu-id="58fa6-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58fa6-109">Al permitir el acceso de usuarios anónimos a su organización, solo se especifica que los servidores que ejecutan el servicio perimetral de acceso admiten el acceso de usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="58fa6-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="58fa6-110">Los usuarios anónimos no pueden participar en ninguna reunión de su organización hasta que también configure al menos una directiva de conferencia y la aplique a uno o más usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="58fa6-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="58fa6-111">Los únicos usuarios que pueden invitar a usuarios anónimos a las reuniones son aquellos a los que se les ha asignado una directiva de conferencia que está configurada para admitir usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="58fa6-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="58fa6-112">Para obtener más información sobre cómo configurar directivas de conferencia para admitir la invitación a usuarios anónimos, consulte <A href="lync-server-2013-conferencing-policies.md">directivas de conferencia en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="58fa6-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="58fa6-113">Para habilitar o deshabilitar el acceso de usuarios anónimos para su organización</span><span class="sxs-lookup"><span data-stu-id="58fa6-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="58fa6-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="58fa6-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58fa6-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="58fa6-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="58fa6-116">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="58fa6-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="58fa6-117">En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **configuración del borde de Access**.</span><span class="sxs-lookup"><span data-stu-id="58fa6-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="58fa6-118">En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="58fa6-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="58fa6-119">En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="58fa6-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="58fa6-120">Para habilitar el acceso de usuarios anónimos para su organización, seleccione la casilla de verificación **habilitar las comunicaciones con usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="58fa6-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="58fa6-121">Para deshabilitar el acceso de usuarios anónimos para su organización, desactive la casilla **habilitar las comunicaciones con usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="58fa6-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="58fa6-122">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="58fa6-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="58fa6-123">Habilitar o deshabilitar el acceso de usuarios anónimos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="58fa6-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="58fa6-124">Puede administrar el acceso de usuarios anónimos mediante Windows PowerShell y el cmdlet **set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="58fa6-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="58fa6-125">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58fa6-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="58fa6-126">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="58fa6-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="58fa6-127">Para habilitar el acceso de usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="58fa6-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="58fa6-128">Para habilitar el acceso de usuarios anónimos, establece el valor de la propiedad **AllowAnonymousUsers** en True ($true):</span><span class="sxs-lookup"><span data-stu-id="58fa6-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="58fa6-129">Para deshabilitar el acceso de usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="58fa6-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="58fa6-130">Para deshabilitar el acceso de usuarios anónimos, establece el valor de la propiedad **AllowAnonymousUsers** en False ($false):</span><span class="sxs-lookup"><span data-stu-id="58fa6-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58fa6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="58fa6-131">See Also</span></span>


[<span data-ttu-id="58fa6-132">Referencia de configuración de directiva de conferencia para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58fa6-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

