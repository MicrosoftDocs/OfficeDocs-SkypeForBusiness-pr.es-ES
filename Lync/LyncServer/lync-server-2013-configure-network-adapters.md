---
title: 'Lync Server 2013: configurar adaptadores de red'
description: 'Lync Server 2013: configurar adaptadores de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fa6aaa76c7815c3c14f711bf79eca82c44551ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577596"
---
# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="14859-103">Configurar adaptadores de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14859-103">Configure network adapters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14859-104">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="14859-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="14859-105">Debe asignar una o más direcciones IP al adaptador de red externo y al menos una dirección IP al adaptador de red interno.</span><span class="sxs-lookup"><span data-stu-id="14859-105">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="14859-106">En los siguientes procedimientos, el servidor que ejecuta Forefront Threat Management Gateway (TMG) 2010 o el enrutamiento de solicitudes de aplicación de Internet Information Server tiene dos adaptadores de red:</span><span class="sxs-lookup"><span data-stu-id="14859-106">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="14859-107">Un adaptador de red público o externo para los clientes que intenten conectarse a su sitio web (es decir, normalmente a través de Internet).</span><span class="sxs-lookup"><span data-stu-id="14859-107">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="14859-108">Una interfaz de red privada, o interna, para los servidores internos que ejecutan Lync Server y que hospedan servicios Web.</span><span class="sxs-lookup"><span data-stu-id="14859-108">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="14859-109">De forma similar a los servidores perimetrales, solo se establece la puerta de enlace predeterminada en el adaptador de red externo.</span><span class="sxs-lookup"><span data-stu-id="14859-109">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="14859-110">La puerta de enlace predeterminada será la dirección IP del enrutador o del firewall con conexión externa que dirige el tráfico a Internet.</span><span class="sxs-lookup"><span data-stu-id="14859-110">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="14859-111">Para el tráfico destinado desde el proxy inverso al adaptador de red orientado interno, debe usar rutas estáticas persistentes (como el comando Route en Windows Server) para todas las subredes que contienen servidores a los que hacen referencia las reglas de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="14859-111">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="14859-112">Establecer una ruta persistente no hace que el equipo se convierta en un enrutador.</span><span class="sxs-lookup"><span data-stu-id="14859-112">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="14859-113">Si el reenvío IP no está habilitado, el equipo solo actúa para dirigir tráfico específico destinado a otra red a la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="14859-113">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="14859-114">Básicamente, esto configura dos puertas de enlace: una como la predeterminada que apunta a las redes externas y otra para el tráfico destinado a la interfaz interna y a un enrutador u otra red.</span><span class="sxs-lookup"><span data-stu-id="14859-114">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="14859-115">Sin embargo, es posible que no sea necesario crear rutas persistentes para todas las subredes si los enrutadores de la red están configurados para resumir las rutas.</span><span class="sxs-lookup"><span data-stu-id="14859-115">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="14859-116">Cree una ruta persistente a la red en la que se define el enrutador y use el enrutador como puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="14859-116">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="14859-117">Si no está seguro de cómo está configurada la red y necesita instrucciones sobre las rutas persistentes que deben crearse, consulte a los ingenieros de red de la empresa.</span><span class="sxs-lookup"><span data-stu-id="14859-117">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="14859-118">El proxy inverso debe ser capaz de resolver los registros de host DNS (A) para el director interno o el servidor front-end y los FQDN de grupo de servidores de próximo salto usados en las reglas de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="14859-118">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="14859-119">Al igual que con los servidores perimetrales, por motivos de seguridad, le recomendamos que no configure un proxy inverso para que use un servidor DNS ubicado en la red interna.</span><span class="sxs-lookup"><span data-stu-id="14859-119">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="14859-120">Esto significa que necesita servidores DNS en el perímetro o que necesita entradas de archivo de hosts en el proxy inverso que resuelve cada uno de estos FQDN a la dirección IP interna de los servidores.</span><span class="sxs-lookup"><span data-stu-id="14859-120">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="14859-121">Para configurar las tarjetas adaptadoras de red en el equipo de proxy inverso</span><span class="sxs-lookup"><span data-stu-id="14859-121">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="14859-122">En el servidor Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 que se ejecuta como proxy inverso, Abra **Cambiar configuración del adaptador** haciendo clic en **Inicio**, seleccione **Panel de control**, haga clic en centro de **redes y recursos compartidos**y, a continuación, haga clic en **Cambiar configuración del adaptador**.</span><span class="sxs-lookup"><span data-stu-id="14859-122">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="14859-123">Haga clic con el botón secundario en la conexión de red externa que desee usar para la interfaz externa y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="14859-123">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="14859-124">En la página de **propiedades** , haga clic en la ficha **red** , haga clic en **Protocolo de Internet versión 4 (TCP/IPv4)** en la lista **esta conexión utiliza los siguientes elementos** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="14859-124">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="14859-125">En la página **propiedades del Protocolo de Internet (TCP/IP)** , configure las direcciones IP según corresponda para la subred de red a la que está conectado el adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="14859-125">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14859-126">Si el proxy inverso ya está siendo usado por otras aplicaciones que usan HTTPS/TCP/443, como para publicar Outlook Web Access, debe agregar otra dirección IP para que pueda publicar los servicios Web de Lync Server 2013 en HTTPS/TCP/443 sin interferir con las reglas y las escuchas de Web existentes, o bien debe reemplazar el certificado existente por uno que agregue los nuevos nombres completos externos al nombre alternativo de sujeto.</span><span class="sxs-lookup"><span data-stu-id="14859-126">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="14859-127">Haga clic en **Aceptar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="14859-127">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="14859-128">En **conexiones de red**, haga clic con el botón secundario en la conexión de red interna que desea usar para la interfaz interna y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="14859-128">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="14859-129">Repita los pasos 3 a 5 para configurar la conexión de red interna.</span><span class="sxs-lookup"><span data-stu-id="14859-129">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

