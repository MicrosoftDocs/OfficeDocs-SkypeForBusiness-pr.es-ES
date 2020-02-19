---
title: 'Lync Server 2013: New-CsClientPolicy para la administración de la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78d63b29ea1198bfee91437a1e6dcd70c1be0a45
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="c1897-102">New-CsClientPolicy para la administración de la libreta de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1897-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1897-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c1897-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c1897-104">Quién puede ejecutar este cmdlet: Generalmente, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-CsClientPolicy: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c1897-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="c1897-105">Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se asignó este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), inicie el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c1897-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="c1897-106">El cmdlet New-CsClientPolicy define un gran número de opciones de configuración para aprovisionar clientes para las características que están disponibles en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1897-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="c1897-107">El parámetro AddressBookAvailability es relevante para el servicio de Libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="c1897-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="c1897-108">Este parámetro, que repercute directamente en las opciones disponibles para los clientes, presenta tres opciones:</span><span class="sxs-lookup"><span data-stu-id="c1897-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="c1897-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="c1897-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="c1897-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="c1897-110">WebSearchOnly</span></span>

  - <span data-ttu-id="c1897-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="c1897-111">FileDownloadOnly</span></span>

<span data-ttu-id="c1897-p103">Cuando se define, determina cómo acceden los clientes a la Libreta de direcciones. Si define este parámetro, defina una de las opciones. Si no modifica esta configuración, permanecerá en vigor la opción predeterminada, WebSearchAndFileDownload.</span><span class="sxs-lookup"><span data-stu-id="c1897-p103">When defined, it determines how the Address Book is accessed by clients. If you define this parameter, you must define one of the options. If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="c1897-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c1897-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="c1897-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1897-116">See Also</span></span>


[<span data-ttu-id="c1897-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="c1897-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

