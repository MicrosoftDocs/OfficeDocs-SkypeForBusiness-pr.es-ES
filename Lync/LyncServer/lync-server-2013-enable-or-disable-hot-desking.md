---
title: 'Lync Server 2013: habilitar o deshabilitar la entrada de lápiz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5d9f2d168a06b5624375dcd005da58b4d3d5fd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="9abf1-102">Habilitar o deshabilitar la entrada manuscrita en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9abf1-102">Enable or disable hot desking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9abf1-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9abf1-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9abf1-104">Puedes configurar teléfonos de área común como *teléfonos de escritorio*.</span><span class="sxs-lookup"><span data-stu-id="9abf1-104">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="9abf1-105">Con los teléfonos de escritorio activo, los usuarios pueden iniciar sesión en su propia cuenta de usuario y, una vez que hayan iniciado sesión, usar las características de Lync Server y su propia configuración de Perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="9abf1-105">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="9abf1-106">La entrada de lápiz en caliente se administra mediante directivas de cliente: para habilitar o deshabilitar la entrada manuscrita activa, debe modificar las directivas de cliente que usan sus teléfonos de área común.</span><span class="sxs-lookup"><span data-stu-id="9abf1-106">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="9abf1-107">Para obtener más información sobre cómo determinar las directivas de conferencia que se han asignado a los teléfonos de área común, vea [ver información de los teléfonos de áreas comunes en Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="9abf1-107">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="9abf1-108">Use el parámetro EnableHotdesking del cmdlet **New-ClientPolicy** o el cmdlet **set-ClientPolicy** para habilitar o deshabilitar la entrada de lápiz caliente en un teléfono, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="9abf1-108">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="9abf1-109">Ejecute estos cmdlets desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9abf1-109">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9abf1-110">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="9abf1-110">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="9abf1-111">Cómo habilitar las entradas de lápiz en caliente</span><span class="sxs-lookup"><span data-stu-id="9abf1-111">Enabling hot desking</span></span>

  - <span data-ttu-id="9abf1-112">Para habilitar la entrada de lápiz para un teléfono de área común, debe modificar la Directiva de cliente que se ha asignado a ese teléfono (o colección de teléfonos).</span><span class="sxs-lookup"><span data-stu-id="9abf1-112">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="9abf1-113">Una vez identificada la Directiva que debe modificarse, el siguiente paso consiste en usar el cmdlet **set-ClientPolicy** para establecer el parámetro EnableHotdesking en true.</span><span class="sxs-lookup"><span data-stu-id="9abf1-113">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="9abf1-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9abf1-114">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="9abf1-115">También puede usar el cmdlet **New-ClientPolicy** para crear una nueva Directiva de cliente que permita la entrada de lápiz.</span><span class="sxs-lookup"><span data-stu-id="9abf1-115">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="9abf1-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9abf1-116">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9abf1-117">Después de crear esta Directiva, debe asignarla a los teléfonos de área común que corresponda.</span><span class="sxs-lookup"><span data-stu-id="9abf1-117">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="9abf1-118">Para obtener más información, vea <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">asignar directivas en Lync Server 2013 a un teléfono de área común</A>.</span><span class="sxs-lookup"><span data-stu-id="9abf1-118">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="9abf1-119">Deshabilitar la entrada de lápiz</span><span class="sxs-lookup"><span data-stu-id="9abf1-119">Disabling hot desking</span></span>

  - <span data-ttu-id="9abf1-120">Para deshabilitar la entrada de lápiz para un teléfono de área común, restablezca el parámetro EnableHotdesking del cmdlet **set-ClientPolicy** al valor predeterminado de falso.</span><span class="sxs-lookup"><span data-stu-id="9abf1-120">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="9abf1-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9abf1-121">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="9abf1-122">Para obtener más información, consulte los temas de ayuda para el cmdlet [New-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) y el cmdlet [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="9abf1-122">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

