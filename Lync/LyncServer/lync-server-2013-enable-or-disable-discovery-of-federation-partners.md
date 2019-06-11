---
title: 'Lync Server 2013: Habilitar o deshabilitar la detección de socios de federación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e83f261fe6fa3ece259518b7730239adf20944c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="30206-102">Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30206-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30206-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="30206-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="30206-104">En el momento de implementar los servidores perimetrales y de habilitar la Federación de su organización, debe haber especificado si se debe admitir la detección automática de dominios federados de socios.</span><span class="sxs-lookup"><span data-stu-id="30206-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="30206-105">Use el procedimiento de este tema para cambiar esa configuración.</span><span class="sxs-lookup"><span data-stu-id="30206-105">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30206-106">En el procedimiento siguiente se supone que ya ha habilitado la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="30206-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="30206-107">Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="30206-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="30206-108">Para habilitar o deshabilitar la detección automática de dominios federados para su organización</span><span class="sxs-lookup"><span data-stu-id="30206-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="30206-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="30206-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="30206-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30206-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30206-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30206-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="30206-112">En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **configuración del borde de Access**.</span><span class="sxs-lookup"><span data-stu-id="30206-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="30206-113">En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="30206-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="30206-114">En **Editar configuración del límite de acceso**, en **habilitar las comunicaciones con usuarios federados**, Active o desactive la casilla **Habilitar la detección** de dominios asociados para habilitar o deshabilitar la detección automática de dominios asociados.</span><span class="sxs-lookup"><span data-stu-id="30206-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="30206-115">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="30206-115">Click **Commit**.</span></span>

<span data-ttu-id="30206-116">Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server, también debe haber configurado al menos una directiva de acceso externa para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="30206-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="30206-117">Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="30206-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="30206-118">Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, consulte [administrar dominios federados SIP para su organización en Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [administrar proveedores federados SIP para su organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) y [administrar XMPP socios federados de Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="30206-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="30206-119">Habilitar o deshabilitar la detección de socios de Federación mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30206-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="30206-120">El descubrimiento de los socios de la Federación se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="30206-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="30206-121">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30206-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="30206-122">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="30206-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="30206-123">Para habilitar la detección de socios de Federación</span><span class="sxs-lookup"><span data-stu-id="30206-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="30206-124">Para habilitar la detección de socios de Federación, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($true).</span><span class="sxs-lookup"><span data-stu-id="30206-124">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="30206-125">Tenga en cuenta que debe habilitar el enrutamiento SRV de DNS para poder cambiar este valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="30206-125">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="30206-126">Para deshabilitar la detección de socios de Federación</span><span class="sxs-lookup"><span data-stu-id="30206-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="30206-127">Para deshabilitar la detección de socios de Federación, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($false):</span><span class="sxs-lookup"><span data-stu-id="30206-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

