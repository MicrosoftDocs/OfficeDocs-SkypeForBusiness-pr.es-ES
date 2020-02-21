---
title: 'Lync Server 2013: definir una aplicación o un servidor de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 329fae20f239f10583b83b64d9b78fa953f6cdc3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="a16f0-102">Definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a16f0-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a16f0-103">_**Última modificación del tema:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="a16f0-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="a16f0-104">Lleve a cabo este procedimiento en el sitio central en caso de que no haya definido la aplicación o el servidor de sucursal con funciones de supervivencia tras agregarlos a la topología.</span><span class="sxs-lookup"><span data-stu-id="a16f0-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="a16f0-105">Para definir una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="a16f0-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="a16f0-106">Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a16f0-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a16f0-107">En el árbol de la consola, expanda el sitio central, expanda **sitios de sucursal**y, a continuación, expanda el nombre del sitio de sucursal en el que va a implementar la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="a16f0-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="a16f0-108">Haga clic con el botón secundario en **aplicaciones de sucursal**con funciones de supervivencia y haga clic en **nueva aplicación de sucursal**con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="a16f0-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a16f0-109">Las <STRONG>aplicaciones de sucursal</STRONG> con funciones de supervivencia son donde define servidores de sucursal con funciones de supervivencia y aplicaciones de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="a16f0-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="a16f0-110">En el cuadro de diálogo **definir aplicación de sucursal** con funciones de supervivencia, haga clic en **FQDN**, escriba el nombre de dominio completo (FQDN) de la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia que se implementará en este sitio de sucursal y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a16f0-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a16f0-111">Si está definiendo una aplicación de sucursal con funciones de supervivencia, el nombre que escriba en el <STRONG>FQDN</STRONG> debe ser el mismo que el FQDN de aplicación de sucursal con funciones de supervivencia asignado al atributo <STRONG>ServicePrincipalName</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a16f0-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="a16f0-112">Para obtener más información, consulte <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a16f0-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="a16f0-113">Haga clic en **grupo de servidores front-end**, haga clic en el servidor front-end (grupo de servicios de usuario) en el sitio central al que se conectará esta aplicación de sucursal con funciones de supervivencia o con un servidor de sucursal con funciones de supervivencia y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a16f0-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="a16f0-114">Haga clic en **servidor perimetral**, haga clic en el grupo de servidores perimetrales al que se conectará esta aplicación de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia para proporcionar conectividad RTC a usuarios remotos del sitio de sucursal y, a continuación, haga clic en **siguiente**</span><span class="sxs-lookup"><span data-stu-id="a16f0-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="a16f0-115">Haga clic en **dirección IP o FQDN de puerta de enlace**y, a continuación, escriba el FQDN o la dirección IP de la puerta de enlace del mismo nivel a la que la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia tienen asociado el enrutamiento de llamadas RTC de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="a16f0-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a16f0-116">Si está definiendo una aplicación de sucursal con funciones de supervivencia, esta es la puerta de enlace a la que se conectará el servidor de mediación de dicha aplicación para conectividad de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="a16f0-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="a16f0-117">Haga clic en **Puerto de escucha para puerta de enlace IP/RTC** y acepte el puerto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a16f0-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="a16f0-118">En **Protocolo de transporte SIP**, haga clic en el protocolo de transporte que usará la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a16f0-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a16f0-119">Por motivos de seguridad, se recomienda encarecidamente usar Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="a16f0-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="a16f0-120">Si está definiendo una aplicación de sucursal con funciones de supervivencia, consulte la documentación del proveedor para verificar que dicha aplicación admita el protocolo de Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="a16f0-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="a16f0-121">En el árbol de la consola, haga clic con el botón secundario en la nueva aplicación o servidor de sucursal con funciones de supervivencia, haga clic en **Topología** y después haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="a16f0-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="a16f0-122">**Siguiente paso**: [implementar una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013: tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="a16f0-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

