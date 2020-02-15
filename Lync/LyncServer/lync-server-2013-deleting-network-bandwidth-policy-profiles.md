---
title: 'Lync Server 2013: eliminación de perfiles de directiva de ancho de banda de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a340cae47a73cb2b7926cf3f3b3832d22432ab2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="b1d8e-102">Eliminación de perfiles de directiva de ancho de banda de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1d8e-102">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1d8e-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b1d8e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b1d8e-104">Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="b1d8e-105">En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="b1d8e-106">Puede establecer limitaciones generales de ancho de banda y sesión.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="b1d8e-107">Puede usar el panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="b1d8e-108">Use los siguientes procedimientos para eliminar perfiles de directiva de ancho de banda de red.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-108">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="b1d8e-109">Para obtener información detallada sobre cómo crear o modificar un perfil de directiva de ancho de banda de red, consulte [creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b1d8e-109">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="b1d8e-110">Para eliminar un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="b1d8e-110">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="b1d8e-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1d8e-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1d8e-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b1d8e-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1d8e-114">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-114">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="b1d8e-115">En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-115">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b1d8e-p103">Puede eliminar más de un perfil en la misma operación. Para hacerlo, pulse CTRL y seleccione varios perfiles manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los perfiles, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-p103">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="b1d8e-119">En el menú \*\*Editar \*\*, haga clic en \*\*Eliminar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-119">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b1d8e-120">No puede eliminar un perfil de directiva de ancho de banda que esté asociado a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-120">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="b1d8e-121">Primero debe eliminar la asociación establecida con el sitio de red para poder eliminar el perfil.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-121">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="b1d8e-122">Para obtener más información sobre cómo modificar el sitio de red, vea <A href="lync-server-2013-creating-or-modifying-network-sites.md">crear o modificar sitios de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b1d8e-122">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1d8e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1d8e-123">See Also</span></span>


[<span data-ttu-id="b1d8e-124">Creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1d8e-124">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="b1d8e-125">Ver la información de Perfil de la Directiva de ancho de banda de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1d8e-125">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="b1d8e-126">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1d8e-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="b1d8e-127">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="b1d8e-127">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

