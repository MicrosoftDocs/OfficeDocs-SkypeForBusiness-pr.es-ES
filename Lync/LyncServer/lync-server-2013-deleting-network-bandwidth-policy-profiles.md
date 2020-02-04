---
title: 'Lync Server 2013: eliminar perfiles de directiva de ancho de banda de red'
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
ms.openlocfilehash: 2d01bdea6efb632d95a15c631715e9ebe0c9a3bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="ace06-102">Eliminar perfiles de directiva de ancho de banda de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ace06-102">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ace06-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ace06-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ace06-104">Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="ace06-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="ace06-105">En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="ace06-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="ace06-106">Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión.</span><span class="sxs-lookup"><span data-stu-id="ace06-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="ace06-107">Puede usar el panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="ace06-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="ace06-108">Use los procedimientos siguientes para eliminar los perfiles de la Directiva de ancho de banda de red.</span><span class="sxs-lookup"><span data-stu-id="ace06-108">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="ace06-109">Para obtener más información sobre cómo crear o modificar un perfil de directiva de ancho de banda de red, vea [crear o modificar perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ace06-109">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="ace06-110">Para eliminar un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="ace06-110">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="ace06-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ace06-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ace06-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ace06-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ace06-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ace06-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ace06-114">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en Directiva de **ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="ace06-114">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="ace06-115">En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ace06-115">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ace06-116">Puede eliminar más de un perfil a la vez.</span><span class="sxs-lookup"><span data-stu-id="ace06-116">You can delete more than one profile at a time.</span></span> <span data-ttu-id="ace06-117">Para ello, presione CTRL y seleccione varios perfiles manteniendo presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="ace06-117">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="ace06-118">O bien, para seleccionar todos los perfiles, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ace06-118">Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="ace06-119">En el menú **Editar** , haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ace06-119">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="ace06-120">No se puede eliminar un perfil de directiva de ancho de banda asociado a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="ace06-120">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="ace06-121">Primero debe quitar la asociación con el sitio de red para poder eliminar el perfil.</span><span class="sxs-lookup"><span data-stu-id="ace06-121">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="ace06-122">Para obtener más información sobre cómo modificar el sitio de red, vea <A href="lync-server-2013-creating-or-modifying-network-sites.md">crear o modificar sitios de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ace06-122">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ace06-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ace06-123">See Also</span></span>


[<span data-ttu-id="ace06-124">Crear o modificar perfiles de directiva de ancho de banda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ace06-124">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="ace06-125">Ver la información de Perfil de la Directiva de ancho de banda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ace06-125">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="ace06-126">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ace06-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="ace06-127">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ace06-127">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

