---
title: 'Lync Server 2013: habilitar o deshabilitar la entrada manuscrita activa'
description: 'Lync Server 2013: habilitar o deshabilitar la entrada manuscrita activa.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd22c9bf51078324cfe5e215bd154503c2d9b57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552436"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="17a28-103">Habilitar o deshabilitar la entrada manuscrita activa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17a28-103">Enable or disable hot desking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17a28-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="17a28-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="17a28-105">Puede configurar teléfonos de área común como *teléfonos de escritorio rápido*.</span><span class="sxs-lookup"><span data-stu-id="17a28-105">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="17a28-106">Con los teléfonos de escritorio activo, los usuarios pueden iniciar sesión en su propia cuenta de usuario y, una vez iniciada la sesión, usar las características de Lync Server y su propia configuración de Perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="17a28-106">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="17a28-107">La entrada manuscrita en caliente se administra mediante directivas de cliente: para habilitar o deshabilitar la entrada manuscrita activa, debe modificar las directivas de cliente que usan los teléfonos de área común.</span><span class="sxs-lookup"><span data-stu-id="17a28-107">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="17a28-108">Para obtener información detallada sobre cómo determinar las directivas de conferencia que se han asignado a los teléfonos de área común, consulte [ver información de teléfono de área común en Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="17a28-108">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="17a28-109">Use el parámetro EnableHotdesking del cmdlet **New-CSClientPolicy** o el cmdlet **set-CSClientPolicy** para habilitar o deshabilitar la entrada manuscrita activa en un teléfono, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="17a28-109">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="17a28-110">Ejecute estos cmdlets desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17a28-110">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="17a28-111">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="17a28-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="17a28-112">Habilitación de la entrada manuscrita activa</span><span class="sxs-lookup"><span data-stu-id="17a28-112">Enabling hot desking</span></span>

  - <span data-ttu-id="17a28-113">Para habilitar la entrada manuscrita activa para un teléfono de área común, debe modificar la Directiva de cliente que se ha asignado a ese teléfono (o colección de teléfonos).</span><span class="sxs-lookup"><span data-stu-id="17a28-113">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="17a28-114">Una vez que haya identificado la Directiva que debe modificarse, el siguiente paso consiste en usar el cmdlet **set-CsClientPolicy** para establecer el parámetro EnableHotdesking en true.</span><span class="sxs-lookup"><span data-stu-id="17a28-114">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="17a28-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a28-115">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="17a28-116">Como alternativa, puede usar el cmdlet **New-CsClientPolicy** para crear una nueva Directiva de cliente que permita la entrada manuscrita activa.</span><span class="sxs-lookup"><span data-stu-id="17a28-116">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="17a28-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a28-117">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="17a28-118">Una vez creada esta Directiva, debe asignarla a los teléfonos de área común adecuados.</span><span class="sxs-lookup"><span data-stu-id="17a28-118">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="17a28-119">Para obtener más información, consulte <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">asignar directivas en Lync Server 2013 a un teléfono de área común</A>.</span><span class="sxs-lookup"><span data-stu-id="17a28-119">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="17a28-120">Deshabilitar la entrada manuscrita activa</span><span class="sxs-lookup"><span data-stu-id="17a28-120">Disabling hot desking</span></span>

  - <span data-ttu-id="17a28-121">Para deshabilitar la entrada manuscrita activa para un teléfono de área común, restablezca el parámetro EnableHotdesking del cmdlet **set-CsClientPolicy** en el valor predeterminado de false.</span><span class="sxs-lookup"><span data-stu-id="17a28-121">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="17a28-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="17a28-122">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="17a28-123">Para obtener más información, consulte los temas de ayuda del cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) y el cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="17a28-123">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

