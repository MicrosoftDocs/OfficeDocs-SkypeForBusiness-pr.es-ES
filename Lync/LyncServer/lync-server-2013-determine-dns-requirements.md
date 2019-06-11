---
title: 'Lync Server 2013: Determinar los requisitos DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e299f138a28ba4863250d2e0be1f31f705f4a173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="7632a-102">Determinar los requisitos DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7632a-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7632a-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7632a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7632a-104">Use el diagrama de flujo siguiente para determinar los requisitos del Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="7632a-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="7632a-105">Cambios para las actualizaciones acumulativas para Lync Server 2013:2013 de febrero se indican dónde se aplican.</span><span class="sxs-lookup"><span data-stu-id="7632a-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7632a-106">Microsoft Lync Server 2013 admite el uso de direcciones IPv6.</span><span class="sxs-lookup"><span data-stu-id="7632a-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="7632a-107">Para usar direcciones IPv6, también necesita proporcionar compatibilidad para DNS IPv6 y configurar registros AAAA de host DNS (conocidos como “cuádruple A”).</span><span class="sxs-lookup"><span data-stu-id="7632a-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="7632a-108">En implementaciones en las que se están usando IPv4 e IPv6, es mejor configurar y mantener registros A de host para IPv4 y AAAA de host para IPv6.</span><span class="sxs-lookup"><span data-stu-id="7632a-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="7632a-109">Aunque su implementación haya realizado una transición completa a IPv6, los registros de host DNS IPv4 todavía pueden ser necesarios cuando los usuarios externos estén usando todavía IPv4.</span><span class="sxs-lookup"><span data-stu-id="7632a-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="7632a-110">**Diagrama de flujo para determinar los requisitos de DNS**</span><span class="sxs-lookup"><span data-stu-id="7632a-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="7632a-111">![175782ac-363e-408A-912f-8991bf152970] (images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408A-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="7632a-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7632a-112">De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, no un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="7632a-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="7632a-113">El generador de topología usa FQDN, no nombres de host.</span><span class="sxs-lookup"><span data-stu-id="7632a-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="7632a-114">Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="7632a-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="7632a-115"><STRONG>Utilice únicamente caracteres estándar</STRONG> (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos.</span><span class="sxs-lookup"><span data-stu-id="7632a-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="7632a-116">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="7632a-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="7632a-117">Los caracteres no estándar en una dirección URL o un FQDN a menudo no son compatibles con DNS externas y CA públicas (es decir, cuando el FQDN debe asignarse al SN en el certificado).</span><span class="sxs-lookup"><span data-stu-id="7632a-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="7632a-118">Para obtener más información, vea <A href="lync-server-2013-configure-dns-host-records.md">configurar registros de host DNS para Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="7632a-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="7632a-119">Cómo los clientes de Lync encuentran los servicios</span><span class="sxs-lookup"><span data-stu-id="7632a-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="7632a-120">Microsoft Lync 2010, Lync 2013 y Lync Mobile son similares en la forma en que el cliente encuentra y obtiene acceso a los servicios en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7632a-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="7632a-121">La excepción más importante es la aplicación de la tienda Windows de Lync que usa un proceso de ubicación de servicio diferente.</span><span class="sxs-lookup"><span data-stu-id="7632a-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="7632a-122">En esta sección se describen dos escenarios en los que los clientes localizan servicios: el primero es el método tradicional que usa una serie de SRV y registros de host A y el segundo usa únicamente los registros del servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="7632a-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="7632a-123">Las actualizaciones acumulativas de los clientes de escritorio cambian el proceso de ubicación DNS de Lync Server 2010 para todos los clientes, el proceso de consulta DNS continúa hasta que se devuelve una consulta correcta, o bien se agota la lista de posibles registros DNS, y se devuelve el error final a el cliente.</span><span class="sxs-lookup"><span data-stu-id="7632a-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="7632a-124">Para todos los clientes **excepto** para la aplicación de la tienda Windows de Lync durante la búsqueda de DNS, los registros SRV se consultan y devuelven al cliente en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="7632a-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="7632a-125">lyncdiscoverinternal. \<Registro\> a (host) de dominio para el servicio de detección automática en los servicios Web internos</span><span class="sxs-lookup"><span data-stu-id="7632a-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="7632a-126">lyncdiscover. \<Registro\> a (host) de dominio para el servicio de detección automática en los servicios web externos</span><span class="sxs-lookup"><span data-stu-id="7632a-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="7632a-127">\_sipinternaltls. \_TCP. \<Registro\> SRV de dominio (Ubicador de servicio) para conexiones TLS internas</span><span class="sxs-lookup"><span data-stu-id="7632a-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="7632a-128">\_sipinternal. \_TCP. \<Registro\> SRV de dominio (Ubicador de servicio) para conexiones TCP internas (se realiza solo si se permite TCP)</span><span class="sxs-lookup"><span data-stu-id="7632a-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="7632a-129">\_SIP. \_TLS. \<Registro\> SRV de dominio (Ubicador de servicio) para conexiones TLS externas</span><span class="sxs-lookup"><span data-stu-id="7632a-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="7632a-130">sipinternal. \<Registro\> a (host) de dominio para el director o grupo de servidores front-end, que solo se pueda resolver en la red interna</span><span class="sxs-lookup"><span data-stu-id="7632a-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="7632a-131">SIP. \<Registro\> a (host) de dominio para el grupo de servidores front-end o director de la red interna, o el servicio perimetral de acceso cuando el cliente es externo</span><span class="sxs-lookup"><span data-stu-id="7632a-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="7632a-132">sipexternal. \<Registro\> a (host) de dominio para el servicio perimetral de acceso cuando el cliente es externo</span><span class="sxs-lookup"><span data-stu-id="7632a-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="7632a-133">La aplicación de la tienda Windows de Lync cambia el proceso por completo porque usa dos registros:</span><span class="sxs-lookup"><span data-stu-id="7632a-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="7632a-134">lyncdiscoverinternal. \<Registro\> a (host) de dominio para el servicio de detección automática en los servicios Web internos</span><span class="sxs-lookup"><span data-stu-id="7632a-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="7632a-135">lyncdiscover. \<Registro\> a (host) de dominio para el servicio de detección automática en los servicios web externos</span><span class="sxs-lookup"><span data-stu-id="7632a-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="7632a-136">No hay reserva para los otros tipos de registros.</span><span class="sxs-lookup"><span data-stu-id="7632a-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="7632a-137">La diferencia entre los métodos usados para los clientes más recientes en comparación con los clientes más antiguos es que el servicio de detección automática se convierte en el método preferido para localizar todos los servicios.</span><span class="sxs-lookup"><span data-stu-id="7632a-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="7632a-138">Cuando una conexión se realiza correctamente, el servicio Detección automática devuelve todas las direcciones URL de servicios web para el grupo de hogar del usuario, incluido el servicio de movilidad (conocido como MCX por el directorio virtual creado para el servicio en IIS), Microsoft Lync Web App y las direcciones URL del programador web.</span><span class="sxs-lookup"><span data-stu-id="7632a-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="7632a-139">Pero, la dirección URL interna del servicio de movilidad y la dirección URL externa del servicio de movilidad se asocian al FQDN externo de los servicios web.</span><span class="sxs-lookup"><span data-stu-id="7632a-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="7632a-140">Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio de movilidad de forma externa a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="7632a-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="7632a-141">Si se han instalado las actualizaciones acumulativas de Lync Server 2013:2013 de febrero, el servicio de detección automática también devuelve referencias a Internal/UCWA, external/UCWA y UCWA.</span><span class="sxs-lookup"><span data-stu-id="7632a-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="7632a-142">Estas entradas hacen referencia al componente web de la API web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="7632a-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="7632a-143">Actualmente solo se usa la entrada de UCWA y proporciona una referencia a una URL para el componente web.</span><span class="sxs-lookup"><span data-stu-id="7632a-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="7632a-144">UCWA lo usan los clientes móviles de Lync 2013 en lugar del servicio de movilidad MCX que usan los clientes móviles de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="7632a-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7632a-145">A la hora de crear registros SRV, es importante recordar que necesitan señalar a un registro A y AAAA (si está usando direccionamiento IPv6) de DNS del mismo dominio donde se crea el registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="7632a-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="7632a-146">Por ejemplo, si el registro SRV se encuentra en contoso.com, los registros a y AAAA (si usa IPv6 Addressing) no pueden estar en fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="7632a-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="7632a-147">La configuración predeterminada dirige todo el tráfico de clientes móviles a través del sitio externo.</span><span class="sxs-lookup"><span data-stu-id="7632a-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="7632a-148">Puede cambiar la configuración para devolver solamente la dirección URL interna, si esto se adapta más a sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="7632a-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="7632a-149">Con esta configuración, los usuarios pueden usar aplicaciones móviles de Skype Empresarial en sus dispositivos móviles solo cuando están dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="7632a-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="7632a-150">Para definir esta configuración, use el cmdlet <STRONG>Set-CsMcxConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7632a-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7632a-151">Aunque las aplicaciones móviles también pueden conectarse a otros servicios de Lync Server 2013, como el servicio de libreta de direcciones, las solicitudes web internas de la aplicación móvil van al FQDN de la web externa solo para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="7632a-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="7632a-152">Otras solicitudes de servicios, como las solicitudes de la libreta de direcciones, no requieren esta configuración.</span><span class="sxs-lookup"><span data-stu-id="7632a-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="7632a-p110">Los dispositivos móviles admiten la detección manual de servicios. En este caso, cada usuario necesita configurar los parámetros del dispositivo móvil con los URI internos y externos completos del servicio de detección automática, incluso el protocolo y la ruta de acceso, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="7632a-p110">Mobile devices support manual discovery of services. In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="7632a-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.SVC/root para acceso externo</span><span class="sxs-lookup"><span data-stu-id="7632a-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="7632a-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.SVC/root para acceso interno</span><span class="sxs-lookup"><span data-stu-id="7632a-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="7632a-157">Recomendamos que use la detección automática, en lugar de la detección manual.</span><span class="sxs-lookup"><span data-stu-id="7632a-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="7632a-158">Pero, la configuración manual puede ser útil para solucionar problemas de conectividad de los dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="7632a-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="7632a-159">Configuración de DNS de horizonte dividido con Lync Server</span><span class="sxs-lookup"><span data-stu-id="7632a-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="7632a-p112">El término DNS de horizonte dividido se conoce con varios nombres, por ejemplo, DNS dividido o DNS de partición de red. Sencillamente describe una configuración de DNS en la que existen dos zonas de DNS con el mismo espacio de nombre, pero una zona de DNS procesa solo las solicitudes internas y la otra solo las externas. Pero, muchos de los registros SRV y los registros A de DNS que contiene el DNS interno no se incluirán en el DNS externo, y viceversa. Además, en los casos en que el mismo registro de DNS existe tanto en el DNS interno como en el externo (por ejemplo, www.contoso.com), la dirección IP devuelta será distinta, en función de dónde (en el interior o en el exterior) se realice la consulta de DNS.</span><span class="sxs-lookup"><span data-stu-id="7632a-p112">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS. Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests. However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true. In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7632a-p113">Actualmente, el DNS de horizonte dividido no es compatible con la movilidad o, más concretamente, con los registros de DNS LyncDiscover y LyncDiscoverInternal. LyncDiscover tiene que definirse en un servidor DNS externo y LyncDiscoverInternal tiene que definirse en un servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="7632a-p113">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records. LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="7632a-166">Aquí se utilizará el término DNS de horizonte dividido.</span><span class="sxs-lookup"><span data-stu-id="7632a-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="7632a-167">Si va a configurar DNS de horizonte dividido, en la siguiente área interna y externa encontrará un resumen de los tipos de registros de DNS necesarios para cada zona.</span><span class="sxs-lookup"><span data-stu-id="7632a-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="7632a-168">Para obtener más información, vea [escenarios de acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7632a-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="7632a-169">**DNS interno:**</span><span class="sxs-lookup"><span data-stu-id="7632a-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="7632a-170">Contiene una zona de DNS llamada contoso.com sobre la que es autoritativo</span><span class="sxs-lookup"><span data-stu-id="7632a-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="7632a-171">La zona contoso.com interna contiene:</span><span class="sxs-lookup"><span data-stu-id="7632a-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="7632a-172">DNS A y AAAA (si está usando direccionamiento IPv6) y los registros SRV para la configuración automática del cliente de Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="7632a-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="7632a-173">DNS A y AAAA (si usa direccionamiento IPv6) o registros CNAME para el descubrimiento automático de los servicios Web de Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="7632a-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="7632a-174">DNS A y AAAA (si está usando direcciones IPv6) registros para el nombre del grupo de servidores front-end, el nombre del grupo o director y todos los servidores internos que ejecutan Lync Server 2013 en la red corporativa</span><span class="sxs-lookup"><span data-stu-id="7632a-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="7632a-175">DNS A y AAAA (si usa IPv6 Addressing) para la interfaz interna perimetral de cada servidor de Lync Server 2013, Edge en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="7632a-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="7632a-176">Registros A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz interna de cada servidor proxy inverso en la red perimetral (opcional para la administración del proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="7632a-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="7632a-177">Todas las interfaces de borde interno del servidor perimetral 2013 de Lync Server en la red perimetral usan la zona DNS interna para resolver las consultas a contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="7632a-178">Todos los servidores que ejecutan Lync Server 2013 y los clientes que ejecutan Lync 2013 en la red corporativa apuntan a los servidores DNS internos para resolver las consultas a contoso.com, o el uso del archivo hosts en cada servidor perimetral y los registros de lista a y AAAA (si usa IPv6 Addressing) para servidor del próximo salto, en concreto, el director o la dirección VIP del Director, la VIP del grupo frontal o el servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="7632a-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="7632a-179">**DNS externo:**</span><span class="sxs-lookup"><span data-stu-id="7632a-179">**External DNS:**</span></span>

  - <span data-ttu-id="7632a-180">Contiene una zona de DNS llamada contoso.com sobre la que es autoritativo</span><span class="sxs-lookup"><span data-stu-id="7632a-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="7632a-181">La zona contoso.com externa contiene:</span><span class="sxs-lookup"><span data-stu-id="7632a-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="7632a-182">DNS A y AAAA (si usa direccionamiento IPv6) y los registros SRV para la configuración automática del cliente de Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="7632a-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="7632a-183">DNS A y AAAA (si usa direccionamiento IPv6) o registros CNAME para el descubrimiento automático de los servicios Web de Lync Server 2013 para usarlos con la movilidad</span><span class="sxs-lookup"><span data-stu-id="7632a-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="7632a-184">DNS A y AAAA (si está usando direccionamiento IPv6) y los registros SRV para la interfaz externa perimetral de cada Lync Server 2013, servidor perimetral o IP virtual del equilibrador de carga de hardware (VIP) en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="7632a-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="7632a-185">Registros A y AAAA (si está usando direccionamiento IPv6) de DNS para la interfaz externa del servidor proxy inverso o VIP para un grupo de servidores proxy inversos en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="7632a-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="7632a-186">Configuración automática sin DNS de horizonte dividido</span><span class="sxs-lookup"><span data-stu-id="7632a-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="7632a-187">Con DNS de horizonte dividido, un usuario de Lync Server 2013 que inicia sesión internamente puede aprovechar la configuración automática si la zona DNS interna contiene un \_sipinternaltls. \_registro TCP SRV para cada dominio SIP en uso.</span><span class="sxs-lookup"><span data-stu-id="7632a-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="7632a-188">Sin embargo, si no usa DNS dividido-Brain, la configuración automática interna de clientes que ejecutan Lync no funcionará a menos que se implemente una de las soluciones descritas en más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="7632a-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="7632a-189">Esto se debe a que Lync Server 2013 requiere que el URI SIP del usuario coincida con el dominio del grupo de servidores front-end designado para la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="7632a-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="7632a-190">Este también es el caso de las versiones anteriores de Communicator.</span><span class="sxs-lookup"><span data-stu-id="7632a-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="7632a-191">Por ejemplo, si tiene dos dominios SIP en uso, se necesitarán los registros de servicio DNS (SRV) siguientes:</span><span class="sxs-lookup"><span data-stu-id="7632a-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="7632a-192">Si un usuario inicia sesión como bob@contoso.com, el registro SRV siguiente funcionará para la configuración automática porque el dominio SIP del usuario (contoso.com) coincide con el dominio del grupo de servidores front-end de configuración automática:</span><span class="sxs-lookup"><span data-stu-id="7632a-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="7632a-193">\_sipinternaltls. \_TCP.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7632a-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="7632a-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="7632a-195">Si un usuario inicia sesión como alice@fabrikam.com, el siguiente registro SRV de DNS funcionará para la configuración automática del segundo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="7632a-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="7632a-196">\_sipinternaltls. \_TCP.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="7632a-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="7632a-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7632a-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="7632a-198">En cambio, si un usuario inicia sesión como tim@litwareinc.com, el siguiente registro SRV de DNS no funcionará para la configuración automática, porque el dominio SIP del cliente (litwareinc.com) no coincide con el dominio donde se encuentra el grupo de servidores (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="7632a-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="7632a-199">\_sipinternaltls. \_TCP.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7632a-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="7632a-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7632a-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="7632a-201">Si la configuración automática es necesaria para los clientes que ejecutan Lync, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7632a-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="7632a-202">**Los objetos**   de directiva de grupo usan objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.</span><span class="sxs-lookup"><span data-stu-id="7632a-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7632a-203">Esta opción no habilita la configuración automática, pero automatiza el proceso de configuración manual, de modo que si se usa este enfoque, no se requerirán los registros SRV asociados con la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="7632a-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="7632a-204">**Zona interna de coincidencia**   cree una zona en el DNS interno que coincida con la zona DNS externa (por ejemplo, contoso.com) y cree registros de DNS a y AAAA (si usa direcciones IPv6) que correspondan al grupo de Lync Server 2013 usado para automático configuración.</span><span class="sxs-lookup"><span data-stu-id="7632a-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="7632a-205">Por ejemplo, si un usuario se ha alojado en pool01.contoso.net pero inicia sesión en Lync como bob@contoso.com, cree una zona de DNS interna denominada contoso.com y dentro de ella, cree un registro DNS A y AAAA (si se usa el direccionamiento IPv6) para pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7632a-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="7632a-206">**Zona interna de punto de ancla**   si está creando una zona completa en el DNS interno no es una opción, puede crear zonas de punto de ancla (es decir, dedicada) que se correspondan con los registros SRV necesarios para la configuración automática y rellenarlas zonas con dnscmd. exe.</span><span class="sxs-lookup"><span data-stu-id="7632a-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="7632a-207">Dnscmd.exe es necesario porque la interfaz de usuario de DNS no admite la creación de zonas designadas.</span><span class="sxs-lookup"><span data-stu-id="7632a-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="7632a-208">Por ejemplo, si el dominio SIP es contoso.com y dispone de un grupo de servidores front-end llamado pool01 que contiene dos servidores front-end, necesitará los siguientes registros A y las siguientes zonas designadas en el DNS interno:</span><span class="sxs-lookup"><span data-stu-id="7632a-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="7632a-209">Si su entorno contiene un segundo dominio SIP (por ejemplo, fabrikam.com), necesitará los siguientes registros A y las siguientes zonas designadas en el DNS interno:</span><span class="sxs-lookup"><span data-stu-id="7632a-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="7632a-210">El FQDN del grupo de servidores front-end aparece dos veces, pero con dos direcciones IP distintas.</span><span class="sxs-lookup"><span data-stu-id="7632a-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="7632a-211">Esto es porque que se usa el equilibrio de carga de DNS, pero si se usara el equilibrio de carga de hardware, solo habría una única entrada de grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="7632a-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="7632a-212">Asimismo, los valores de FQDN del grupo de servidores front-end cambian entre el ejemplo de contoso.com y el ejemplo de fabrikam.com, pero las direcciones IP permanecen iguales.</span><span class="sxs-lookup"><span data-stu-id="7632a-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="7632a-213">Esto se debe a que los usuarios que inician sesión desde cualquiera de los dominios SIP usan el mismo grupo de servidores front-end para la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="7632a-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="7632a-214">Para obtener más información, consulte el artículo del blog de DMTF, "Communicator Automatic Configuration and split-brain [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)DNS", en.</span><span class="sxs-lookup"><span data-stu-id="7632a-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7632a-215">El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="7632a-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="7632a-216">Configuración del sistema de nombres de dominio (DNS) para la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="7632a-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="7632a-217">Para configurar DNS de redirigir el tráfico web de Lync Server 2013 a los sitios de recuperación ante desastres y conmutación por error, debe estar usando un proveedor de DNS que admita GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="7632a-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="7632a-218">Puede configurar los registros DNS para que la web admita la recuperación ante desastres, de modo que las características que usan los servicios web continúen incluso si se interrumpe un grupo de servidores front-end completo.</span><span class="sxs-lookup"><span data-stu-id="7632a-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="7632a-219">Esta característica de recuperación ante desastres admite direcciones URL sencillas de detección automática (URL de Lyncdiscover), de reunión y de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="7632a-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="7632a-p123">Los registros de host DNS adicionales (A y AAAA si se usa IPv6) se definen y se configuran para la resolución interna y externa de servicios web en su proveedor de GeoDNS. En la información siguiente se presupone que su proveedor admite grupos emparejados, geográficamente dispersos, y GeoDNS con round robin de DNS o configurados para usar Pool1 como grupo principal y conmutar por error a Pool2 en caso de pérdida de comunicaciones o error de hardware.</span><span class="sxs-lookup"><span data-stu-id="7632a-p123">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider. The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7632a-222">Registro de GeoDNS (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="7632a-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="7632a-223">Registros del grupo (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="7632a-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="7632a-224">Registros CNAME (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="7632a-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="7632a-225">Configuración de DNS (seleccione una opción)</span><span class="sxs-lookup"><span data-stu-id="7632a-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7632a-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-229">Alias Meet.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-230">Alias Meet.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-231">Round robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="7632a-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="7632a-232">Usa el principal; se conecta al secundario en caso de error</span><span class="sxs-lookup"><span data-stu-id="7632a-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7632a-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-236">Alias Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-237">Alias Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-238">Round robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="7632a-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="7632a-239">Usa el principal; se conecta al secundario en caso de error</span><span class="sxs-lookup"><span data-stu-id="7632a-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7632a-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-243">Alias Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-244">Alias Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-245">Round robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="7632a-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="7632a-246">Usa el principal; se conecta al secundario en caso de error</span><span class="sxs-lookup"><span data-stu-id="7632a-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7632a-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-250">Alias Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-251">Alias Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-252">Round robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="7632a-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="7632a-253">Usa el principal; se conecta al secundario en caso de error</span><span class="sxs-lookup"><span data-stu-id="7632a-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7632a-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-257">Alias Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-258">Alias Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-259">Round robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="7632a-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="7632a-260">Usa el principal; se conecta al secundario en caso de error</span><span class="sxs-lookup"><span data-stu-id="7632a-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7632a-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-264">Alias Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-265">Alias Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-266">Round robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="7632a-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="7632a-267">Usa el principal; se conecta al secundario en caso de error</span><span class="sxs-lookup"><span data-stu-id="7632a-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7632a-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-271">Alias Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-272">Alias Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-273">Round robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="7632a-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="7632a-274">Usa el principal; se conecta al secundario en caso de error</span><span class="sxs-lookup"><span data-stu-id="7632a-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7632a-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-278">Alias Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="7632a-279">Alias Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7632a-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7632a-280">Round robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="7632a-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="7632a-281">Usa el principal; se conecta al secundario en caso de error</span><span class="sxs-lookup"><span data-stu-id="7632a-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="7632a-282">Equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="7632a-282">DNS Load Balancing</span></span>

<span data-ttu-id="7632a-283">El equilibrio de carga de DNS suele implementarse en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7632a-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="7632a-284">La aplicación (por ejemplo, un cliente que ejecute Lync) intenta conectarse a un servidor de un grupo conectándose a una de las direcciones IP devueltas por el DNS a y AAAA (si se usa el direccionamiento IPv6) para el nombre de dominio completo del grupo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="7632a-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="7632a-285">Por ejemplo, si hay tres servidores front-end en un grupo denominado pool01.contoso.com, pasará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7632a-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="7632a-286">Los clientes que ejecutan DNS de consulta de Lync para pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7632a-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="7632a-287">La consulta devuelve tres direcciones IP y las almacena en caché como sigue (no necesariamente en este orden):</span><span class="sxs-lookup"><span data-stu-id="7632a-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="7632a-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="7632a-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="7632a-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="7632a-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="7632a-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="7632a-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="7632a-p126">Luego, el cliente intenta establecer una conexión del Protocolo de control de transmisión (TCP) con una de las direcciones IP. Si no funciona, lo intenta con la siguiente dirección IP almacenada en caché.</span><span class="sxs-lookup"><span data-stu-id="7632a-p126">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses. If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="7632a-293">Si la conexión TCP se establece correctamente, el cliente negocia con el TLS para conectarse con el registrador principal en pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7632a-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="7632a-294">Si el cliente prueba todas las entradas almacenadas en caché sin una conexión correcta, se notificará al usuario que no hay servidores que ejecuten Lync Server 2013 en este momento.</span><span class="sxs-lookup"><span data-stu-id="7632a-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7632a-p127">El equilibrio de carga basado en DNS es distinto al round robin de DNS (RR de DNS), que normalmente hace referencia al equilibrio de carga usando el DNS para proporcionar un orden distinto de direcciones IP correspondientes a los servidores de un grupo de servidores. Por lo general, RR de DNS solo habilita la distribución de carga, pero no habilita la conmutación por error. Por ejemplo, si no se consigue establecer la conexión con una de las direcciones IP devueltas por la consulta A y AAAA (si está usando el direccionamiento IPv6) de DNS, la conexión será errónea. Por tanto, el round robin de DNS por sí solo es menos fiable que el equilibrio de carga basado en DNS. Puede usar el round robin de DNS junto con el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="7632a-p127">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool. Typically DNS RR only enables load distribution, but does not enable failover. For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails. Therefore, DNS round robin by itself is less reliable than DNS-based load balancing. You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="7632a-300">El equilibrio de carga de DNS se usa para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7632a-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="7632a-301">Equilibrar la carga SIP de servidor a servidor con los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="7632a-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="7632a-302">Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS) como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="7632a-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="7632a-303">Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (proceso también conocido como "purga").</span><span class="sxs-lookup"><span data-stu-id="7632a-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="7632a-304">Equilibrar la carga de todo el tráfico desde el servidor al cliente entre clientes y servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="7632a-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="7632a-305">El equilibrio de carga de DNS no puede usarse para:</span><span class="sxs-lookup"><span data-stu-id="7632a-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="7632a-306">Tráfico web de cliente a servidor al director o a los servidores front-end</span><span class="sxs-lookup"><span data-stu-id="7632a-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="7632a-307">Equilibrio de carga de DNS y tráfico federado:</span><span class="sxs-lookup"><span data-stu-id="7632a-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="7632a-308">Si una consulta SRV de DNS devuelve varios registros de DNS, el servicio perimetral de acceso siempre selecciona el registro SRV de DNS con la prioridad numérica más baja y con el peso numérico más alto.</span><span class="sxs-lookup"><span data-stu-id="7632a-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="7632a-309">El documento del grupo de tareas de ingeniería de Internet "un registro de registros de DNS para especificar la ubicación de <http://www.ietf.org/rfc/rfc2782.txt> los servicios (DNS SRV)" especifica que si hay varios registros SRV de DNS definidos, el primer uso de Priority y, a continuación, Weight.</span><span class="sxs-lookup"><span data-stu-id="7632a-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="7632a-310">Por ejemplo, el registro A de SRV de DNS tiene un peso de 20 y una prioridad de 40, y el registro B de SRV de DNS tiene un peso de 10 y una prioridad de 50.</span><span class="sxs-lookup"><span data-stu-id="7632a-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="7632a-311">Se seleccionará el registro A de SRV de DNS con una prioridad de 40.</span><span class="sxs-lookup"><span data-stu-id="7632a-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="7632a-312">Las siguientes reglas se aplican a la selección de registros SRV de DNS:</span><span class="sxs-lookup"><span data-stu-id="7632a-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="7632a-p129">La prioridad se considera primero. Un cliente TIENE QUE intentar contactar con el host de destino definido por el registro SRV de DNS con la menor prioridad numerada que pueda alcanzar. Los destinos con la misma prioridad NECESITAN intentarse siguiendo el orden definido por el campo de peso.</span><span class="sxs-lookup"><span data-stu-id="7632a-p129">Priority is considered first. A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach. Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="7632a-p130">El campo de peso especifica un peso relativo para las entradas que tienen la misma prioridad. Es PRECISO que a los pesos más grandes se les otorgue una probabilidad proporcionalmente mayor para ser seleccionados. Los administradores de DNS TIENEN QUE usar el peso 0 cuando no hay ninguna selección de servidor que hacer. Cuando existen registros con pesos superiores a 0, los registros con peso 0 necesitan tener una oportunidad muy pequeña de ser elegidos.</span><span class="sxs-lookup"><span data-stu-id="7632a-p130">The weight field specifies a relative weight for entries with the same priority. Larger weights SHOULD be given a proportionately higher probability of being selected. DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do. In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="7632a-320">Si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso, el servicio perimetral de acceso seleccionará el registro SRV que se haya obtenido en primer lugar del servidor DNS.</span><span class="sxs-lookup"><span data-stu-id="7632a-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

