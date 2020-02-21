---
title: 'Lync Server 2013: get-CsWebServiceConfiguration para la administración de la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc131bdcd4713b4bdf5971825675dc770da8ec3f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="3226e-102">Get-CsWebServiceConfiguration para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3226e-102">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3226e-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3226e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3226e-p101">Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Get-CsWebServiceConfiguration localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3226e-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsWebServiceConfiguration cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

<span data-ttu-id="3226e-p102">Get-CsWebServiceConfiguration devuelve información de la configuración de los servicios web que se encuentran actualmente en uso en su organización. Para los servicios de libreta de direcciones es interesante el estado de la función de expansión de lista de distribución. Si el atributo EnableGroupExpansion es True, significa que su organización admite la expansión de grupos.</span><span class="sxs-lookup"><span data-stu-id="3226e-p102">Get-CsWebServiceConfiguration returns information of the Web Services configuration currently in use in your organization. Of interest to the Address Book Services is the status of Distribution List Expansion function. If the attribute EnableGroupExpansion is True, your organization currently allows group expansion.</span></span>

<span data-ttu-id="3226e-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3226e-109">For example:</span></span>

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="3226e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3226e-110">See Also</span></span>


[<span data-ttu-id="3226e-111">Get-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="3226e-111">Get-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

