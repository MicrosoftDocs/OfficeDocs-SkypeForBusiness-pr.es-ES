---
title: 'Lync Server 2013: determinar los requisitos de DNS'
description: 'Lync Server 2013: determinar los requisitos de DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a4bfe682314fa4f91826f4bf85f8eac36ea91d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550916"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="5def1-103">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5def1-103">Determine DNS requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5def1-104">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5def1-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5def1-105">Use el diagrama de flujo siguiente para determinar los requisitos del Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="5def1-105">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="5def1-106">Cambios en las actualizaciones acumulativas de Lync Server 2013: el 2013 de febrero se indica dónde se aplican.</span><span class="sxs-lookup"><span data-stu-id="5def1-106">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5def1-107">Microsoft Lync Server 2013 admite el uso de direcciones IPv6.</span><span class="sxs-lookup"><span data-stu-id="5def1-107">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="5def1-108">Para usar direcciones IPv6, también debe proporcionar compatibilidad con DNS de IPv6 y configurar registros de host DNS AAAA (conocidos como "Quad-A").</span><span class="sxs-lookup"><span data-stu-id="5def1-108">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="5def1-109">En las implementaciones en las que se usan IPv4 e IPv6, es mejor configurar y mantener registros de host A para IPv4 y host AAAA para IPv6.</span><span class="sxs-lookup"><span data-stu-id="5def1-109">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="5def1-110">Incluso si la implementación se ha migrado por completo a IPv6, es posible que los registros de host DNS IPv4 sigan siendo necesarios cuando los usuarios externos sigan usando IPv4.</span><span class="sxs-lookup"><span data-stu-id="5def1-110">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="5def1-111">**Diagrama de flujo para determinar los requisitos de DNS**</span><span class="sxs-lookup"><span data-stu-id="5def1-111">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="5def1-112">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="5def1-112">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5def1-113">De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, no un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5def1-113">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="5def1-114">El generador de topologías usa FQDN, no nombres de host.</span><span class="sxs-lookup"><span data-stu-id="5def1-114">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="5def1-115">Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio.</span><span class="sxs-lookup"><span data-stu-id="5def1-115">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="5def1-116"><STRONG>Utilice únicamente caracteres estándar </STRONG> (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo de sus servidores Lync, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="5def1-116"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="5def1-117">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="5def1-117">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="5def1-118">Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (es decir, cuando el FQDN se debe asignar al nombre de sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="5def1-118">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="5def1-119">Para obtener más información, consulte <A href="lync-server-2013-configure-dns-host-records.md">configure DNS host Records for Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="5def1-119">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="5def1-120">Cómo localizan los clientes Lync Services</span><span class="sxs-lookup"><span data-stu-id="5def1-120">How Lync Clients Locate Services</span></span>

