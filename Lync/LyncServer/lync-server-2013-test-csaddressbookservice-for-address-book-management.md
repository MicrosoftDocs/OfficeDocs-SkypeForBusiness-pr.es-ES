---
title: 'Lync Server 2013: prueba-CsAddressBookService para la administración de libretas de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookService for Address Book management
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429720(v=OCS.15)
ms:contentKeyID: 48185206
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120a61ff03957a25cb7e6e0d09b8d3bccb11343c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="6cfcb-102">Prueba-CsAddressBookService para la administración de libretas de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cfcb-102">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cfcb-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6cfcb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6cfcb-104">¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet test-CsAddressBookService: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookService cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="6cfcb-105">Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6cfcb-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="6cfcb-106">Lync Server 2013 contiene varios cmdlets que inician comandos sintéticos para confirmar que una función o característica específica está funcionando correctamente.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-106">Lync Server 2013 contains a number of cmdlets that initiate synthetic commands to confirm that a specific function or feature is working properly.</span></span> <span data-ttu-id="6cfcb-107">Prueba-CsAddressBookService confirma que un usuario definido puede conectarse y solicitar los archivos locales del servicio Web de libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="6cfcb-107">Test-CsAddressBookService confirms that a defined user can connect and request the local files from the Address Book Web service.</span></span>

<span data-ttu-id="6cfcb-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6cfcb-108">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="6cfcb-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cfcb-109">See Also</span></span>


[<span data-ttu-id="6cfcb-110">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="6cfcb-110">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

