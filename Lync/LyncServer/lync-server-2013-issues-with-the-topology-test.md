---
title: 'Lync Server 2013: problemas con la topología de la prueba'
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
ms.openlocfilehash: a0492f53692230bf02b3b66d91ba7fdf14b01c23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="186d6-102">Problemas con la prueba de topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="186d6-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="186d6-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="186d6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="186d6-104">Al igual que el cmdlet **Test-CsTopology** , el analizador de procedimientos recomendados proporciona una forma de comprobar que Lync Server 2013 está funcionando correctamente en un nivel global.</span><span class="sxs-lookup"><span data-stu-id="186d6-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="186d6-105">De forma predeterminada, el analizador de procedimientos recomendados, como el cmdlet, comprueba toda la infraestructura de Lync Server 2013, verifica que los servicios necesarios se estén ejecutando y que se hayan establecido los derechos y permisos de usuario apropiados para estos servicios y para la aplicación universal. grupos de seguridad creados al instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="186d6-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="186d6-106">Además de comprobar la validez de Lync Server como un todo, **Test-CsTopology** también comprueba la validez de un servicio específico.</span><span class="sxs-lookup"><span data-stu-id="186d6-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="186d6-107">Para obtener detalles sobre el uso del cmdlet para probar servicios específicos, consulte [prueba-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="186d6-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="186d6-108">Use la siguiente información para ayudar a resolver problemas con su topología.</span><span class="sxs-lookup"><span data-stu-id="186d6-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="186d6-109">En función de la configuración de los servidores perimetrales y de cualquier configuración de red perimetral relacionada, incluyendo la configuración y los permisos del firewall, es posible que el analizador de procedimientos recomendados no pueda tener acceso a los servidores perimetrales y explorarlos.</span><span class="sxs-lookup"><span data-stu-id="186d6-109">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="186d6-110">Si incluye servidores perimetrales en el análisis y los informes indican que hay un problema de acceso a los servidores perimetrales, desactive la casilla <STRONG>servidores perimetrales</STRONG> y ejecute el examen de nuevo para evitar que se muestre el problema en los informes.</span><span class="sxs-lookup"><span data-stu-id="186d6-110">If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="186d6-111">Solución de problemas con su topología</span><span class="sxs-lookup"><span data-stu-id="186d6-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="186d6-112">Si la prueba de topología encontró problemas con su topología, probablemente se deba a problemas que se produjeron al publicar o habilitar su topología.</span><span class="sxs-lookup"><span data-stu-id="186d6-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="186d6-113">Cuando realice cambios en su topología, los cambios solo se aplicarán cuando se hayan publicado y habilitado.</span><span class="sxs-lookup"><span data-stu-id="186d6-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="186d6-114">Debe usar topología Builder para realizar cambios de topología.</span><span class="sxs-lookup"><span data-stu-id="186d6-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="186d6-115">Después de realizar los cambios, puede publicar y habilitar esos cambios con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="186d6-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="186d6-116">Al publicar los cambios, la nueva información (por ejemplo, un nuevo sitio o una nueva función de servidor) se escribe en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="186d6-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="186d6-117">Sin embargo, estos nuevos objetos (o los recién modificados) no se unen inmediatamente a su topología.</span><span class="sxs-lookup"><span data-stu-id="186d6-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="186d6-118">Los objetos se unen a su topología solo cuando habilita la topología actualizada.</span><span class="sxs-lookup"><span data-stu-id="186d6-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="186d6-119">Si selecciona la opción de publicación en el generador de topología, se realizan ambos pasos: los cambios se publican (es decir, se escriben en el almacén de administración central) y, a continuación, se habilita la nueva topología.</span><span class="sxs-lookup"><span data-stu-id="186d6-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="186d6-120">De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins tienen autorización para ejecutar el cmdlet **Publish-CsTopology** y el cmdlet **enable-CsTopology** .</span><span class="sxs-lookup"><span data-stu-id="186d6-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="186d6-121">Sin embargo, si los permisos de configuración no se han delegado, debe haber iniciado sesión como administrador de dominio para poder ejecutar **Publish-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="186d6-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="186d6-122">Para otorgar a RTCUniversalServerAdmins el derecho de usar el cmdlet **Publish-CsTopology** , debe ejecutar el cmdlet **Grant-CsSetupPermission** en todos los contenedores de Active Directory que contienen los equipos que ejecutan los servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="186d6-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="186d6-123">Para otorgar a RTCUniversalServerAdmins el derecho de usar el cmdlet **enable-CsTopology** , debe ejecutar el cmdlet **set-CsSetupPermission** en todos los contenedores de los servicios de dominio de Active Directory que contengan equipos con los servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="186d6-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="186d6-124">Tenga en cuenta que esto se aplica a habilitar y publicar una topología mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="186d6-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="186d6-125">Si no ha delegado permisos mediante **set-CsSetupPermission**, solo el administrador del dominio puede habilitar y publicar una topología a través de Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="186d6-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