<span data-ttu-id="5def1-121">Microsoft Lync 2010, Lync 2013 y Lync Mobile son similares en la forma en que el cliente encuentra y obtiene acceso a los servicios en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5def1-121">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="5def1-122">La excepción más importante es la aplicación Lync de la tienda Windows que usa un proceso de ubicación del servicio diferente.</span><span class="sxs-lookup"><span data-stu-id="5def1-122">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="5def1-123">En esta sección se detallan dos escenarios de cómo los clientes localizan los servicios, primero el método tradicional que usa una serie de registros de host y de host, segundo usando solo los registros del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="5def1-123">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="5def1-124">Las actualizaciones acumulativas de los clientes de escritorio cambian el proceso de ubicación de DNS de Lync Server 2010 para todos los clientes, el proceso de consulta DNS sigue hasta que se devuelve una consulta correcta o se agota la lista de posibles registros DNS, y se devuelve el error final al cliente.</span><span class="sxs-lookup"><span data-stu-id="5def1-124">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="5def1-125">Para todos los clientes **excepto** para la aplicación Lync de la tienda Windows durante la búsqueda de DNS, los registros SRV se consultan y devuelven al cliente en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="5def1-125">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="5def1-126">lyncdiscoverinternal. \<domain\>     Registro a (host) para el servicio de detección automática en los servicios Web internos</span><span class="sxs-lookup"><span data-stu-id="5def1-126">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="5def1-127">lyncdiscover. \<domain\>     Registro a (host) para el servicio de detección automática en los servicios web externos</span><span class="sxs-lookup"><span data-stu-id="5def1-127">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="5def1-128">\_sipinternaltls. \_ TCP. \<domain\>     Registro SRV (localizador de servicios) para conexiones TLS internas</span><span class="sxs-lookup"><span data-stu-id="5def1-128">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="5def1-129">\_sipinternal. \_ TCP. \<domain\>     Registro SRV (localizador de servicios) para conexiones TCP internas (se realiza solo si se permite TCP)</span><span class="sxs-lookup"><span data-stu-id="5def1-129">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="5def1-130">\_SIP. \_ TLS. \<domain\>     Registro SRV (localizador de servicios) para conexiones TLS externas</span><span class="sxs-lookup"><span data-stu-id="5def1-130">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="5def1-131">sipinternal. \<domain\>     Registro a (host) para el director o el grupo de servidores front-end, que solo se pueda resolver en la red interna</span><span class="sxs-lookup"><span data-stu-id="5def1-131">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="5def1-132">SIP. \<domain\>     Registro a (host) para el grupo de servidores front-end o el director de la red interna, o el servicio perimetral de acceso cuando el cliente es externo</span><span class="sxs-lookup"><span data-stu-id="5def1-132">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="5def1-133">sipexternal. \<domain\>     Registro a (host) para el servicio perimetral de acceso cuando el cliente es externo</span><span class="sxs-lookup"><span data-stu-id="5def1-133">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="5def1-134">La aplicación Lync de la tienda Windows cambia el proceso por completo porque usa dos registros:</span><span class="sxs-lookup"><span data-stu-id="5def1-134">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="5def1-135">lyncdiscoverinternal. \<domain\>     Registro a (host) para el servicio de detección automática en los servicios Web internos</span><span class="sxs-lookup"><span data-stu-id="5def1-135">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="5def1-136">lyncdiscover. \<domain\>     Registro a (host) para el servicio de detección automática en los servicios web externos</span><span class="sxs-lookup"><span data-stu-id="5def1-136">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="5def1-137">No hay ninguna reserva para los otros tipos de registros.</span><span class="sxs-lookup"><span data-stu-id="5def1-137">There is no fallback to the other record types.</span></span>

