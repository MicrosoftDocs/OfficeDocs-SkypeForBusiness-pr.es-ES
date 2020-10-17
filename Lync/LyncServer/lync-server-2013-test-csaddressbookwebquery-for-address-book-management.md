---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery para la administración de la libreta de direcciones'
description: 'Lync Server 2013: Test-CsAddressBookWebQuery para la administración de la libreta de direcciones.'
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
ms.openlocfilehash: c7448733ed1477d36b887648154d66c96f9e6d0b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547446"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="f391a-103">Test-CsAddressBookWebQuery para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f391a-103">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f391a-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f391a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f391a-105">Quién puede ejecutar este cmdlet: de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Test-CsAddressBookWebQuery: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f391a-105">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="f391a-106">Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se asignó este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), inicie el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f391a-106">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="f391a-107">De forma similar a la transacción sintética Test-CsAddressBookService, Test-CsAddressBookWebQuery realiza una consulta en la consulta Web de la libreta de direcciones para asegurarse de que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="f391a-107">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="f391a-108">El cmdlet se conectará a la autenticación del vale web y presentará las credenciales especificadas en – UserCredential.</span><span class="sxs-lookup"><span data-stu-id="f391a-108">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="f391a-109">Si se autentica, el cmdlet presenta la información – TargetSipAddress.</span><span class="sxs-lookup"><span data-stu-id="f391a-109">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="f391a-110">El cmdlet debe informar de que se ha realizado correctamente si pudo recuperar la información sobre el contacto.</span><span class="sxs-lookup"><span data-stu-id="f391a-110">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="f391a-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f391a-111">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="f391a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f391a-112">See Also</span></span>


[<span data-ttu-id="f391a-113">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="f391a-113">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

