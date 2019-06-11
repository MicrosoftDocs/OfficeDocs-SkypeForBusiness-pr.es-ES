---
title: 'Lync Server 2013: Definir un servidor o aplicación de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dadaa26f6a951995906ed29ffd0615da16066928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="41729-102">Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41729-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41729-103">_**Última modificación del tema:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="41729-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="41729-104">Lleve a cabo este procedimiento en el sitio central si no definió el equipo o servidor de rama que funciona bien cuando lo agregó a su topología.</span><span class="sxs-lookup"><span data-stu-id="41729-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="41729-105">Para definir un equipo de sucursal o un servidor de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="41729-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="41729-106">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="41729-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="41729-107">En el árbol de consola, expanda el sitio central, expanda **sitios de sucursal**y, a continuación, expanda el nombre del sitio de la sucursal donde planea implementar el equipo con la sucursal o el servidor de sucursal que pueda superviviente.</span><span class="sxs-lookup"><span data-stu-id="41729-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="41729-108">Haga clic con el botón derecho en **dispositivos de sucursales**supervivientes y, a continuación, haga clic en **nuevo dispositivo de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="41729-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41729-109">Los equipos de las <STRONG>sucursales</STRONG> con las que son supervivientes son los que definen servidores de sucursal y las aplicaciones de la que son supervivientes.</span><span class="sxs-lookup"><span data-stu-id="41729-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="41729-110">En el cuadro de diálogo **definir aplicación de aplicación** reinstalable, haga clic en **FQDN**, escriba el nombre de dominio completo (FQDN) de la aplicación de la rama que funcionará con la supervivencia o el servidor de sucursal con la supervivencia que va a implementar en este sitio de la sucursal y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="41729-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41729-111">Si está definiendo una aplicación de un equipo que pueda ser superviviente, el nombre que escriba en <STRONG>FQDN</STRONG> debe ser el mismo que el FQDN de la aplicación de rama superviviente que asignó al atributo <STRONG>ServicePrincipalName</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="41729-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="41729-112">Para obtener más información, vea <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Agregar una aplicación de rama que se puede hacer a Active Directory en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="41729-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="41729-113">Haga clic en **grupo de servidores front-end**, haga clic en el servidor front-end (grupo de servicios de usuario) en el sitio central al que se conectará este equipo con la sucursal o el servidor de sucursal supervivientes y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="41729-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="41729-114">Haga clic en **servidor perimetral**, haga clic en el grupo perimetral al que se conectará esta aplicación de sucursal o servidor de sucursal supervivientes para proporcionar conectividad RTC a los usuarios remotos del sitio de la sucursal y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="41729-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="41729-115">Haga clic en **FQDN de la puerta de enlace o dirección IP**y, a continuación, escriba el FQDN o la dirección IP de la puerta de enlace del mismo nivel a la que la sucursal o el servidor de sucursal superviviente está asociado para enrutar llamadas RTC entrantes o salientes.</span><span class="sxs-lookup"><span data-stu-id="41729-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41729-116">Si está definiendo un dispositivo de sucursal que funciona bien, esta es la puerta de enlace a la que se conectará el servidor de mediación de la aplicación de la sucursal con la que se puede obtener conectividad RTC.</span><span class="sxs-lookup"><span data-stu-id="41729-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="41729-117">Haga clic en **Puerto de escucha para la puerta de enlace IP/RTC**y, a continuación, acepte el puerto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="41729-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="41729-118">En **Protocolo de transporte SIP**, haga clic en el protocolo de transporte que usará el equipo de la sucursal o el servidor de sucursal supervivientes y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="41729-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41729-119">Por razones de seguridad, le recomendamos encarecidamente que use la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="41729-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="41729-120">Si está definiendo un dispositivo de sucursal que es reviviente, consulte la documentación del proveedor de su equipo de sucursales que sea superviviente para verificar que su equipo de sucursales con la supervivencia es compatible con el protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="41729-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="41729-121">En el árbol de consola, haga clic con el botón derecho en el nuevo dispositivo de sucursal o servidor que sea reviviente, haga clic en **topología**y luego en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="41729-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="41729-122">**Siguiente paso**: [implementar un equipo o servidor de rama con la supervivencia con Lync Server 2013: tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="41729-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

