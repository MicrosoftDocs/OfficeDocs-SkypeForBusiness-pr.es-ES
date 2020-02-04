---
title: 'Lync Server 2013: nuevo-CsWebServiceConfiguration para la administración de libretas de direcciones'
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
ms.openlocfilehash: 434c9a7c4ded9516cd930bbaa9bba72873b15a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="01e8b-102">Nuevo: CsWebServiceConfiguration para la administración de libretas de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e8b-102">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01e8b-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="01e8b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="01e8b-104">¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-CsWebServiceConfiguration de forma local: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="01e8b-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="01e8b-105">Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="01e8b-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

<span data-ttu-id="01e8b-106">El cmdlet New-CsWebServiceConfiguration define una nueva configuración para los servicios Web de su organización.</span><span class="sxs-lookup"><span data-stu-id="01e8b-106">The cmdlet New-CsWebServiceConfiguration defines a new configuration for Web Services in your organization.</span></span> <span data-ttu-id="01e8b-107">El ámbito de la configuración de los servicios web solo puede encontrarse en el nivel de sitio o de servicio.</span><span class="sxs-lookup"><span data-stu-id="01e8b-107">The scope for the Web Services configuration can only be at the site or service level.</span></span> <span data-ttu-id="01e8b-108">No puede crear una nueva configuración de servicios web en el nivel global.</span><span class="sxs-lookup"><span data-stu-id="01e8b-108">It cannot create a new Web Services configuration at the global level.</span></span> <span data-ttu-id="01e8b-109">Específicamente de interés para la libreta de direcciones es el atributo EnableGroupExansion.</span><span class="sxs-lookup"><span data-stu-id="01e8b-109">Specifically of interest to the Address Book is the EnableGroupExansion attribute.</span></span> <span data-ttu-id="01e8b-110">Si se establece en true, los servicios Web pueden responder a las solicitudes de expansión de grupo.</span><span class="sxs-lookup"><span data-stu-id="01e8b-110">If set to True, the Web Services can respond to requests for group expansion.</span></span>

<span data-ttu-id="01e8b-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="01e8b-111">For example:</span></span>

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

<div>

## <a name="see-also"></a><span data-ttu-id="01e8b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="01e8b-112">See Also</span></span>


[<span data-ttu-id="01e8b-113">New-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="01e8b-113">New-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

