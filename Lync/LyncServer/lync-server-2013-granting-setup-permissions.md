---
title: 'Lync Server 2013: concesión de permisos de instalación'
description: 'Lync Server 2013: concesión de permisos de instalación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554486"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="150b5-103">Concesión de permisos de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="150b5-103">Granting setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="150b5-104">_**Última modificación del tema:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="150b5-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="150b5-105">Puede usar el cmdlet **Grant-CsSetupPermission** para agregar permisos de lectura, escritura, ReadSPN y WriteSPN al grupo RTCUniversalServerAdmins para una unidad organizativa (OU) de Active Directory específica.</span><span class="sxs-lookup"><span data-stu-id="150b5-105">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="150b5-106">A continuación, los miembros del grupo RTCUniversalServerAdmins en esa unidad organizativa pueden instalar servidores que ejecuten Lync Server 2013 en el dominio especificado sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="150b5-106">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="150b5-107">Use el cmdlet **Test-CsSetupPermission** para comprobar los permisos configurados mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="150b5-107">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="150b5-108">Puede usar el cmdlet **REVOKE-CsSetupPermission** para quitar los permisos concedidos mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="150b5-108">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="150b5-109">Para conceder permisos de configuración</span><span class="sxs-lookup"><span data-stu-id="150b5-109">To grant setup permissions</span></span>

1.  <span data-ttu-id="150b5-110">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea conceder permisos de configuración.</span><span class="sxs-lookup"><span data-stu-id="150b5-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="150b5-111">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="150b5-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="150b5-112">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="150b5-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="150b5-113">Realizar</span><span class="sxs-lookup"><span data-stu-id="150b5-113">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="150b5-114">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="150b5-114">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="150b5-115">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="150b5-115">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="150b5-116">En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="150b5-116">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="150b5-117">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="150b5-117">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="150b5-118">Para comprobar los permisos del programa de instalación</span><span class="sxs-lookup"><span data-stu-id="150b5-118">To verify setup permissions</span></span>

1.  <span data-ttu-id="150b5-119">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de configuración que ha concedido mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="150b5-119">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="150b5-120">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="150b5-120">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="150b5-121">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="150b5-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="150b5-122">Realizar</span><span class="sxs-lookup"><span data-stu-id="150b5-122">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="150b5-123">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="150b5-123">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="150b5-124">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="150b5-124">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="150b5-125">En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="150b5-125">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="150b5-126">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="150b5-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="150b5-127">Para revocar los permisos de instalación</span><span class="sxs-lookup"><span data-stu-id="150b5-127">To revoke setup permissions</span></span>

1.  <span data-ttu-id="150b5-128">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar los permisos de instalación concedidos por el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="150b5-128">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="150b5-129">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="150b5-129">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="150b5-130">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="150b5-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="150b5-131">Realizar</span><span class="sxs-lookup"><span data-stu-id="150b5-131">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="150b5-132">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="150b5-132">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="150b5-133">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="150b5-133">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="150b5-134">En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="150b5-134">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="150b5-135">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="150b5-135">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

