---
title: Remove-CsAddressBookConfiguration para la administración de la libreta de direcciones
description: Remove-CsAddressBookConfiguration para la administración de la libreta de direcciones.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove-CsAddressBookConfiguration for Address Book management
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429705(v=OCS.15)
ms:contentKeyID: 48184258
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d513c128dfe87c5a6e92b66a6ba4e1dbdfbfb651
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555696"
---
# <a name="remove-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="5832b-103">Remove-CsAddressBookConfiguration para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5832b-103">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5832b-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5832b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5832b-p101">Quién puede ejecutar este cmdlet: De manera predeterminada, los miembros de los siguientes grupos están autorizados para ejecutar localmente el cmdlet Remove-CsAddressBookConfiguration: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5832b-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

<span data-ttu-id="5832b-107">Como implica su nombre en inglés, el cmdlet Remove-CsAddressBookConfiguration eliminará la configuración basándose en la identidad de sitio definida.</span><span class="sxs-lookup"><span data-stu-id="5832b-107">As the name implies, Remove-CsAddressBookConfiguration will remove the configuration based on the defined Site Identity.</span></span>

<span data-ttu-id="5832b-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5832b-108">For example:</span></span>

    Remove-CsAddressBookConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="5832b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5832b-109">See Also</span></span>


<span data-ttu-id="5832b-110">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5832b-110">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

