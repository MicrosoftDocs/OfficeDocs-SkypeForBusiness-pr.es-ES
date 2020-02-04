---
title: 'Lync Server 2013: Conceder permisos de unidad organizativa'
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
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="23d2e-102">Conceder permisos de unidad organizativa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23d2e-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23d2e-103">_**Última modificación del tema:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="23d2e-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="23d2e-104">Puede usar el cmdlet **Grant-CsOuPermission** para conceder permisos a los objetos de unidades organizativas (OU) especificadas de modo que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a ellos sin ser miembros del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="23d2e-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="23d2e-105">Los permisos agregados a la unidad organizativa especificada son los mismos permisos que el cmdlet **enable-CsAdDomain** agrega a los contenedores de equipos y usuarios durante la preparación del dominio.</span><span class="sxs-lookup"><span data-stu-id="23d2e-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="23d2e-106">Use el cmdlet **Test-CsOuPermission** para comprobar los permisos que configuró mediante el cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="23d2e-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="23d2e-107">Puede usar el cmdlet **REVOKE-CsOuPermission** para quitar los permisos que ha otorgado mediante el cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="23d2e-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="23d2e-108">Para conceder permisos de Uo</span><span class="sxs-lookup"><span data-stu-id="23d2e-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="23d2e-109">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio al que desee conceder permisos de Uo.</span><span class="sxs-lookup"><span data-stu-id="23d2e-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="23d2e-110">Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="23d2e-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="23d2e-111">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="23d2e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23d2e-112">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="23d2e-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="23d2e-113">Si no especifica el parámetro domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="23d2e-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="23d2e-114">Para comprobar los permisos de Uo</span><span class="sxs-lookup"><span data-stu-id="23d2e-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="23d2e-115">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea comprobar los permisos de Uo que ha otorgado mediante el cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="23d2e-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="23d2e-116">Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="23d2e-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="23d2e-117">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="23d2e-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23d2e-118">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="23d2e-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="23d2e-119">Si no especifica el parámetro domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="23d2e-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="23d2e-120">Para revocar permisos de Uo</span><span class="sxs-lookup"><span data-stu-id="23d2e-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="23d2e-121">Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que desea revocar permisos de OU que ha otorgado el cmdlet **Grant-CsOuPermission** .</span><span class="sxs-lookup"><span data-stu-id="23d2e-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="23d2e-122">Use una cuenta que sea miembro del grupo administradores del dominio o del grupo administradores de la organización si la OU está en otro dominio secundario.</span><span class="sxs-lookup"><span data-stu-id="23d2e-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="23d2e-123">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="23d2e-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23d2e-124">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="23d2e-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="23d2e-125">Si no especifica el parámetro domain, el valor predeterminado es el dominio local.</span><span class="sxs-lookup"><span data-stu-id="23d2e-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

