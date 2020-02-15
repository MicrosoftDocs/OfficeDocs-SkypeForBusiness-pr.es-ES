---
title: 'Lync Server 2013: problemas con la prueba de topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 254fb591acca4f58bf27b300d5ead3e615e026ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="beefc-102">Problemas con la prueba de topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beefc-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beefc-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="beefc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="beefc-104">Al igual que el cmdlet **Test-CsTopology** , el analizador de procedimientos recomendados proporciona una manera de comprobar que Lync Server 2013 funciona correctamente a nivel global.</span><span class="sxs-lookup"><span data-stu-id="beefc-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="beefc-105">De forma predeterminada, el analizador de procedimientos recomendados, al igual que el cmdlet, comprueba toda la infraestructura 2013 de Lync Server, comprobando que los servicios necesarios se están ejecutando y que se han establecido los derechos y permisos de usuario adecuados para estos servicios y para la universal grupos de seguridad creados al instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="beefc-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="beefc-106">Además de comprobar la validez de Lync Server como un todo, **Test-CsTopology** también comprueba la validez de un servicio específico.</span><span class="sxs-lookup"><span data-stu-id="beefc-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="beefc-107">Para obtener información detallada sobre cómo usar el cmdlet para probar servicios específicos, consulte [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="beefc-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="beefc-108">Use la siguiente información para ayudar a resolver los problemas con su topología.</span><span class="sxs-lookup"><span data-stu-id="beefc-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beefc-p103">Dependiendo de la configuración de sus Servidores perimetrales y las configuraciones de red perimetrales relacionadas, incluso los permisos y configuraciones de firewall, el Analizador de mejores prácticas puede no acceder y registrar sus Servidores perimetrales. Si incluye los Servidores perimetrales en su registro y los informes indican que existe un problema al acceder a los Servidores perimetrales, desmarque la casilla <STRONG>Servidores perimetrales</STRONG> y ejecute nuevamente para evitar que el problema aparezca en los informes.</span><span class="sxs-lookup"><span data-stu-id="beefc-p103">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="beefc-111">Resolver problemas con su topología</span><span class="sxs-lookup"><span data-stu-id="beefc-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="beefc-112">Si la prueba de topología encuentra problemas con su topología, estos problemas son probablemente causados por problemas que se produjeron cuando publicó o habilitó su topología.</span><span class="sxs-lookup"><span data-stu-id="beefc-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="beefc-113">Cuando realiza cambios en su topología, los cambios surten efecto solo después de haberse publicado y habilitado.</span><span class="sxs-lookup"><span data-stu-id="beefc-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="beefc-114">Debe usar el generador de topologías para realizar cambios en la topología.</span><span class="sxs-lookup"><span data-stu-id="beefc-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="beefc-115">Después de realizar los cambios, puede publicar y habilitar dichos cambios mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="beefc-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="beefc-116">Al publicar los cambios, la nueva información (por ejemplo, un nuevo sitio o un nuevo rol de servidor) se escribe en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="beefc-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="beefc-117">Sin embargo, estos nuevos objetos (o los que se modificaron recientemente) no se unen inmediatamente a su topología.</span><span class="sxs-lookup"><span data-stu-id="beefc-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="beefc-118">los objetos se unen a su topología solo cuando habilita la topología actualizada.</span><span class="sxs-lookup"><span data-stu-id="beefc-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="beefc-119">Si selecciona la opción publicar en el generador de topologías, se producen estos dos pasos: los cambios se publican (es decir, se escriben en el almacén de administración central) y, a continuación, se habilita la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="beefc-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="beefc-120">De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins tienen la autorización de ejecutar el cmdlet **Publish-CsTopology** y el cmdlet **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="beefc-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="beefc-121">Sin embargo, si no se delegaron los permisos de configuración, debe haber iniciado sesión como un administrador de dominio para ejecutar **Publish-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="beefc-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="beefc-122">Para conceder a RTCUniversalServerAdmins el derecho de usar el cmdlet **Publish-CsTopology** , debe ejecutar el cmdlet **Grant-CsSetupPermission** en cada contenedor de Active Directory que contenga equipos que ejecutan servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="beefc-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="beefc-123">Para conceder a RTCUniversalServerAdmins el derecho a usar el cmdlet **enable-CsTopology** , debe ejecutar el cmdlet **set-CsSetupPermission** en cada contenedor de servicios de dominio de Active Directory que contiene equipos que ejecutan servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="beefc-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="beefc-124">Tenga en cuenta que esto se aplica a la habilitación y publicación de una topología mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="beefc-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="beefc-125">Si no ha delegado permisos mediante **set-CsSetupPermission**, solo un administrador de dominio puede habilitar y publicar una topología a través del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="beefc-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

