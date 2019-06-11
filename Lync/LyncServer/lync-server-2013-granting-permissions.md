---
title: 'Lync Server 2013: Conceder permisos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c8afde42a231124648824fbf8fbae07b0beedc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="4ad96-102">Conceder permisos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad96-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ad96-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="4ad96-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="4ad96-104">Para la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa de Active Directory específica, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esa OU instalar Lync Server 2013 en el dominio especificado.</span><span class="sxs-lookup"><span data-stu-id="4ad96-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="4ad96-105">Al conceder permisos para una unidad organizativa, se conceden los permisos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ad96-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="4ad96-106">Consulte</span><span class="sxs-lookup"><span data-stu-id="4ad96-106">Read</span></span>

  - <span data-ttu-id="4ad96-107">Graba</span><span class="sxs-lookup"><span data-stu-id="4ad96-107">Write</span></span>

  - <span data-ttu-id="4ad96-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="4ad96-108">ReadSPN</span></span>

  - <span data-ttu-id="4ad96-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="4ad96-109">WriteSPN</span></span>

<span data-ttu-id="4ad96-110">Para la administración, puede Agregar permisos a unidades organizativas específicas para que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin necesidad de ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="4ad96-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="4ad96-111">Los permisos agregados a la unidad organizativa especificada son los mismos permisos que el cmdlet **enable-CsAdDomain** agrega a los contenedores de ou de equipos y usuarios.</span><span class="sxs-lookup"><span data-stu-id="4ad96-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4ad96-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4ad96-112">In This Section</span></span>

  - [<span data-ttu-id="4ad96-113">Concesión de permisos de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad96-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="4ad96-114">Conceder permisos de unidad organizativa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ad96-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

