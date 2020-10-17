---
title: 'Lync Server 2013: Delegación de permisos de configuración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453da166895c79cafe9f9637163e93a63ebccd75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504287"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="29711-102">Delegación de permisos de instalación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29711-102">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29711-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="29711-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="29711-104">Si no desea conceder la pertenencia al grupo administradores del dominio a los usuarios o grupos que están implementando Lync Server 2013, puede habilitar los miembros del grupo RTCUniversalServerAdmins para que ejecuten el cmdlet **enable-CsTopology**de   Windows PowerShell en los servidores que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29711-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="29711-105">De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins no pueden ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="29711-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="29711-106">Para conceder derechos y permisos de administrador para ejecutar **enable-CsTopology** en servidores que ejecuten Lync Server, use el cmdlet **Grant-CsSetupPermission** y especifique una unidad organizativa (OU) en la que se encuentren los objetos de equipo del servidor que ejecuta Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29711-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="29711-107">La preparación del dominio que se produce al instalar Lync Server no agrega automáticamente los permisos que permiten a los miembros del grupo RTCUniversalServerAdmins ejecutar el cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="29711-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="29711-108">Esto quiere decir que, de forma predeterminada, debe ser un administrador del dominio para poder habilitar una topología.</span><span class="sxs-lookup"><span data-stu-id="29711-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="29711-109">Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho para habilitar una topología, debe ejecutar el cmdlet Grant-CsSetupPermissions.</span><span class="sxs-lookup"><span data-stu-id="29711-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="29711-110">Además, tendrá que ejecutar este cmdlet en cada contenedor de Active Directory que contenga equipos que ejecuten Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29711-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="29711-111">Tenga en cuenta que este cmdlet solo concede permisos al grupo RTCUniversalServerAdmins; el cmdlet no se puede usar para conceder permisos a otros grupos de seguridad o a usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="29711-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29711-112"><STRONG>Enable-CsTopology</STRONG> es el cmdlet Key que permite a los miembros del grupo RTCUniversalServerAdmins configurar e implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29711-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="29711-113">Para conceder al grupo RTCUniversalServerAdmins la posibilidad de ejecutar Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="29711-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="29711-114">Inicie sesión en un servidor como miembro del grupo Admins. del dominio para el dominio en que el usuario delegado ejecutará **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="29711-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="29711-115">Abra el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29711-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="29711-116">El shell de administración de Lync Server 2013 se instala automáticamente en cada servidor front-end o en cualquier equipo en el que se hayan instalado las herramientas administrativas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29711-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="29711-117">Para obtener más información sobre el shell de administración de Lync Server 2013, consulte Shell de administración de Lync [server 2013](lync-server-2013-lync-server-management-shell.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="29711-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="29711-118">Ejecute el siguiente cmdlet desde el shell de administración de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="29711-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29711-119">Si la unidad organizativa no es de nivel superior, debe proporcionar el nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="29711-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="29711-120">En el ejemplo siguiente, la unidad organizativa es "Lync Servers" y se encuentra en el dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="29711-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

