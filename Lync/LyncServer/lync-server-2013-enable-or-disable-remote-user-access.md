---
title: 'Lync Server 2013: habilitar o deshabilitar el acceso de usuarios remotos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73381280b2d87ff73daa79162571f1f729086b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="926fa-102">Habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="926fa-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="926fa-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="926fa-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="926fa-104">Los usuarios remotos son usuarios de la organización que tienen una identidad persistente de Active Directory en la organización.</span><span class="sxs-lookup"><span data-stu-id="926fa-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="926fa-105">Los usuarios remotos a menudo inician sesión en Lync Server desde fuera de la red mediante el uso de una red privada virtual (VPN) cuando no están conectados a la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="926fa-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="926fa-106">Entre los usuarios se encuentran los empleados que trabajan en casa o fuera de la oficina, así como otros trabajadores remotos, como los proveedores de confianza, a los que se conceden credenciales corporativas.</span><span class="sxs-lookup"><span data-stu-id="926fa-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="926fa-107">Si habilita el acceso de usuarios remotos para los usuarios remotos, los usuarios remotos admitidos se conectan a través de Internet y no tienen que conectarse mediante una VPN para colaborar con los usuarios internos mediante Lync Server.</span><span class="sxs-lookup"><span data-stu-id="926fa-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="926fa-p102">Si más adelante desea impedir de forma provisional o definitiva el acceso a usuarios de dominios federados, deshabilite la federación para la organización. Para habilitar o deshabilitar el acceso de usuarios federados en su organización, siga el procedimiento de esta sección, que también incluye las opciones de federación adecuadas que debe admitir la organización.</span><span class="sxs-lookup"><span data-stu-id="926fa-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="926fa-112">Al habilitar el acceso de usuarios remotos solo se especifica que los servidores que ejecuten el servicio perimetral de acceso permitan la comunicación con usuarios remotos, pero dichos usuarios no pueden participar en mensajes instantáneos ni en conferencias de la organización hasta que también se configure una directiva para administrar el uso del acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="926fa-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="926fa-113">La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="926fa-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="926fa-114">La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="926fa-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="926fa-115">Esto significa que cuanto más cerca esté la configuración de la Directiva, el objeto al que afecta la Directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="926fa-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="926fa-116">Para más información sobre cómo configurar directivas para el uso del acceso de usuarios remotos, vea <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure Policies to control remote User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="926fa-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="926fa-117">Para habilitar o deshabilitar el acceso de usuarios remotos en la organización</span><span class="sxs-lookup"><span data-stu-id="926fa-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="926fa-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="926fa-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="926fa-119">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="926fa-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="926fa-120">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="926fa-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="926fa-121">En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y luego en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="926fa-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="926fa-122">En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="926fa-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="926fa-123">En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="926fa-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="926fa-124">Para habilitar el acceso de usuarios remotos en la organización, active la casilla **Habilitar el acceso remoto de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="926fa-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="926fa-125">Para deshabilitar el acceso remoto de usuarios en la organización, desactive la casilla **Habilitar el acceso remoto de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="926fa-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="926fa-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="926fa-126">Click **Commit**.</span></span>

<span data-ttu-id="926fa-127">Para permitir que los usuarios remotos inicien sesión en los servidores que ejecutan Lync Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="926fa-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="926fa-128">Para obtener más información, vea [Configure Policies to control remote User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) en la documentación sobre implementación o sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="926fa-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="926fa-129">Habilitación o deshabilitación del acceso de usuarios remotos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="926fa-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="926fa-130">El acceso de usuarios remotos se puede administrar con Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="926fa-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="926fa-131">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="926fa-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="926fa-132">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="926fa-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="926fa-133">Para habilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="926fa-133">To enable remote user access</span></span>

  - <span data-ttu-id="926fa-134">Para habilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="926fa-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="926fa-135">Para deshabilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="926fa-135">To disable remote user access</span></span>

  - <span data-ttu-id="926fa-136">Para inhabilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="926fa-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

