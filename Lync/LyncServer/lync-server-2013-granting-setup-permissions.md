---
title: 'Lync Server 2013: concesión de permisos de instalación'
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
ms.openlocfilehash: 61fb0f5eac11016cf21dd8691ed9fa5f97bc804f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="80462-102">Concesión de permisos de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80462-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80462-103">_**Última modificación del tema:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="80462-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="80462-104">Puede usar el cmdlet **Grant-CsSetupPermission** para agregar permisos de lectura, escritura, ReadSPN y WriteSPN al grupo RTCUniversalServerAdmins para una unidad organizativa (OU) de Active Directory específica.</span><span class="sxs-lookup"><span data-stu-id="80462-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="80462-105">A continuación, los miembros del grupo RTCUniversalServerAdmins en esa unidad organizativa pueden instalar servidores que ejecuten Lync Server 2013 en el dominio especificado sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="80462-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="80462-106">Use el cmdlet **Test-CsSetupPermission** para comprobar los permisos configurados mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="80462-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="80462-107">Puede usar el cmdlet **REVOKE-CsSetupPermission** para quitar los permisos concedidos mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="80462-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="80462-108">Para conceder permisos de configuración</span><span class="sxs-lookup"><span data-stu-id="80462-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="80462-109">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea conceder permisos de configuración.</span><span class="sxs-lookup"><span data-stu-id="80462-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="80462-110">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="80462-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="80462-111">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="80462-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="80462-112">Realizar</span><span class="sxs-lookup"><span data-stu-id="80462-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="80462-113">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="80462-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="80462-114">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="80462-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="80462-115">En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="80462-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="80462-116">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="80462-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="80462-117">Para comprobar los permisos del programa de instalación</span><span class="sxs-lookup"><span data-stu-id="80462-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="80462-118">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de configuración que ha concedido mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="80462-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="80462-119">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="80462-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="80462-120">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="80462-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="80462-121">Realizar</span><span class="sxs-lookup"><span data-stu-id="80462-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="80462-122">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="80462-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="80462-123">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="80462-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="80462-124">En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="80462-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="80462-125">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="80462-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="80462-126">Para revocar los permisos de instalación</span><span class="sxs-lookup"><span data-stu-id="80462-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="80462-127">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar los permisos de instalación concedidos por el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="80462-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="80462-128">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="80462-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="80462-129">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="80462-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="80462-130">Realizar</span><span class="sxs-lookup"><span data-stu-id="80462-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="80462-131">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="80462-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="80462-132">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) de la unidad organizativa completa (por ejemplo, "CN = equipos, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="80462-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="80462-133">En este último caso, debe especificar un DN de unidad organizativa que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="80462-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="80462-134">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="80462-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

