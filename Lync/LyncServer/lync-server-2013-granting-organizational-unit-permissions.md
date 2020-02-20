---
title: 'Lync Server 2013: concesión de permisos de unidad organizativa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be8e2e96de97444364cb07169ce4276a7983f158
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="11c02-102">Concesión de permisos de unidad organizativa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c02-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c02-103">_**Última modificación del tema:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="11c02-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="11c02-104">Puede usar el cmdlet **Grant-CsOuPermission** para conceder permisos a objetos en unidades organizativas especificadas para que los miembros de los grupos de RTC universales creados por la preparación del bosque puedan tener acceso a ellos sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="11c02-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="11c02-105">Los permisos agregados a la unidad organizativa especificada tienen los mismos permisos que el cmdlet **enable-CsAdDomain** agrega a los contenedores Computers and users durante la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="11c02-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="11c02-106">Use el cmdlet **Test-CsOuPermission** para comprobar los permisos configurados mediante el cmdlet **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="11c02-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="11c02-107">Puede usar el cmdlet **Revoke-CsOuPermission** para quitar permisos que haya concedido mediante el cmdlet **Grant-CsOuPermission**.</span><span class="sxs-lookup"><span data-stu-id="11c02-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="11c02-108">Para conceder permisos de unidades organizativas</span><span class="sxs-lookup"><span data-stu-id="11c02-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="11c02-109">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio al que desea conceder permisos de unidad organizativa.</span><span class="sxs-lookup"><span data-stu-id="11c02-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="11c02-110">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="11c02-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="11c02-111">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="11c02-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="11c02-112">Realizar</span><span class="sxs-lookup"><span data-stu-id="11c02-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="11c02-113">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="11c02-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="11c02-114">Para comprobar permisos de unidades organizativas</span><span class="sxs-lookup"><span data-stu-id="11c02-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="11c02-115">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de OU que ha concedido mediante el cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="11c02-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="11c02-116">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="11c02-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="11c02-117">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="11c02-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="11c02-118">Realizar</span><span class="sxs-lookup"><span data-stu-id="11c02-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="11c02-119">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="11c02-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="11c02-120">Para revocar permisos de unidades organizativas</span><span class="sxs-lookup"><span data-stu-id="11c02-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="11c02-121">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar los permisos de OU concedidos por el cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="11c02-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="11c02-122">Use una cuenta que sea miembro del grupo administradores de dominio o del grupo administradores de empresa si la unidad organizativa está en un dominio secundario diferente.</span><span class="sxs-lookup"><span data-stu-id="11c02-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="11c02-123">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="11c02-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="11c02-124">Realizar</span><span class="sxs-lookup"><span data-stu-id="11c02-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="11c02-125">Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="11c02-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

