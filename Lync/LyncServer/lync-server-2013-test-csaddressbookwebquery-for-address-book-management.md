---
title: 'Lync Server 2013: test-CsAddressBookWebQuery para la administración de la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f03ead82f4ec5ebcb09c3bbfa1bba6206b8333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="29c8a-102">Test-CsAddressBookWebQuery para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29c8a-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29c8a-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="29c8a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="29c8a-104">Quién puede ejecutar este cmdlet: de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet test-CsAddressBookWebQuery: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="29c8a-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="29c8a-105">Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se asignó este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), inicie el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29c8a-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="29c8a-106">De forma similar a la transacción sintética test-CsAddressBookService, test-CsAddressBookWebQuery realiza una consulta en la consulta Web de la libreta de direcciones para asegurarse de que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="29c8a-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="29c8a-107">El cmdlet se conectará a la autenticación del vale web y presentará las credenciales especificadas en – UserCredential.</span><span class="sxs-lookup"><span data-stu-id="29c8a-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="29c8a-108">Si se autentica, el cmdlet presenta la información – TargetSipAddress.</span><span class="sxs-lookup"><span data-stu-id="29c8a-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="29c8a-109">El cmdlet debe informar de que se ha realizado correctamente si pudo recuperar la información sobre el contacto.</span><span class="sxs-lookup"><span data-stu-id="29c8a-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="29c8a-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29c8a-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="29c8a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="29c8a-111">See Also</span></span>


[<span data-ttu-id="29c8a-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="29c8a-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

