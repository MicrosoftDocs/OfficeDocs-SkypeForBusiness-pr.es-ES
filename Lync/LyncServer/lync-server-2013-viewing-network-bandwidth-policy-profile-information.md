---
title: 'Lync Server 2013: ver información de Perfil de la Directiva de ancho de banda de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb8583eb7d96443f755b0060aedf22c669ad3453
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="059d5-102">Ver la información de Perfil de la Directiva de ancho de banda de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="059d5-102">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="059d5-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="059d5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="059d5-104">Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades.</span><span class="sxs-lookup"><span data-stu-id="059d5-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="059d5-105">En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="059d5-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="059d5-106">Puede establecer limitaciones generales de ancho de banda y sesión.</span><span class="sxs-lookup"><span data-stu-id="059d5-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="059d5-107">Puede usar el panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="059d5-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="059d5-108">Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red.</span><span class="sxs-lookup"><span data-stu-id="059d5-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="059d5-109">Utilice los siguientes procedimientos para ver un perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="059d5-109">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="059d5-110">Para crear o modificar un perfil de directiva de ancho de banda, consulte [creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="059d5-110">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="059d5-111">Para ver un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="059d5-111">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="059d5-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="059d5-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="059d5-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="059d5-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="059d5-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="059d5-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="059d5-115">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="059d5-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="059d5-116">En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea ver.</span><span class="sxs-lookup"><span data-stu-id="059d5-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="059d5-117">En el menú \*\*Editar \*\*, haga clic en \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="059d5-117">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="059d5-118">Ver información de Perfil de la Directiva de ancho de banda de red mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="059d5-118">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="059d5-119">Los perfiles de ancho de banda de red se pueden ver con Windows PowerShell y el cmdlet Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="059d5-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="059d5-120">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="059d5-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="059d5-121">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="059d5-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="059d5-122">Para ver la información del perfil de la Directiva de ancho de banda de red</span><span class="sxs-lookup"><span data-stu-id="059d5-122">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="059d5-123">Para ver información sobre todos los perfiles de directiva de ancho de banda de red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="059d5-123">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="059d5-124">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="059d5-124">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="059d5-125">Si desea más información, consulte el tema de ayuda relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="059d5-125">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="059d5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="059d5-126">See Also</span></span>


[<span data-ttu-id="059d5-127">Creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="059d5-127">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="059d5-128">Eliminación de perfiles de directiva de ancho de banda de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="059d5-128">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="059d5-129">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="059d5-129">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

