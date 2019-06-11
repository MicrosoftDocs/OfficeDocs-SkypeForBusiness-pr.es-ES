---
title: 'Lync Server 2013: Remove-CsWebServiceConfiguration para la administración de libretas de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove-CsWebServiceConfiguration for Address Book management
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429713(v=OCS.15)
ms:contentKeyID: 48184848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 206c47ebb272f6ab637f4f07e9bb54a7fd1d40e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f449a-102">Remove-CsWebServiceConfiguration para la administración de libretas de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f449a-102">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f449a-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f449a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f449a-104">¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Remove-CsWebServiceConfiguration de forma local: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f449a-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsWebServiceConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="f449a-105">Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f449a-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

<span data-ttu-id="f449a-106">El cmdlet Remove-CsWebServiceConfiguration permite a un administrador quitar una configuración de servicios Web creada previamente.</span><span class="sxs-lookup"><span data-stu-id="f449a-106">The Remove-CsWebServiceConfiguration cmdlet allows an administrator to remove a previously created Web Services configuration.</span></span> <span data-ttu-id="f449a-107">El cmdlet no puede quitar la configuración de los servicios web globales.</span><span class="sxs-lookup"><span data-stu-id="f449a-107">The cmdlet cannot remove the global Web Services configuration.</span></span>

<span data-ttu-id="f449a-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f449a-108">For example:</span></span>

    Remove-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a><span data-ttu-id="f449a-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f449a-109">See Also</span></span>


[<span data-ttu-id="f449a-110">Remove-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="f449a-110">Remove-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

