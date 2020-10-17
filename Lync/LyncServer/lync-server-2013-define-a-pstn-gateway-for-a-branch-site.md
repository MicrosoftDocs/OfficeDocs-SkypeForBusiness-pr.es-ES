---
title: 'Lync Server 2013: definir una puerta de enlace RTC para un sitio de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 435af3ab537097592325438707b89ce901da9bcd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516397"
---
# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="3316e-102">Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3316e-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3316e-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3316e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3316e-104">Lleve a cabo este procedimiento en el sitio central, que contiene al menos un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3316e-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3316e-105">Antes de llevar a cabo el procedimiento, se deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="3316e-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="3316e-106">El software de comunicaciones de Lync Server 2013 &nbsp; debe estar configurado en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="3316e-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="3316e-107">El servidor de mediación debe implementarse en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="3316e-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="3316e-108">Para definir una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="3316e-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="3316e-109">Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server** y **Lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="3316e-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="3316e-110">En el árbol de consola, expanda el sitio central, expanda **Sucursales**, expanda el nombre de la sucursal para la que desee definir una puerta de enlace de la red telefónica conmutada (RTC) y, a continuación, expanda **Componentes compartidos**.</span><span class="sxs-lookup"><span data-stu-id="3316e-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="3316e-111">Haga clic con el botón secundario en **Puertas de enlace RTC** y, a continuación, en **Nueva puerta de enlace RTC/IP**.</span><span class="sxs-lookup"><span data-stu-id="3316e-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="3316e-112">En el cuadro de diálogo **Definir la nueva puerta de enlace RTC/IP**, haga clic en **Dirección IP o FQDN de la puerta de enlace** y, a continuación, escriba el nombre de dominio completo (FQDN) o la dirección IP de la puerta de enlace que está implementando en la sucursal.</span><span class="sxs-lookup"><span data-stu-id="3316e-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="3316e-113">Haga clic en **Puerto de escucha de la puerta de enlace RTC/IP** y acepte los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3316e-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="3316e-114">En la lista **Protocolo de transporte SIP**, haga clic en el protocolo de transporte que usa la puerta de enlace y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3316e-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3316e-115">Por motivos de seguridad, se recomienda encarecidamente usar una puerta de enlace RTC compatible con Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="3316e-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="3316e-116">Use el cmdlet Set-<STRONG>Set-CsPstnGateway</STRONG> para modificar las propiedades de una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="3316e-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="3316e-117">Para obtener más información, vea <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">set-CsPstnGateway</A>en la ayuda del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3316e-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="3316e-118">**Siguiente paso** para la resistencia de sitios de sucursal: [configuración de usuarios para la resistencia de sitios de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="3316e-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3316e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3316e-119">See Also</span></span>


[<span data-ttu-id="3316e-120">Opciones de implementación de la puerta de enlace RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3316e-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

