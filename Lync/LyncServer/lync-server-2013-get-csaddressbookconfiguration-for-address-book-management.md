---
title: 'Lync Server 2013: Get-CsAddressBookConfiguration para la administración de la libreta de direcciones'
description: 'Lync Server 2013: Get-CsAddressBookConfiguration para la administración de la libreta de direcciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91b96aead7b7038464f3166691a5952b9ff850dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567006"
---
# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="e83ac-103">Get-CsAddressBookConfiguration para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e83ac-103">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e83ac-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e83ac-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e83ac-p101">Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos están autorizados a ejecutar el cmdlet Get-CsAddressBookConfiguration de forma local: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e83ac-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

<span data-ttu-id="e83ac-107">El cmdlet Get-CsAddressBookConfiguration devuelve información sobre una configuración que ya existe.</span><span class="sxs-lookup"><span data-stu-id="e83ac-107">The cmdlet Get-CsAddressBookConfiguration returns information about a configuration that already exists.</span></span>

<span data-ttu-id="e83ac-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e83ac-108">For example:</span></span>

    Get-CsAddressBookConfiguration -Identity site:Redmond

<span data-ttu-id="e83ac-p102">Si se combina la funcionalidad de Get-CsAddressBookConfiguration y de Set-CsAddressBookConfiguration, el administrador puede definir qué configuraciones se van modificar y, posteriormente, aplicar estas modificaciones. Por ejemplo, si se combina:</span><span class="sxs-lookup"><span data-stu-id="e83ac-p102">Combining the functionality of Get-CsAddressBookConfiguration and Set-CsAddressBookConfiguration allows the administrator to define which configurations to modify and then apply the modifications. For example, this combined:</span></span>

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

<span data-ttu-id="e83ac-111">Se obtienen todas las configuraciones en todos los sitios y se aplica el RunTimeOfDay de 23:00 horas a las configuraciones.</span><span class="sxs-lookup"><span data-stu-id="e83ac-111">Returns all configurations in all sites and applies the RunTimeOfDay of 23:00 hours to the configurations.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e83ac-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e83ac-112">See Also</span></span>


[<span data-ttu-id="e83ac-113">Get-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="e83ac-113">Get-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

