---
title: 'Lync Server 2013: Habilitar y deshabilitar el acceso de usuarios remotos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="7d534-102">Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d534-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d534-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7d534-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7d534-104">Los usuarios remotos son usuarios de su organización que tienen una identidad de Active Directory persistente dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="7d534-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="7d534-105">Los usuarios remotos suelen iniciar sesión en Lync Server desde fuera de la red mediante una red privada virtual (VPN) cuando no están conectados a la red de su organización.</span><span class="sxs-lookup"><span data-stu-id="7d534-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="7d534-106">Los usuarios remotos incluyen empleados que trabajan en casa o que están de viaje y otros trabajadores remotos, como proveedores de confianza, a los que se les han concedido credenciales empresariales.</span><span class="sxs-lookup"><span data-stu-id="7d534-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="7d534-107">Si habilita el acceso de usuarios remotos para usuarios remotos, los usuarios remotos compatibles se conectan a través de Internet y no tienen que conectarse usando una VPN para colaborar con usuarios internos que usen Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d534-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="7d534-108">Para admitir el acceso de usuarios remotos, debe habilitar el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="7d534-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="7d534-109">Cuando se habilita el acceso de usuarios remotos, se habilita para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="7d534-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="7d534-110">Si posteriormente desea evitar el acceso de usuarios remotos de forma temporal o permanente, puede deshabilitarlo para su organización.</span><span class="sxs-lookup"><span data-stu-id="7d534-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="7d534-111">Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios remotos a su organización.</span><span class="sxs-lookup"><span data-stu-id="7d534-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d534-112">Habilitar el acceso de usuarios remotos solo especifica que los servidores que ejecutan el servicio perimetral de acceso admiten comunicaciones con usuarios remotos, pero los usuarios remotos no pueden participar en la mensajería instantánea (mi) ni en conferencias de su organización hasta que también configure en menos una directiva para administrar el uso del acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="7d534-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="7d534-113">La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="7d534-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="7d534-114">La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="7d534-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="7d534-115">Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="7d534-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="7d534-116">Para obtener más información sobre cómo configurar directivas para el uso de acceso de usuarios remotos, vea <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7d534-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="7d534-117">Para habilitar o deshabilitar el acceso de usuarios remotos a su organización</span><span class="sxs-lookup"><span data-stu-id="7d534-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="7d534-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7d534-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7d534-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d534-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7d534-120">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7d534-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7d534-121">En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="7d534-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="7d534-122">En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="7d534-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7d534-123">En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7d534-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="7d534-124">Para habilitar el acceso de usuarios remotos a su organización, seleccione la casilla de verificación **Habilitar el acceso de usuarios remotos** .</span><span class="sxs-lookup"><span data-stu-id="7d534-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="7d534-125">Para deshabilitar el acceso de usuarios remotos a su organización, desactive la casilla **Habilitar el acceso de usuarios remotos** .</span><span class="sxs-lookup"><span data-stu-id="7d534-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="7d534-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7d534-126">Click **Commit**.</span></span>

<span data-ttu-id="7d534-127">Para permitir que los usuarios remotos inicien sesión en los servidores que ejecutan Lync Server, también debe configurar al menos una directiva de acceso externo para que admita el acceso de usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="7d534-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="7d534-128">Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="7d534-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7d534-129">Habilitar o deshabilitar el acceso de usuarios remotos mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d534-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7d534-130">El acceso de usuarios remotos se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7d534-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="7d534-131">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d534-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7d534-132">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="7d534-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="7d534-133">Para habilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="7d534-133">To enable remote user access</span></span>

  - <span data-ttu-id="7d534-134">Para habilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en True ($true):</span><span class="sxs-lookup"><span data-stu-id="7d534-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="7d534-135">Para deshabilitar el acceso de usuarios remotos</span><span class="sxs-lookup"><span data-stu-id="7d534-135">To disable remote user access</span></span>

  - <span data-ttu-id="7d534-136">Para deshabilitar el acceso de usuarios remotos, establezca el valor de la propiedad **AllowOutsideUsers** en False ($false):</span><span class="sxs-lookup"><span data-stu-id="7d534-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