<span data-ttu-id="5def1-138">La diferencia entre los métodos usados para los clientes más recientes en comparación con los clientes anteriores es que el servicio de detección automática se convierte en el método preferido para buscar todos los servicios.</span><span class="sxs-lookup"><span data-stu-id="5def1-138">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="5def1-139">Cuando una conexión se realiza correctamente, el servicio Detección automática devuelve todas las direcciones URL de servicios web para el grupo principal del usuario, incluido el servicio de movilidad (conocido como MCX por el directorio virtual creado para el servicio en IIS), las direcciones URL de Microsoft Lync Web App y Web Scheduler.</span><span class="sxs-lookup"><span data-stu-id="5def1-139">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="5def1-140">En cambio, las direcciones URL interna y externa de Mobility Service están asociadas con el FQDN externo de los servicios web.</span><span class="sxs-lookup"><span data-stu-id="5def1-140">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="5def1-141">Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio de movilidad de forma externa a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="5def1-141">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="5def1-142">Si se instalaron las actualizaciones acumulativas de Lync Server 2013: febrero de 2013, el servicio de detección automática también devuelve referencias a Internal/UCWA, external/UCWA y UCWA.</span><span class="sxs-lookup"><span data-stu-id="5def1-142">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="5def1-143">Estas entradas se refieren al componente web de la API web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="5def1-143">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="5def1-144">Actualmente, solo se utiliza la entrada UCWA y se proporciona una referencia a una dirección URL para el componente Web.</span><span class="sxs-lookup"><span data-stu-id="5def1-144">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="5def1-145">UCWA usa los clientes móviles de Lync 2013 en lugar del servicio de movilidad MCX que usan los clientes móviles de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="5def1-145">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5def1-146">Al crear registros SRV, es importante recordar que deben apuntar a un registro DNS A y AAAA (si se usa direccionamiento IPv6) en el mismo dominio en el que se crea el registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="5def1-146">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="5def1-147">Por ejemplo, si el registro SRV está en contoso.com, el registro a y AAAA (si está usando direccionamiento IPv6) al que apunta no puede estar en fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="5def1-147">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="5def1-148">La configuración predeterminada es dirigir todo el tráfico de clientes móviles a través del sitio externo.</span><span class="sxs-lookup"><span data-stu-id="5def1-148">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="5def1-149">Puede modificar la configuración para que devuelva solo la dirección URL interna, si es más preferible para sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="5def1-149">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="5def1-150">Con esta configuración, los usuarios pueden usar aplicaciones móviles de Lync en sus dispositivos móviles solo cuando están dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="5def1-150">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="5def1-151">Para definir esta configuración, use el cmdlet <STRONG>set-CsMcxConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5def1-151">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5def1-152">Aunque las aplicaciones móviles también pueden conectarse a otros servicios de Lync Server 2013, como el servicio de libreta de direcciones, las solicitudes web internas de aplicaciones móviles van al FQDN de Web externo solo para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="5def1-152">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="5def1-153">Otras solicitudes de servicios, como las solicitudes de la libreta de direcciones, no requieren esta configuración.</span><span class="sxs-lookup"><span data-stu-id="5def1-153">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="5def1-154">Los dispositivos móviles admiten la detección manual de servicios.</span><span class="sxs-lookup"><span data-stu-id="5def1-154">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="5def1-155">En este caso, cada usuario debe configurar los parámetros del dispositivo móvil con las URL internas y externas completas del servicio Detección automática, incluyendo el protocolo y la ruta de acceso, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="5def1-155">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="5def1-156">https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.SVC/root para acceso externo</span><span class="sxs-lookup"><span data-stu-id="5def1-156">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="5def1-157">https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.SVC/root para el acceso interno</span><span class="sxs-lookup"><span data-stu-id="5def1-157">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="5def1-158">Le recomendamos que use la detección automática en lugar de la detección manual.</span><span class="sxs-lookup"><span data-stu-id="5def1-158">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="5def1-159">Sin embargo, la configuración manual puede ser útil para solucionar problemas de conectividad de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="5def1-159">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="5def1-160">Configuración de Split-Brain DNS con Lync Server</span><span class="sxs-lookup"><span data-stu-id="5def1-160">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="5def1-161">El DNS de cerebro dividido se conoce por una serie de nombres, por ejemplo, DNS dividido o DNS de horizonte dividido.</span><span class="sxs-lookup"><span data-stu-id="5def1-161">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="5def1-162">Simplemente, describe una configuración de DNS en la que hay dos zonas de DNS con el mismo espacio de nombres, pero solo las solicitudes de servicios de zona DNS son internas y las solicitudes de otros servicios de zona DNS son solo externas.</span><span class="sxs-lookup"><span data-stu-id="5def1-162">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="5def1-163">No obstante, muchos de los registros SRV y registros A de DNS que contiene el DNS interno no se incluirán en el DNS externo, y viceversa.</span><span class="sxs-lookup"><span data-stu-id="5def1-163">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="5def1-164">En los casos en los que el mismo registro DNS existe en el DNS interno y externo (por ejemplo, www.contoso.com), la dirección IP devuelta será distinta en función de la ubicación (interna o externa) en la que se inició la consulta.</span><span class="sxs-lookup"><span data-stu-id="5def1-164">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5def1-165">Actualmente, Split-Brain DNS no es compatible para la movilidad, o más concretamente, los registros DNS LyncDiscover y LyncDiscoverInternal.</span><span class="sxs-lookup"><span data-stu-id="5def1-165">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="5def1-166">LyncDiscover debe definirse en un servidor DNS externo y LyncDiscoverInternal debe definirse en un servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="5def1-166">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="5def1-167">Para los fines de estos temas, se usará el término DNS de cerebro dividido.</span><span class="sxs-lookup"><span data-stu-id="5def1-167">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="5def1-168">Si va a configurar DNS de horizonte dividido, a continuación se incluye un resumen de los tipos de registros DNS necesarios para cada zona.</span><span class="sxs-lookup"><span data-stu-id="5def1-168">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="5def1-169">Para obtener más información, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5def1-169">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="5def1-170">**DNS interno:**</span><span class="sxs-lookup"><span data-stu-id="5def1-170">**Internal DNS:**</span></span>

  - <span data-ttu-id="5def1-171">Contiene una zona DNS llamada contoso.com sobre la cual es autoritativo</span><span class="sxs-lookup"><span data-stu-id="5def1-171">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="5def1-172">La zona contoso.com interna contiene:</span><span class="sxs-lookup"><span data-stu-id="5def1-172">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="5def1-173">DNS A y AAAA (si usa direccionamiento IPv6) y registros SRV para la configuración automática de clientes de Lync Server 2013 interna (opcional)</span><span class="sxs-lookup"><span data-stu-id="5def1-173">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="5def1-174">DNS A y AAAA (si está usando direccionamiento IPv6) o registros CNAME para la detección automática de servicios Web de Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="5def1-174">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="5def1-175">Los registros de DNS A y AAAA (si está usando direccionamiento IPv6) para el nombre del grupo de servidores front-end, el nombre del grupo de directores o el director y todos los servidores internos que ejecutan Lync Server 2013 en la red corporativa</span><span class="sxs-lookup"><span data-stu-id="5def1-175">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="5def1-176">Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz interna perimetral de cada servidor perimetral de Lync Server 2013 en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="5def1-176">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="5def1-177">Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz interna de cada servidor proxy inverso en la red perimetral (opcional para la administración del proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="5def1-177">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="5def1-178">Todas las interfaces perimetrales internas del servidor perimetral 2013 de Lync Server en la red perimetral usan la zona DNS interna para resolver las consultas a contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-178">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="5def1-179">Todos los servidores que ejecutan Lync Server 2013 y los clientes que ejecutan Lync 2013 en la red corporativa punto a los servidores DNS internos para resolver las consultas a contoso.com, o el uso del archivo hosts en cada servidor perimetral y los registros de la lista A y AAAA (si está usando direccionamiento IPv6) para el servidor del próximo salto, específicamente el director o VIP de Director, VIP del grupo o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5def1-179">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="5def1-180">**DNS externo:**</span><span class="sxs-lookup"><span data-stu-id="5def1-180">**External DNS:**</span></span>

  - <span data-ttu-id="5def1-181">Contiene una zona DNS llamada contoso.com sobre la cual es autoritativo</span><span class="sxs-lookup"><span data-stu-id="5def1-181">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="5def1-182">La zona contoso.com externa contiene:</span><span class="sxs-lookup"><span data-stu-id="5def1-182">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="5def1-183">DNS A y AAAA (si está usando direccionamiento IPv6) y registros SRV para la configuración automática de clientes de Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="5def1-183">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="5def1-184">DNS A y AAAA (si está usando direccionamiento IPv6) o registros CNAME para la detección automática de servicios Web de Lync Server 2013 para su uso con la movilidad</span><span class="sxs-lookup"><span data-stu-id="5def1-184">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="5def1-185">DNS A y AAAA (si está usando direccionamiento IPv6) y los registros SRV para la interfaz perimetral externa de cada servidor de Lync Server 2013, servidor perimetral o dirección IP virtual (VIP) del equilibrador de carga de hardware en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="5def1-185">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="5def1-186">Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz externa del servidor de proxy inverso o VIP para un grupo de servidores de proxy inverso en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="5def1-186">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="5def1-187">Configuración automática sin DNS de horizonte dividido</span><span class="sxs-lookup"><span data-stu-id="5def1-187">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="5def1-188">Mediante el uso de DNS de horizonte dividido, un usuario de Lync Server 2013 que inicie sesión internamente puede aprovechar la configuración automática si la zona DNS interna contiene un \_ sipinternaltls. \_ registro SRV de TCP para cada dominio SIP en uso.</span><span class="sxs-lookup"><span data-stu-id="5def1-188">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="5def1-189">Sin embargo, si no usa DNS de horizonte dividido, la configuración automática interna de clientes que ejecutan Lync no funcionará a menos que se implemente una de las soluciones descritas en más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="5def1-189">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="5def1-190">Esto se debe a que Lync Server 2013 requiere que el URI del SIP del usuario se corresponda con el dominio del grupo de servidores front-end designado para la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="5def1-190">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="5def1-191">Este es también el caso de las versiones anteriores de Communicator.</span><span class="sxs-lookup"><span data-stu-id="5def1-191">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="5def1-192">Por ejemplo, si tiene dos dominios SIP en uso, se necesitarán los registros de servicio DNS (SRV) siguientes:</span><span class="sxs-lookup"><span data-stu-id="5def1-192">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="5def1-193">Si un usuario inicia sesión como bob@contoso.com, el siguiente registro SRV funcionará para la configuración automática porque el dominio SIP del usuario (contoso.com) coincide con el dominio del grupo de servidores front-end de configuración automática):</span><span class="sxs-lookup"><span data-stu-id="5def1-193">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="5def1-194">\_sipinternaltls. \_ tcp.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5def1-194">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="5def1-195">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-195">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="5def1-196">Si un usuario inicia sesión como alice@fabrikam.com, el siguiente registro SRV de DNS funcionará para la configuración automática del segundo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="5def1-196">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="5def1-197">\_sipinternaltls. \_ tcp.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="5def1-197">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="5def1-198">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5def1-198">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="5def1-199">Para la comparación, si un usuario inicia sesión como tim@litwareinc.com, el siguiente registro SRV de DNS no funcionará para la configuración automática, porque el dominio SIP del cliente (litwareinc.com) no coincide con el dominio en el que se encuentra el grupo de servidores (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="5def1-199">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="5def1-200">\_sipinternaltls. \_ tcp.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5def1-200">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="5def1-201">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5def1-201">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="5def1-202">Si la configuración automática es necesaria para los clientes que ejecutan Lync, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5def1-202">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="5def1-203">Objetos de directiva de **Grupo**     Use objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.</span><span class="sxs-lookup"><span data-stu-id="5def1-203">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5def1-204">Esta opción no habilita la configuración automática, pero automatiza el proceso de configuración manual, de modo que si se usa este enfoque, no se requerirán los registros SRV asociados con la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="5def1-204">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="5def1-205">**Coincidencia de zona interna**     Cree una zona en el DNS interno que coincida con la zona DNS externa (por ejemplo, contoso.com) y cree registros de DNS A y AAAA (si está usando direccionamiento IPv6) correspondientes al grupo de Lync Server 2013 que se usa para la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="5def1-205">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="5def1-206">Por ejemplo, si un usuario se hospeda en pool01.contoso.net pero inicia sesión en Lync como bob@contoso.com, cree una zona de DNS interna denominada contoso.com y dentro de ella, cree un registro de DNS A y AAAA (si se usa el direccionamiento IPv6) para pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5def1-206">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="5def1-207">Zona interna de **punto de anclaje**     Si está creando una zona completa en el DNS interno no es una opción, puede crear zonas de punto de anclaje (es decir, dedicada) que correspondan a los registros SRV necesarios para la configuración automática y rellenar dichas zonas con dnscmd.exe.</span><span class="sxs-lookup"><span data-stu-id="5def1-207">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="5def1-208">Dnscmd.exe es obligatorio porque la interfaz de usuario de DNS no admite la creación de zonas designadas.</span><span class="sxs-lookup"><span data-stu-id="5def1-208">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="5def1-209">Por ejemplo, si el dominio SIP es contoso.com y dispone de un grupo de servidores front-end llamado pool01 que contiene dos servidores front-end, necesitará los siguientes registros A y zonas designadas en el DNS interno:</span><span class="sxs-lookup"><span data-stu-id="5def1-209">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="5def1-210">Si su entorno contiene un segundo dominio SIP (por ejemplo, fabrikam.com), necesitará los siguientes registros A y zonas designadas en el DNS interno:</span><span class="sxs-lookup"><span data-stu-id="5def1-210">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="5def1-p121">El FQDN del grupo de servidores front-end aparece dos veces, pero con dos direcciones IP distintas. Esto se debe a que se usa el equilibrio de carga de DNS, pero si se usara el equilibrio de carga de hardware, solo habría una entrada de grupo de servidores front-end. Asimismo, los valores de FQDN del grupo de servidores front-end cambian entre el ejemplo de contoso.com y el ejemplo de fabrikam.com, pero las direcciones IP permanecen iguales. Esto se debe a que los usuarios que inician sesión desde cualquiera de los dominios SIP, usan el mismo grupo de servidores front-end para la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="5def1-p121">The Front End pool FQDN appears twice, but with two different IP addresses. This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry. Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same. This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="5def1-215">Para obtener más información, consulte el artículo del blog DMTF "configuración automática de Communicator y DNS de Split-Brain" en [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) .</span><span class="sxs-lookup"><span data-stu-id="5def1-215">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5def1-216">El contenido de cada blog y su dirección URL están sujetos a cambio sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="5def1-216">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="5def1-217">Configuración del sistema de nombres de dominio (DNS) para la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="5def1-217">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="5def1-218">Para configurar DNS para redirigir el tráfico web de Lync Server 2013 a los sitios de recuperación ante desastres y conmutación por error, debe usar un proveedor de DNS que admita GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="5def1-218">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="5def1-219">Puede configurar los registros DNS para que admitan la recuperación ante desastres, de modo que las características que usan servicios web continúen incluso si hay un grupo de servidores front-end completo que deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="5def1-219">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="5def1-220">Esta característica de recuperación ante desastres admite las direcciones URL sencillas de detección automática (URL de Lyncdiscover), de reunirse y de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="5def1-220">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="5def1-221">Se definen y configuran registros adicionales de host DNS (A y AAAA si se usa IPv6) para la resolución interna y externa de servicios web en su proveedor de GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="5def1-221">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="5def1-222">Los siguientes detalles dan por sentado que los grupos emparejados, geográficamente dispersos y GeoDNS compatibles con el proveedor con DNS de operación por rondas, o que están configurados para usar Grupo1 como principal, y conmutan por error a grupo2 en caso de pérdida de comunicaciones o error de hardware.</span><span class="sxs-lookup"><span data-stu-id="5def1-222">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5def1-223">Registro GeoDNS (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="5def1-223">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="5def1-224">Registros de grupo (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="5def1-224">Pool records (example)</span></span></th>
<th><span data-ttu-id="5def1-225">Registros CNAME (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="5def1-225">CNAME records (example)</span></span></th>
<th><span data-ttu-id="5def1-226">Configuración de DNS (seleccione una opción)</span><span class="sxs-lookup"><span data-stu-id="5def1-226">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5def1-227">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-227">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-228">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-228">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-229">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-229">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-230">Alias Meet.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-230">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-231">Alias Meet.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-231">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-232">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="5def1-232">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5def1-233">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="5def1-233">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5def1-234">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-234">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-235">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-235">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-236">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-236">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-237">Alias Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-237">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-238">Alias Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-238">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-239">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="5def1-239">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5def1-240">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="5def1-240">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5def1-241">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-241">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-242">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-242">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-243">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-243">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-244">Alias Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-244">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-245">Alias Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-245">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-246">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="5def1-246">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5def1-247">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="5def1-247">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5def1-248">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-248">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-249">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-249">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-250">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-250">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-251">Alias Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-251">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-252">Alias Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-252">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-253">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="5def1-253">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5def1-254">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="5def1-254">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5def1-255">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-255">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-256">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-256">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-257">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-257">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-258">Alias Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-258">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-259">Alias Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-259">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-260">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="5def1-260">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5def1-261">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="5def1-261">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5def1-262">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-262">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-263">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-263">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-264">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-264">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-265">Alias Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-265">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-266">Alias Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-266">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-267">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="5def1-267">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5def1-268">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="5def1-268">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5def1-269">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-269">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-270">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-270">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-271">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-271">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-272">Alias Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-272">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-273">Alias Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-273">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-274">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="5def1-274">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5def1-275">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="5def1-275">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5def1-276">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-276">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-277">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-277">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-278">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-278">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-279">Alias Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-279">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5def1-280">Alias Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5def1-280">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5def1-281">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="5def1-281">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5def1-282">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="5def1-282">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="5def1-283">Equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="5def1-283">DNS Load Balancing</span></span>

<span data-ttu-id="5def1-284">El equilibrio de carga de DNS suele implementarse en el nivel de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5def1-284">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="5def1-285">La aplicación (por ejemplo, un cliente que ejecuta Lync), intenta conectarse a un servidor de un grupo de servidores conectándose a una de las direcciones IP devueltas desde las direcciones IP a y AAAA (si se usa el direccionamiento IPv6) para el nombre de dominio completo (FQDN) del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="5def1-285">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="5def1-286">Por ejemplo, si hay tres servidores front-end en un grupo de servidores denominado pool01.contoso.com, pasará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5def1-286">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="5def1-287">Clientes que ejecutan el DNS de consulta de Lync para pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5def1-287">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="5def1-288">La consulta devuelve tres direcciones IP y las almacena en caché de la siguiente manera (no necesariamente en el orden indicado):</span><span class="sxs-lookup"><span data-stu-id="5def1-288">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="5def1-289">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="5def1-289">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="5def1-290">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="5def1-290">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="5def1-291">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="5def1-291">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="5def1-292">El cliente intenta establecer una conexión de protocolo de control de transmisión (TCP) con una de las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="5def1-292">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="5def1-293">Si no funciona, lo intentará con la siguiente dirección IP almacenada en caché.</span><span class="sxs-lookup"><span data-stu-id="5def1-293">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="5def1-294">Si la conexión TCP se realiza correctamente, el cliente negocia TLS para conectarse al registrador principal en pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5def1-294">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="5def1-295">Si el cliente prueba todas las entradas almacenadas en caché sin establecer una conexión correctamente, se notificará al usuario que no hay servidores disponibles que ejecuten Lync Server 2013 en este momento.</span><span class="sxs-lookup"><span data-stu-id="5def1-295">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5def1-296">El equilibrio de carga basado en DNS es distinto al round robin de DNS (DNS RR), que normalmente hace referencia al equilibrio de carga usando el DNS para proporcionar un orden distinto de direcciones IP correspondientes a los servidores de un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="5def1-296">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="5def1-297">Por lo general, DNS RR solo habilita la distribución de carga, pero no habilita la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="5def1-297">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="5def1-298">Por ejemplo, si la conexión a la dirección IP devuelta por la consulta de DNS A y AAAA (si está usando direccionamiento IPv6) produce un error, se producirá un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="5def1-298">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="5def1-299">Por tanto, el round robin de DNS por sí solo es menos fiable que el equilibrio de carga basado en DNS.</span><span class="sxs-lookup"><span data-stu-id="5def1-299">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="5def1-300">Puede usar el round robin de DNS junto con el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="5def1-300">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="5def1-301">El equilibrio de carga de DNS se usa para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5def1-301">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="5def1-302">Equilibrio de carga de SIP de servidor a servidor a los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="5def1-302">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="5def1-303">Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS, Unified Communications Application Services), como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5def1-303">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="5def1-304">Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (proceso también conocido como "purga").</span><span class="sxs-lookup"><span data-stu-id="5def1-304">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="5def1-305">Equilibrar la carga de todo el tráfico de servidor a cliente entre clientes y servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="5def1-305">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="5def1-306">El equilibrio de carga de DNS no puede usarse para:</span><span class="sxs-lookup"><span data-stu-id="5def1-306">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="5def1-307">Tráfico web de cliente a servidor a servidores de director o front-end</span><span class="sxs-lookup"><span data-stu-id="5def1-307">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="5def1-308">Equilibrio de carga de DNS y tráfico federado:</span><span class="sxs-lookup"><span data-stu-id="5def1-308">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="5def1-309">Si una consulta SRV de DNS devuelve varios registros DNS, el servicio perimetral de acceso siempre elige el registro SRV de DNS con la prioridad numérica más baja y el peso numérico más alto.</span><span class="sxs-lookup"><span data-stu-id="5def1-309">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="5def1-310">El documento del equipo de la tarea de ingeniería de Internet "un RR de DNS para especificar la ubicación de los servicios (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> especifica que si hay varios registros SRV de DNS definidos, se usa primero la prioridad y luego el peso.</span><span class="sxs-lookup"><span data-stu-id="5def1-310">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="5def1-311">Por ejemplo, el registro A de SRV de DNS tiene un peso de 20 y una prioridad de 40 y el registro B de SRV de DNS tiene un peso de 10 y una prioridad de 50.</span><span class="sxs-lookup"><span data-stu-id="5def1-311">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="5def1-312">Se seleccionará el registro SRV de DNS A con prioridad 40.</span><span class="sxs-lookup"><span data-stu-id="5def1-312">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="5def1-313">Las siguientes reglas se aplican a la selección de registros SRV de DNS:</span><span class="sxs-lookup"><span data-stu-id="5def1-313">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="5def1-314">La prioridad se considera en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="5def1-314">Priority is considered first.</span></span> <span data-ttu-id="5def1-315">Un cliente debe intentar ponerse en contacto con el host de destino definido por el registro SRV de DNS con la prioridad con el número más bajo que pueda llegar.</span><span class="sxs-lookup"><span data-stu-id="5def1-315">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="5def1-316">Los destinos con la misma prioridad deben probarse en el orden definido por el campo weight.</span><span class="sxs-lookup"><span data-stu-id="5def1-316">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="5def1-317">El campo peso especifica un peso relativo para las entradas con la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="5def1-317">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="5def1-318">A los pesos más grandes se les debe dar una probabilidad proporcionalmente mayor de ser seleccionados.</span><span class="sxs-lookup"><span data-stu-id="5def1-318">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="5def1-319">Los administradores de DNS deben usar Weight 0 cuando no hay ninguna selección de servidor que hacer.</span><span class="sxs-lookup"><span data-stu-id="5def1-319">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="5def1-320">En presencia de registros que contienen pesos mayores que 0, los registros con peso 0 deben tener una probabilidad muy pequeña de ser seleccionados.</span><span class="sxs-lookup"><span data-stu-id="5def1-320">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="5def1-321">Si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso, el servicio perimetral de acceso seleccionará el registro SRV que se recibió primero del servidor DNS.</span><span class="sxs-lookup"><span data-stu-id="5def1-321">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

