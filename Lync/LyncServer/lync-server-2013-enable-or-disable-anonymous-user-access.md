---
title: 'Lync Server 2013: habilitar o deshabilitar el acceso de usuarios anónimos'
description: 'Lync Server 2013: habilitar o deshabilitar el acceso de usuarios anónimos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca36cffc25cd31d057b00c22cb299c56cfd7b3c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544776"
---
# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="a67a9-103">Habilitar o deshabilitar el acceso de usuarios anónimos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a67a9-103">Enable or disable anonymous user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a67a9-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a67a9-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a67a9-105">Los usuarios anónimos son usuarios que no tienen una cuenta de usuario en los servicios de dominio de Active Directory de la organización o en un dominio federado admitido, pero que pueden ser invitados a participar remotamente en una conferencia local.</span><span class="sxs-lookup"><span data-stu-id="a67a9-105">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="a67a9-106">Al permitir la participación anónima en las reuniones, se habilitan los usuarios anónimos (es decir, los usuarios cuya identidad se comprueba sólo a través de la reunión o la clave de conferencia) para unirse a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="a67a9-106">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="a67a9-107">Para permitir la participación anónima, es necesario habilitarla para su organización.</span><span class="sxs-lookup"><span data-stu-id="a67a9-107">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="a67a9-108">Si más adelante desea evitar temporalmente o permanentemente el acceso de usuarios anónimos, puede deshabilitarlo para su organización.</span><span class="sxs-lookup"><span data-stu-id="a67a9-108">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="a67a9-109">Use el procedimiento descrito en esta sección para habilitar o deshabilitar el acceso de usuarios anónimos para su organización.</span><span class="sxs-lookup"><span data-stu-id="a67a9-109">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a67a9-110">Al habilitar el acceso de usuarios anónimos para su organización, solo está especificando que los servidores que ejecutan el servicio perimetral de acceso admitan el acceso por parte de usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="a67a9-110">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="a67a9-111">Los usuarios anónimos no pueden participar en ninguna reunión de su organización hasta que también configure al menos una directiva de conferencia y la aplique a uno o varios usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a67a9-111">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="a67a9-112">Los únicos usuarios que pueden invitar a usuarios anónimos a las reuniones son aquellos a los que se les asigna una directiva de conferencia configurada para admitir usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="a67a9-112">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="a67a9-113">Para obtener más información sobre cómo configurar directivas de conferencia para admitir la invitación a usuarios anónimos, consulte <A href="lync-server-2013-conferencing-policies.md">directivas de conferencia en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a67a9-113">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="a67a9-114">Para habilitar o deshabilitar el acceso de usuarios anónimos para la organización</span><span class="sxs-lookup"><span data-stu-id="a67a9-114">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="a67a9-115">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a67a9-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a67a9-116">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a67a9-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a67a9-117">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a67a9-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a67a9-118">En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="a67a9-118">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="a67a9-119">En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="a67a9-119">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a67a9-120">En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a67a9-120">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="a67a9-121">Para habilitar el acceso de usuarios anónimos para su organización, active la casilla de verificación **Habilitar comunicaciones con usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="a67a9-121">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="a67a9-122">Para deshabilitar el acceso de usuarios anónimos para la organización, desactive la casilla de verificación **Habilitar comunicaciones con usuarios anónimos** .</span><span class="sxs-lookup"><span data-stu-id="a67a9-122">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="a67a9-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a67a9-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a67a9-124">Habilitación o deshabilitación del acceso de usuarios anónimos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a67a9-124">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a67a9-125">Puede administrar el acceso de usuarios anónimos mediante Windows PowerShell y el cmdlet **set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a67a9-125">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="a67a9-126">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a67a9-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a67a9-127">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a67a9-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="a67a9-128">Para habilitar el acceso de usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="a67a9-128">To enable anonymous user access</span></span>

  - <span data-ttu-id="a67a9-129">Para habilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en True ($true):</span><span class="sxs-lookup"><span data-stu-id="a67a9-129">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="a67a9-130">Para deshabilitar el acceso de usuarios anónimos</span><span class="sxs-lookup"><span data-stu-id="a67a9-130">To disable anonymous user access</span></span>

  - <span data-ttu-id="a67a9-131">Para deshabilitar el acceso de usuarios anónimos, establezca el valor de la propiedad **AllowAnonymousUsers** en False ($false):</span><span class="sxs-lookup"><span data-stu-id="a67a9-131">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a67a9-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a67a9-132">See Also</span></span>


[<span data-ttu-id="a67a9-133">Referencia de configuración de directiva de conferencia para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a67a9-133">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

