---
title: 'Lync Server 2013: New-CsWebServiceConfiguration para la administración de la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsWebServiceConfiguration for Address Book management
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429703(v=OCS.15)
ms:contentKeyID: 48184067
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fa02c95a3b6bf149c5b3eb5e893ad62dc45dbb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="032a4-102">New-CsWebServiceConfiguration para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="032a4-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="032a4-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="032a4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="032a4-p101">Quién puede ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-CsWebServiceConfiguration localmente: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="032a4-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="032a4-p102">El cmdlet New-CsWebServiceConfiguration define una nueva configuración de los servicios web de su organización. El ámbito de la configuración de los servicios web solo puede ser de nivel de sitio o de nivel de servicio. No puede crear una configuración de servicios web de nivel global. El atributo EnableGroupExansion resulta de especial interés para la libreta de direcciones. Si se establece en True, los servicios web pueden responder a solicitudes de expansión de grupo.</span><span class="sxs-lookup"><span data-stu-id="032a4-p102">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization. The scope for the Web Services configuration can only be at the site or service level. It cannot create a new Web Services configuration at the global level. Specifically of interest to the Address Book is the EnableGroupExansion attribute. If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="032a4-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="032a4-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="032a4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="032a4-112">See Also</span></span>


[<span data-ttu-id="032a4-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="032a4-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

