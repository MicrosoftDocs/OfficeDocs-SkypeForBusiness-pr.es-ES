---
title: 'Lync Server 2013: concesión de permisos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20679f910ead1f1b7cab45fde658b38233c644f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="d1dcb-102">Concesión de permisos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1dcb-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1dcb-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="d1dcb-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="d1dcb-104">Para el programa de instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa (OU) de Active Directory específica, habilitando a los miembros del grupo RTCUniversalServerAdmins en dicha unidad organizativa que instalen Lync Server 2013 en el dominio especificado.</span><span class="sxs-lookup"><span data-stu-id="d1dcb-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="d1dcb-105">Cuando se conceden permisos para una unidad organizativa, se conceden los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="d1dcb-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="d1dcb-106">Leer</span><span class="sxs-lookup"><span data-stu-id="d1dcb-106">Read</span></span>

  - <span data-ttu-id="d1dcb-107">Escritura</span><span class="sxs-lookup"><span data-stu-id="d1dcb-107">Write</span></span>

  - <span data-ttu-id="d1dcb-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="d1dcb-108">ReadSPN</span></span>

  - <span data-ttu-id="d1dcb-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="d1dcb-109">WriteSPN</span></span>

<span data-ttu-id="d1dcb-110">Para la administración, puede agregar permisos a las OU especificadas, de modo que los miembros de los grupos universales RTC que se han creado durante la preparación del bosque pueden obtener acceso a las OU sin ser miembros del grupo de administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="d1dcb-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="d1dcb-111">Los permisos agregados a la OU especificada son los mismos permisos que los que el cmdlet **Enable-CsAdDomain** agrega a los equipos y los contenedores de OU de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d1dcb-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d1dcb-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d1dcb-112">In This Section</span></span>

  - [<span data-ttu-id="d1dcb-113">Concesión de permisos de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1dcb-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="d1dcb-114">Concesión de permisos de unidad organizativa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1dcb-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

