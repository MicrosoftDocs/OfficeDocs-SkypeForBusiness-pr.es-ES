---
title: 'Lync Server 2013: Concesión de permisos de instalación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751ec9ba024780344596bfc0513c15f7e9eafec7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="f0df6-102">Concesión de permisos de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0df6-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0df6-103">_**Última modificación del tema:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="f0df6-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="f0df6-104">Puede usar el cmdlet **Grant-CsSetupPermission** para agregar permisos de lectura, escritura, ReadSPN y WriteSPN al grupo RTCUniversalServerAdmins para una unidad organizativa (OU) específica de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0df6-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="f0df6-105">A continuación, los miembros del grupo RTCUniversalServerAdmins de esa unidad organizativa pueden instalar servidores que ejecuten Lync Server 2013 en el dominio especificado sin ser miembros del grupo administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="f0df6-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="f0df6-106">Use el cmdlet **Test-CsSetupPermission** para comprobar los permisos que configuró mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="f0df6-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="f0df6-107">Puede usar el cmdlet **REVOKE-CsSetupPermission** para quitar los permisos que ha otorgado mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="f0df6-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="f0df6-108">Para conceder permisos de configuración</span><span class="sxs-lookup"><span data-stu-id="f0df6-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="f0df6-109">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea conceder permisos de configuración.</span><span class="sxs-lookup"><span data-stu-id="f0df6-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="f0df6-110">Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="f0df6-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="f0df6-111">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0df6-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f0df6-112">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="f0df6-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="f0df6-113">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="f0df6-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="f0df6-114">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) completo de la uo (por ejemplo, "CN = Computers, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="f0df6-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="f0df6-115">En este último caso, debe especificar un DN de Uo que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="f0df6-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="f0df6-116">Si no especifica el parámetro domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="f0df6-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="f0df6-117">Para comprobar los permisos de configuración</span><span class="sxs-lookup"><span data-stu-id="f0df6-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="f0df6-118">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de configuración que ha otorgado mediante el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="f0df6-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="f0df6-119">Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="f0df6-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="f0df6-120">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0df6-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f0df6-121">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="f0df6-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="f0df6-122">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="f0df6-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="f0df6-123">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) completo de la uo (por ejemplo, "CN = Computers, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="f0df6-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="f0df6-124">En este último caso, debe especificar un DN de Uo que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="f0df6-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="f0df6-125">Si no especifica el parámetro domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="f0df6-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="f0df6-126">Para revocar los permisos de configuración</span><span class="sxs-lookup"><span data-stu-id="f0df6-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="f0df6-127">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar los permisos de configuración que ha otorgado el cmdlet **Grant-CsSetupPermission** .</span><span class="sxs-lookup"><span data-stu-id="f0df6-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="f0df6-128">Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="f0df6-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="f0df6-129">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f0df6-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f0df6-130">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="f0df6-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="f0df6-131">Puede especificar el parámetro ComputerOu en relación con el contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN = Computers).</span><span class="sxs-lookup"><span data-stu-id="f0df6-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="f0df6-132">Como alternativa, puede especificar este parámetro como el nombre distintivo (DN) completo de la uo (por ejemplo, "CN = Computers, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="f0df6-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="f0df6-133">En este último caso, debe especificar un DN de Uo que sea coherente con el dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="f0df6-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="f0df6-134">Si no especifica el parámetro domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="f0df6-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

