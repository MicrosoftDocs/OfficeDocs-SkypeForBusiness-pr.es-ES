---
title: 'Lync Server 2013: nuevo-ClientPolicy para la administración de libretas de direcciones'
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
ms.openlocfilehash: 3f68f6cfa2fde4d1e5a2bc58a36478a60060dd5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="0bec3-102">Nuevo: ClientPolicy para la administración de libretas de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bec3-102">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bec3-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0bec3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0bec3-104">¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet New-ClientPolicy: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0bec3-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsClientPolicy cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="0bec3-105">Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0bec3-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

<span data-ttu-id="0bec3-106">El cmdlet New-ClientPolicy define un gran número de opciones para aprovisionar los clientes de las características que están disponibles en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bec3-106">The cmdlet New-CsClientPolicy defines a large number of settings for provisioning clients for features that are available in Lync Server 2013.</span></span> <span data-ttu-id="0bec3-107">Para el servicio de libreta de direcciones, el parámetro AddressBookAvailability es de interés.</span><span class="sxs-lookup"><span data-stu-id="0bec3-107">For the Address Book Service, the parameter AddressBookAvailability is of interest.</span></span> <span data-ttu-id="0bec3-108">Este parámetro, que afecta directamente a las opciones disponibles para los clientes, tiene tres opciones posibles:</span><span class="sxs-lookup"><span data-stu-id="0bec3-108">This parameter, which directly impacts the options available to clients, has three possible options:</span></span>

  - <span data-ttu-id="0bec3-109">WebSearchAndFileDownload</span><span class="sxs-lookup"><span data-stu-id="0bec3-109">WebSearchAndFileDownload</span></span>

  - <span data-ttu-id="0bec3-110">WebSearchOnly</span><span class="sxs-lookup"><span data-stu-id="0bec3-110">WebSearchOnly</span></span>

  - <span data-ttu-id="0bec3-111">FileDownloadOnly</span><span class="sxs-lookup"><span data-stu-id="0bec3-111">FileDownloadOnly</span></span>

<span data-ttu-id="0bec3-112">Cuando se define, determina cómo se obtiene acceso a la libreta de direcciones por parte de los clientes.</span><span class="sxs-lookup"><span data-stu-id="0bec3-112">When defined, it determines how the Address Book is accessed by clients.</span></span> <span data-ttu-id="0bec3-113">Si define este parámetro, debe definir una de las opciones.</span><span class="sxs-lookup"><span data-stu-id="0bec3-113">If you define this parameter, you must define one of the options.</span></span> <span data-ttu-id="0bec3-114">Si no modifica esta configuración, el WebSearchAndFileDownload predeterminado permanece en vigor.</span><span class="sxs-lookup"><span data-stu-id="0bec3-114">If you do not modify this setting, the default WebSearchAndFileDownload remains in effect.</span></span>

<span data-ttu-id="0bec3-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0bec3-115">For example:</span></span>

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a><span data-ttu-id="0bec3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bec3-116">See Also</span></span>


[<span data-ttu-id="0bec3-117">New-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0bec3-117">New-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

