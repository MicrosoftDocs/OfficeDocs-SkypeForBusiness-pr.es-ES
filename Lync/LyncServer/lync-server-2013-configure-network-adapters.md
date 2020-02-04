---
title: 'Lync Server 2013: Configurar adaptadores de red'
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
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="ae05d-102">Configurar adaptadores de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae05d-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae05d-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ae05d-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ae05d-104">Debe asignar una o más direcciones IP al adaptador de red externa y al menos una dirección IP al adaptador de red interna.</span><span class="sxs-lookup"><span data-stu-id="ae05d-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="ae05d-105">En los procedimientos siguientes, el servidor que ejecuta Forefront Threat Management Gateway (TMG) 2010 o el enrutamiento de solicitudes de aplicaciones de Internet Information Server tiene dos adaptadores de red:</span><span class="sxs-lookup"><span data-stu-id="ae05d-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="ae05d-106">Un adaptador de red público o externo, para los clientes que intentan conectarse a su sitio web (es decir, generalmente a través de Internet).</span><span class="sxs-lookup"><span data-stu-id="ae05d-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="ae05d-107">Una interfaz de red privada, o interna, para servidores internos que ejecutan Lync Server y que hospedan servicios Web.</span><span class="sxs-lookup"><span data-stu-id="ae05d-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ae05d-108">Al igual que los servidores perimetrales, la puerta de enlace predeterminada solo se establece en el adaptador de red externo.</span><span class="sxs-lookup"><span data-stu-id="ae05d-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="ae05d-109">La puerta de enlace predeterminada será la dirección IP del enrutador o del firewall de orientación externa que dirige el tráfico a Internet.</span><span class="sxs-lookup"><span data-stu-id="ae05d-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="ae05d-110">Para el tráfico que se destina del proxy inverso al adaptador de red orientado interno, debe usar rutas estáticas persistentes (como el comando Route en Windows Server) para todas las subredes que contienen servidores a los que hacen referencia las reglas de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="ae05d-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="ae05d-111">Establecer una ruta persistente no hace que el equipo se convierta en un enrutador.</span><span class="sxs-lookup"><span data-stu-id="ae05d-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="ae05d-112">Si el reenvío IP no está habilitado, el equipo solo actúa para dirigir tráfico específico destinado a otra red a la interfaz correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ae05d-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="ae05d-113">Esto se establece esencialmente en dos puertas de enlace: una como predeterminada que señala a las redes externas y otra para el tráfico destinado a la interfaz interna y a un router u otra red.</span><span class="sxs-lookup"><span data-stu-id="ae05d-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="ae05d-114">Sin embargo, es posible que no sea necesario crear rutas persistentes para todas las subredes si los enrutadores de su red están configurados para resumir las rutas.</span><span class="sxs-lookup"><span data-stu-id="ae05d-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="ae05d-115">Cree una ruta persistente a la red en la que se define el enrutador y use el router como puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ae05d-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="ae05d-116">Si no está seguro de cómo está configurada su red y necesita ayuda sobre las rutas persistentes que se deben crear, consulte a los ingenieros de red de su empresa.</span><span class="sxs-lookup"><span data-stu-id="ae05d-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="ae05d-117">El proxy inverso debe poder resolver los registros de host (A) DNS para el director interno o el servidor front-end y los FQDN del grupo de próximos saltos que se usan en las reglas de publicación Web.</span><span class="sxs-lookup"><span data-stu-id="ae05d-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="ae05d-118">Al igual que con los servidores perimetrales, por razones de seguridad, le recomendamos que no configure un proxy inverso para usar un servidor DNS ubicado en la red interna.</span><span class="sxs-lookup"><span data-stu-id="ae05d-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="ae05d-119">Esto significa que necesita servidores DNS en el perímetro o necesita entradas de archivo de hosts en el proxy inverso que resuelve cada uno de estos FQDN a la dirección IP interna de los servidores.</span><span class="sxs-lookup"><span data-stu-id="ae05d-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="ae05d-120">Para configurar las tarjetas de adaptador de red en el equipo del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ae05d-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="ae05d-121">En Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2 que se ejecuta como proxy inverso, Abra **Cambiar configuración del adaptador** haciendo clic en **Inicio**, seleccione **Panel de control**, haga clic en centro de **redes y recursos compartidos**y, a continuación, haga clic en **Cambiar configuración del adaptador**.</span><span class="sxs-lookup"><span data-stu-id="ae05d-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="ae05d-122">Haga clic con el botón secundario en la conexión de red externa que desee usar para la interfaz externa y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ae05d-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="ae05d-123">En la página de **propiedades** , haga clic en la pestaña **red** , haga clic en **Protocolo de Internet versión 4 (TCP/IPv4)** en la lista **esta conexión usa los siguientes elementos** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ae05d-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="ae05d-124">En la página **propiedades de protocolo Internet (TCP/IP)** , configure las direcciones IP según corresponda para la subred de red a la que está conectado el adaptador de red.</span><span class="sxs-lookup"><span data-stu-id="ae05d-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ae05d-125">Si el proxy inverso ya está siendo usado por otras aplicaciones que usan HTTPS/TCP/443, como, por ejemplo, para publicar Outlook Web Access, es necesario agregar otra dirección IP para que pueda publicar los servicios Web de Lync Server 2013 en HTTPS/TCP/443 sin interferir con las reglas y las escuchas de Web existentes, o bien, necesita reemplazar el certificado existente por uno que agregue los nuevos nombres de FQDN externos al nombre alternativo de asunto.</span><span class="sxs-lookup"><span data-stu-id="ae05d-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="ae05d-126">Haga clic en **Aceptar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ae05d-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="ae05d-127">En **conexiones de red**, haga clic con el botón secundario en la conexión de red interna que desea usar para la interfaz interna y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ae05d-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="ae05d-128">Repita los pasos 3 a 5 para configurar la conexión de red interna.</span><span class="sxs-lookup"><span data-stu-id="ae05d-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

