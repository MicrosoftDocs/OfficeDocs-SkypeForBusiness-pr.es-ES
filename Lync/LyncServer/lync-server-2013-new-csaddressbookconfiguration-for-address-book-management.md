---
title: 'Lync Server 2013: New-CsAddressBookConfiguration para la administración de la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88c2cbeb3ff4b9f75a0bce77543e8094ba8a7a89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508837"
---
# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="62e31-102">New-CsAddressBookConfiguration para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62e31-102">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62e31-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="62e31-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="62e31-104">Quiénes pueden ejecutar este cmdlet: De forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-CsAddressBookConfiguration localmente: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="62e31-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsAddressBookConfiguration cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="62e31-105">Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se asignó este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), inicie el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="62e31-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

<span data-ttu-id="62e31-106">El cmdlet New-CsAddressBookConfiguration crea una nueva configuración para administrar el comportamiento de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="62e31-106">The New-CsAddressBookConfiguration cmdlet creates a new configuration to manage the behavior of the Address book.</span></span> <span data-ttu-id="62e31-107">Específica de este cmdlet es la capacidad de definir si el servicio de libreta de direcciones crea los archivos de descarga del cliente, cómo y si se usan las reglas de normalización, cuánto tiempo se conservan los archivos Delta y Delta compactos, el tamaño del archivo Delta antes de incorporar una nueva creación completa de archivos, la hora del día en que se crea la libreta de direcciones del</span><span class="sxs-lookup"><span data-stu-id="62e31-107">Specific to this cmdlet is the ability to define if the Address Book Service creates the client download files, how and if normalization rules are used, how long to retain delta and compact delta files, delta file size before incorporating a new full file creation, what time of day the full file Address Book is created, and what the internal should be for synchronization of information in the User database.</span></span>

<span data-ttu-id="62e31-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="62e31-108">For example:</span></span>

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a><span data-ttu-id="62e31-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="62e31-109">See Also</span></span>


[<span data-ttu-id="62e31-110">New-CsAddressBookConfiguration</span><span class="sxs-lookup"><span data-stu-id="62e31-110">New-CsAddressBookConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

