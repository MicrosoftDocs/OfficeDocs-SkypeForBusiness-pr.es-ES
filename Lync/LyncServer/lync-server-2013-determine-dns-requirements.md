---
title: 'Lync Server 2013: determinar los requisitos de DNS'
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
ms.openlocfilehash: e3f1bc8cd839b986a4830ad32f797835c56e9ebd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="f54b5-102">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f54b5-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f54b5-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f54b5-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f54b5-104">Use el diagrama de flujo siguiente para determinar los requisitos del Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="f54b5-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="f54b5-105">Cambios en las actualizaciones acumulativas de Lync Server 2013: el 2013 de febrero se indica dónde se aplican.</span><span class="sxs-lookup"><span data-stu-id="f54b5-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f54b5-106">Microsoft Lync Server 2013 admite el uso de direcciones IPv6.</span><span class="sxs-lookup"><span data-stu-id="f54b5-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="f54b5-107">Para usar direcciones IPv6, también debe proporcionar compatibilidad con DNS de IPv6 y configurar registros de host DNS AAAA (conocidos como "Quad-A").</span><span class="sxs-lookup"><span data-stu-id="f54b5-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="f54b5-108">En las implementaciones en las que se usan IPv4 e IPv6, es mejor configurar y mantener registros de host A para IPv4 y host AAAA para IPv6.</span><span class="sxs-lookup"><span data-stu-id="f54b5-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="f54b5-109">Incluso si la implementación se ha migrado por completo a IPv6, es posible que los registros de host DNS IPv4 sigan siendo necesarios cuando los usuarios externos sigan usando IPv4.</span><span class="sxs-lookup"><span data-stu-id="f54b5-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="f54b5-110">**Diagrama de flujo para determinar los requisitos de DNS**</span><span class="sxs-lookup"><span data-stu-id="f54b5-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="f54b5-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="f54b5-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f54b5-112">De forma predeterminada, el nombre de equipo de un equipo que no está unido a un dominio es un nombre de host, no un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="f54b5-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="f54b5-113">El generador de topologías usa FQDN, no nombres de host.</span><span class="sxs-lookup"><span data-stu-id="f54b5-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="f54b5-114">Así pues, debe configurar un sufijo de DNS en el nombre del equipo para poder implementarlo como servidor perimetral no incorporado a un dominio.</span><span class="sxs-lookup"><span data-stu-id="f54b5-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="f54b5-115"><STRONG>Utilice únicamente caracteres estándar </STRONG> (A–Z, a–z, 0–9 y guiones) cuando asigne los nombres de dominio completo de sus servidores Lync, servidores perimetrales y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="f54b5-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="f54b5-116">No utilice caracteres Unicode ni de subrayado.</span><span class="sxs-lookup"><span data-stu-id="f54b5-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="f54b5-117">Los DNS externos y las entidades de certificación públicas no admiten caracteres que no sean estándar en un nombre de dominio completo (es decir, cuando el FQDN se debe asignar al nombre de sujeto en el certificado).</span><span class="sxs-lookup"><span data-stu-id="f54b5-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="f54b5-118">Para obtener más información, consulte <A href="lync-server-2013-configure-dns-host-records.md">configure DNS host Records for Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="f54b5-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="f54b5-119">Cómo localizan los clientes Lync Services</span><span class="sxs-lookup"><span data-stu-id="f54b5-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="f54b5-120">Microsoft Lync 2010, Lync 2013 y Lync Mobile son similares en la forma en que el cliente encuentra y obtiene acceso a los servicios en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f54b5-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="f54b5-121">La excepción más importante es la aplicación Lync de la tienda Windows que usa un proceso de ubicación del servicio diferente.</span><span class="sxs-lookup"><span data-stu-id="f54b5-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="f54b5-122">En esta sección se detallan dos escenarios de cómo los clientes localizan los servicios, primero el método tradicional que usa una serie de registros de host y de host, segundo usando solo los registros del servicio Detección automática.</span><span class="sxs-lookup"><span data-stu-id="f54b5-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="f54b5-123">Las actualizaciones acumulativas de los clientes de escritorio cambian el proceso de ubicación de DNS de Lync Server 2010 para todos los clientes, el proceso de consulta DNS sigue hasta que se devuelve una consulta correcta o se agota la lista de posibles registros DNS, y se devuelve el error final a el cliente.</span><span class="sxs-lookup"><span data-stu-id="f54b5-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="f54b5-124">Para todos los clientes **excepto** para la aplicación Lync de la tienda Windows durante la búsqueda de DNS, los registros SRV se consultan y devuelven al cliente en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="f54b5-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="f54b5-125">lyncdiscoverinternal. \<Registro\> de dominio a (host) para el servicio de detección automática en los servicios Web internos</span><span class="sxs-lookup"><span data-stu-id="f54b5-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="f54b5-126">lyncdiscover. \<Registro\> de dominio a (host) para el servicio de detección automática en los servicios web externos</span><span class="sxs-lookup"><span data-stu-id="f54b5-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="f54b5-127">\_sipinternaltls. \_TCP. \<Registro\> de dominio SRV (localizador de servicios) para conexiones TLS internas</span><span class="sxs-lookup"><span data-stu-id="f54b5-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="f54b5-128">\_sipinternal. \_TCP. \<Registro\> de dominio SRV (localizador de servicios) para conexiones TCP internas (se realiza solo si se permite TCP)</span><span class="sxs-lookup"><span data-stu-id="f54b5-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="f54b5-129">\_SIP. \_TLS. \<Registro\> de dominio SRV (localizador de servicios) para conexiones TLS externas</span><span class="sxs-lookup"><span data-stu-id="f54b5-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="f54b5-130">sipinternal. \<Registro\> a (host) de dominio para el director o grupo de servidores front-end, que solo se pueda resolver en la red interna</span><span class="sxs-lookup"><span data-stu-id="f54b5-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="f54b5-131">SIP. \<Registro\> de dominio a (host) para el grupo de servidores front-end o el director de la red interna, o el servicio perimetral de acceso cuando el cliente es externo</span><span class="sxs-lookup"><span data-stu-id="f54b5-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="f54b5-132">sipexternal. \<Registro\> de dominio a (host) para el servicio perimetral de acceso cuando el cliente es externo</span><span class="sxs-lookup"><span data-stu-id="f54b5-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="f54b5-133">La aplicación Lync de la tienda Windows cambia el proceso por completo porque usa dos registros:</span><span class="sxs-lookup"><span data-stu-id="f54b5-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="f54b5-134">lyncdiscoverinternal. \<Registro\> de dominio a (host) para el servicio de detección automática en los servicios Web internos</span><span class="sxs-lookup"><span data-stu-id="f54b5-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="f54b5-135">lyncdiscover. \<Registro\> de dominio a (host) para el servicio de detección automática en los servicios web externos</span><span class="sxs-lookup"><span data-stu-id="f54b5-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="f54b5-136">No hay ninguna reserva para los otros tipos de registros.</span><span class="sxs-lookup"><span data-stu-id="f54b5-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="f54b5-137">La diferencia entre los métodos usados para los clientes más recientes en comparación con los clientes anteriores es que el servicio de detección automática se convierte en el método preferido para buscar todos los servicios.</span><span class="sxs-lookup"><span data-stu-id="f54b5-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="f54b5-138">Cuando una conexión se realiza correctamente, el servicio Detección automática devuelve todas las direcciones URL de servicios web para el grupo principal del usuario, incluido el servicio de movilidad (conocido como MCX por el directorio virtual creado para el servicio en IIS), las direcciones URL de Microsoft Lync Web App y Web Scheduler.</span><span class="sxs-lookup"><span data-stu-id="f54b5-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="f54b5-139">En cambio, las direcciones URL interna y externa de Mobility Service están asociadas con el FQDN externo de los servicios web.</span><span class="sxs-lookup"><span data-stu-id="f54b5-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="f54b5-140">Por lo tanto, independientemente de si un dispositivo móvil es interno o externo a la red, el dispositivo siempre se conecta al servicio de movilidad de forma externa a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f54b5-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="f54b5-141">Si se instalaron las actualizaciones acumulativas de Lync Server 2013: febrero de 2013, el servicio de detección automática también devuelve referencias a Internal/UCWA, external/UCWA y UCWA.</span><span class="sxs-lookup"><span data-stu-id="f54b5-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="f54b5-142">Estas entradas se refieren al componente web de la API web de comunicaciones unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="f54b5-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="f54b5-143">Actualmente, solo se utiliza la entrada UCWA y se proporciona una referencia a una dirección URL para el componente Web.</span><span class="sxs-lookup"><span data-stu-id="f54b5-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="f54b5-144">UCWA usa los clientes móviles de Lync 2013 en lugar del servicio de movilidad MCX que usan los clientes móviles de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="f54b5-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f54b5-145">Al crear registros SRV, es importante recordar que deben apuntar a un registro DNS A y AAAA (si se usa direccionamiento IPv6) en el mismo dominio en el que se crea el registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="f54b5-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="f54b5-146">Por ejemplo, si el registro SRV está en contoso.com, el registro a y AAAA (si está usando direccionamiento IPv6) al que apunta no puede estar en fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f54b5-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="f54b5-147">La configuración predeterminada es dirigir todo el tráfico de clientes móviles a través del sitio externo.</span><span class="sxs-lookup"><span data-stu-id="f54b5-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="f54b5-148">Puede modificar la configuración para que devuelva solo la dirección URL interna, si es más preferible para sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="f54b5-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="f54b5-149">Con esta configuración, los usuarios pueden usar aplicaciones móviles de Lync en sus dispositivos móviles solo cuando están dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="f54b5-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="f54b5-150">Para definir esta configuración, use el cmdlet <STRONG>set-CsMcxConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f54b5-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f54b5-151">Aunque las aplicaciones móviles también pueden conectarse a otros servicios de Lync Server 2013, como el servicio de libreta de direcciones, las solicitudes web internas de aplicaciones móviles van al FQDN de Web externo solo para el servicio de movilidad.</span><span class="sxs-lookup"><span data-stu-id="f54b5-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="f54b5-152">Otras solicitudes de servicios, como las solicitudes de la libreta de direcciones, no requieren esta configuración.</span><span class="sxs-lookup"><span data-stu-id="f54b5-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="f54b5-153">Los dispositivos móviles admiten la detección manual de servicios.</span><span class="sxs-lookup"><span data-stu-id="f54b5-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="f54b5-154">En este caso, cada usuario debe configurar los parámetros del dispositivo móvil con las URL internas y externas completas del servicio Detección automática, incluyendo el protocolo y la ruta de acceso, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="f54b5-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="f54b5-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.SVC/root para acceso externo</span><span class="sxs-lookup"><span data-stu-id="f54b5-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="f54b5-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.SVC/root para acceso interno</span><span class="sxs-lookup"><span data-stu-id="f54b5-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="f54b5-157">Le recomendamos que use la detección automática en lugar de la detección manual.</span><span class="sxs-lookup"><span data-stu-id="f54b5-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="f54b5-158">Sin embargo, la configuración manual puede ser útil para solucionar problemas de conectividad de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="f54b5-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="f54b5-159">Configuración de DNS de horizonte dividido con Lync Server</span><span class="sxs-lookup"><span data-stu-id="f54b5-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="f54b5-160">El DNS de cerebro dividido se conoce por una serie de nombres, por ejemplo, DNS dividido o DNS de horizonte dividido.</span><span class="sxs-lookup"><span data-stu-id="f54b5-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="f54b5-161">Simplemente, describe una configuración de DNS en la que hay dos zonas de DNS con el mismo espacio de nombres, pero solo las solicitudes de servicios de zona DNS son internas y las solicitudes de otros servicios de zona DNS son solo externas.</span><span class="sxs-lookup"><span data-stu-id="f54b5-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="f54b5-162">No obstante, muchos de los registros SRV y registros A de DNS que contiene el DNS interno no se incluirán en el DNS externo, y viceversa.</span><span class="sxs-lookup"><span data-stu-id="f54b5-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="f54b5-163">En los casos en los que el mismo registro DNS existe en el DNS interno y externo (por ejemplo, www.contoso.com), la dirección IP devuelta será distinta en función de la ubicación (interna o externa) en la que se inició la consulta.</span><span class="sxs-lookup"><span data-stu-id="f54b5-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f54b5-164">Actualmente, el DNS de cerebro dividido no es compatible para la movilidad, o más concretamente, los registros DNS LyncDiscover y LyncDiscoverInternal.</span><span class="sxs-lookup"><span data-stu-id="f54b5-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="f54b5-165">LyncDiscover debe definirse en un servidor DNS externo y LyncDiscoverInternal debe definirse en un servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="f54b5-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="f54b5-166">Para los fines de estos temas, se usará el término DNS de cerebro dividido.</span><span class="sxs-lookup"><span data-stu-id="f54b5-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="f54b5-167">Si va a configurar DNS de horizonte dividido, a continuación se incluye un resumen de los tipos de registros DNS necesarios para cada zona.</span><span class="sxs-lookup"><span data-stu-id="f54b5-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="f54b5-168">Para obtener más información, consulte [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f54b5-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="f54b5-169">**DNS interno:**</span><span class="sxs-lookup"><span data-stu-id="f54b5-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="f54b5-170">Contiene una zona DNS llamada contoso.com sobre la cual es autoritativo</span><span class="sxs-lookup"><span data-stu-id="f54b5-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="f54b5-171">La zona contoso.com interna contiene:</span><span class="sxs-lookup"><span data-stu-id="f54b5-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="f54b5-172">DNS A y AAAA (si usa direccionamiento IPv6) y registros SRV para la configuración automática de clientes de Lync Server 2013 interna (opcional)</span><span class="sxs-lookup"><span data-stu-id="f54b5-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="f54b5-173">DNS A y AAAA (si está usando direccionamiento IPv6) o registros CNAME para la detección automática de servicios Web de Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="f54b5-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="f54b5-174">Los registros de DNS A y AAAA (si está usando direccionamiento IPv6) para el nombre del grupo de servidores front-end, el nombre del grupo de directores o el director y todos los servidores internos que ejecutan Lync Server 2013 en la red corporativa</span><span class="sxs-lookup"><span data-stu-id="f54b5-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="f54b5-175">Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz interna perimetral de cada servidor perimetral de Lync Server 2013 en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="f54b5-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="f54b5-176">Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz interna de cada servidor proxy inverso en la red perimetral (opcional para la administración del proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f54b5-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="f54b5-177">Todas las interfaces perimetrales internas del servidor perimetral 2013 de Lync Server en la red perimetral usan la zona DNS interna para resolver las consultas a contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="f54b5-178">Todos los servidores que ejecutan Lync Server 2013 y los clientes que ejecutan Lync 2013 en la red corporativa señalan a los servidores DNS internos para resolver las consultas a contoso.com o el uso del archivo hosts en cada servidor perimetral y los registros de la lista A y AAAA (si está usando direccionamiento IPv6) para servidor del próximo salto, específicamente el director o VIP del Director, VIP del grupo de servidores front-end o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f54b5-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="f54b5-179">**DNS externo:**</span><span class="sxs-lookup"><span data-stu-id="f54b5-179">**External DNS:**</span></span>

  - <span data-ttu-id="f54b5-180">Contiene una zona DNS llamada contoso.com sobre la cual es autoritativo</span><span class="sxs-lookup"><span data-stu-id="f54b5-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="f54b5-181">La zona contoso.com externa contiene:</span><span class="sxs-lookup"><span data-stu-id="f54b5-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="f54b5-182">DNS A y AAAA (si está usando direccionamiento IPv6) y registros SRV para la configuración automática de clientes de Lync Server 2013 (opcional)</span><span class="sxs-lookup"><span data-stu-id="f54b5-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="f54b5-183">DNS A y AAAA (si está usando direccionamiento IPv6) o registros CNAME para la detección automática de servicios Web de Lync Server 2013 para su uso con la movilidad</span><span class="sxs-lookup"><span data-stu-id="f54b5-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="f54b5-184">DNS A y AAAA (si está usando direccionamiento IPv6) y los registros SRV para la interfaz perimetral externa de cada servidor de Lync Server 2013, servidor perimetral o dirección IP virtual (VIP) del equilibrador de carga de hardware en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="f54b5-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="f54b5-185">Registros de DNS A y AAAA (si está usando direccionamiento IPv6) para la interfaz externa del servidor de proxy inverso o VIP para un grupo de servidores de proxy inverso en la red perimetral</span><span class="sxs-lookup"><span data-stu-id="f54b5-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="f54b5-186">Configuración automática sin DNS de horizonte dividido</span><span class="sxs-lookup"><span data-stu-id="f54b5-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="f54b5-187">Mediante el uso de DNS de horizonte dividido, un usuario de Lync Server 2013 que inicie sesión internamente puede aprovechar la configuración automática si la zona DNS \_interna contiene un sipinternaltls. \_registro SRV de TCP para cada dominio SIP en uso.</span><span class="sxs-lookup"><span data-stu-id="f54b5-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="f54b5-188">Sin embargo, si no usa DNS de horizonte dividido, la configuración automática interna de clientes que ejecutan Lync no funcionará a menos que se implemente una de las soluciones descritas en más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="f54b5-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="f54b5-189">Esto se debe a que Lync Server 2013 requiere que el URI del SIP del usuario se corresponda con el dominio del grupo de servidores front-end designado para la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="f54b5-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="f54b5-190">Este es también el caso de las versiones anteriores de Communicator.</span><span class="sxs-lookup"><span data-stu-id="f54b5-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="f54b5-191">Por ejemplo, si tiene dos dominios SIP en uso, se necesitarán los registros de servicio DNS (SRV) siguientes:</span><span class="sxs-lookup"><span data-stu-id="f54b5-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="f54b5-192">Si un usuario inicia sesión como bob@contoso.com, el siguiente registro SRV funcionará para la configuración automática porque el dominio SIP del usuario (contoso.com) coincide con el dominio del grupo de servidores front-end de configuración automática):</span><span class="sxs-lookup"><span data-stu-id="f54b5-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="f54b5-193">\_sipinternaltls. \_TCP.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f54b5-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="f54b5-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="f54b5-195">Si un usuario inicia sesión como alice@fabrikam.com, el siguiente registro SRV de DNS funcionará para la configuración automática del segundo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="f54b5-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="f54b5-196">\_sipinternaltls. \_TCP.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="f54b5-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="f54b5-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="f54b5-198">Para la comparación, si un usuario inicia sesión como tim@litwareinc.com, el siguiente registro SRV de DNS no funcionará para la configuración automática, porque el dominio SIP del cliente (litwareinc.com) no coincide con el dominio en el que se encuentra el grupo de servidores (fabrikam.com):</span><span class="sxs-lookup"><span data-stu-id="f54b5-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="f54b5-199">\_sipinternaltls. \_TCP.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="f54b5-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="f54b5-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="f54b5-201">Si la configuración automática es necesaria para los clientes que ejecutan Lync, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f54b5-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="f54b5-202">**Los objetos**   de directiva de grupo usan objetos de directiva de grupo (GPO) para rellenar los valores de servidor correctos.</span><span class="sxs-lookup"><span data-stu-id="f54b5-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f54b5-203">Esta opción no habilita la configuración automática, pero automatiza el proceso de configuración manual, de modo que si se usa este enfoque, no se requerirán los registros SRV asociados con la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="f54b5-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="f54b5-204">**Zona interna coincidente**   cree una zona en el DNS interno que coincida con la zona DNS externa (por ejemplo, contoso.com) y cree registros de DNS a y AAAA (si está usando direccionamiento IPv6) correspondientes al grupo de Lync Server 2013 que se usa para la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="f54b5-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="f54b5-205">Por ejemplo, si un usuario se hospeda en pool01.contoso.net pero inicia sesión en Lync como bob@contoso.com, cree una zona de DNS interna denominada contoso.com y dentro de ella, cree un registro de DNS A y AAAA (si se usa el direccionamiento IPv6) para pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f54b5-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="f54b5-206">**Zona interna de punto de anclaje**   si va a crear una zona completa en el DNS interno no es una opción, puede crear zonas de punto de anclaje (es decir, dedicada) que correspondan a los registros SRV necesarios para la configuración automática y rellenar esas zonas con dnscmd. exe.</span><span class="sxs-lookup"><span data-stu-id="f54b5-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="f54b5-207">Dnscmd.exe es obligatorio porque la interfaz de usuario de DNS no admite la creación de zonas designadas.</span><span class="sxs-lookup"><span data-stu-id="f54b5-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="f54b5-208">Por ejemplo, si el dominio SIP es contoso.com y dispone de un grupo de servidores front-end llamado pool01 que contiene dos servidores front-end, necesitará los siguientes registros A y zonas designadas en el DNS interno:</span><span class="sxs-lookup"><span data-stu-id="f54b5-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="f54b5-209">Si su entorno contiene un segundo dominio SIP (por ejemplo, fabrikam.com), necesitará los siguientes registros A y zonas designadas en el DNS interno:</span><span class="sxs-lookup"><span data-stu-id="f54b5-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="f54b5-p121">El FQDN del grupo de servidores front-end aparece dos veces, pero con dos direcciones IP distintas. Esto se debe a que se usa el equilibrio de carga de DNS, pero si se usara el equilibrio de carga de hardware, solo habría una entrada de grupo de servidores front-end. Asimismo, los valores de FQDN del grupo de servidores front-end cambian entre el ejemplo de contoso.com y el ejemplo de fabrikam.com, pero las direcciones IP permanecen iguales. Esto se debe a que los usuarios que inician sesión desde cualquiera de los dominios SIP, usan el mismo grupo de servidores front-end para la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="f54b5-p121">The Front End pool FQDN appears twice, but with two different IP addresses. This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry. Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same. This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="f54b5-214">Para obtener más información, consulte el artículo del blog de DMTF "configuración automática de Communicator y DNS de cerebro [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707)dividido" en.</span><span class="sxs-lookup"><span data-stu-id="f54b5-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f54b5-215">El contenido de cada blog y su dirección URL están sujetos a cambio sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="f54b5-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="f54b5-216">Configuración del sistema de nombres de dominio (DNS) para la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="f54b5-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="f54b5-217">Para configurar DNS para redirigir el tráfico web de Lync Server 2013 a los sitios de recuperación ante desastres y conmutación por error, debe usar un proveedor de DNS que admita GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="f54b5-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="f54b5-218">Puede configurar los registros DNS para que admitan la recuperación ante desastres, de modo que las características que usan servicios web continúen incluso si hay un grupo de servidores front-end completo que deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="f54b5-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="f54b5-219">Esta característica de recuperación ante desastres admite las direcciones URL sencillas de detección automática (URL de Lyncdiscover), de reunirse y de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="f54b5-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="f54b5-220">Se definen y configuran registros adicionales de host DNS (A y AAAA si se usa IPv6) para la resolución interna y externa de servicios web en su proveedor de GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="f54b5-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="f54b5-221">Los siguientes detalles dan por sentado que los grupos emparejados, geográficamente dispersos y GeoDNS compatibles con el proveedor con DNS de operación por rondas, o que están configurados para usar Grupo1 como principal, y conmutan por error a grupo2 en caso de pérdida de comunicaciones o error de hardware.</span><span class="sxs-lookup"><span data-stu-id="f54b5-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f54b5-222">Registro GeoDNS (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="f54b5-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="f54b5-223">Registros de grupo (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="f54b5-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="f54b5-224">Registros CNAME (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="f54b5-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="f54b5-225">Configuración de DNS (seleccione una opción)</span><span class="sxs-lookup"><span data-stu-id="f54b5-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f54b5-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-229">Alias Meet.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-230">Alias Meet.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-231">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="f54b5-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f54b5-232">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="f54b5-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f54b5-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-236">Alias Meet.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-237">Alias Meet.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-238">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="f54b5-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f54b5-239">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="f54b5-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f54b5-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-243">Alias Dialin.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-244">Alias Dialin.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-245">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="f54b5-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f54b5-246">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="f54b5-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f54b5-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-250">Alias Dialin.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-251">Alias Dialin.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-252">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="f54b5-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f54b5-253">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="f54b5-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f54b5-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-257">Alias Lyncdiscoverinternal.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-258">Alias Lyncdiscoverinternal.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-259">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="f54b5-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f54b5-260">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="f54b5-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f54b5-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-264">Alias Lyncdiscover.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-265">Alias Lyncdiscover.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-266">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="f54b5-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f54b5-267">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="f54b5-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f54b5-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-271">Alias Scheduler.contoso.com a Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-272">Alias Scheduler.contoso.com a Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-273">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="f54b5-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f54b5-274">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="f54b5-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f54b5-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-278">Alias Scheduler.contoso.com a Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="f54b5-279">Alias Scheduler.contoso.com a Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f54b5-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f54b5-280">Round Robin entre grupos</span><span class="sxs-lookup"><span data-stu-id="f54b5-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="f54b5-281">Usar principal, conectar con secundario si se produce un error</span><span class="sxs-lookup"><span data-stu-id="f54b5-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="f54b5-282">Equilibrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="f54b5-282">DNS Load Balancing</span></span>

<span data-ttu-id="f54b5-283">El equilibrio de carga de DNS suele implementarse en el nivel de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f54b5-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="f54b5-284">La aplicación (por ejemplo, un cliente que ejecuta Lync), intenta conectarse a un servidor de un grupo de servidores conectándose a una de las direcciones IP devueltas desde las direcciones IP a y AAAA (si se usa el direccionamiento IPv6) para el nombre de dominio completo (FQDN) del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f54b5-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="f54b5-285">Por ejemplo, si hay tres servidores front-end en un grupo de servidores denominado pool01.contoso.com, pasará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f54b5-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="f54b5-286">Clientes que ejecutan el DNS de consulta de Lync para pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f54b5-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="f54b5-287">La consulta devuelve tres direcciones IP y las almacena en caché de la siguiente manera (no necesariamente en el orden indicado):</span><span class="sxs-lookup"><span data-stu-id="f54b5-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="f54b5-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="f54b5-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="f54b5-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="f54b5-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="f54b5-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="f54b5-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="f54b5-291">El cliente intenta establecer una conexión de protocolo de control de transmisión (TCP) con una de las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="f54b5-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="f54b5-292">Si no funciona, lo intentará con la siguiente dirección IP almacenada en caché.</span><span class="sxs-lookup"><span data-stu-id="f54b5-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="f54b5-293">Si la conexión TCP se realiza correctamente, el cliente negocia TLS para conectarse al registrador principal en pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f54b5-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="f54b5-294">Si el cliente prueba todas las entradas almacenadas en caché sin establecer una conexión correctamente, se notificará al usuario que no hay servidores disponibles que ejecuten Lync Server 2013 en este momento.</span><span class="sxs-lookup"><span data-stu-id="f54b5-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f54b5-295">El equilibrio de carga basado en DNS es distinto al round robin de DNS (DNS RR), que normalmente hace referencia al equilibrio de carga usando el DNS para proporcionar un orden distinto de direcciones IP correspondientes a los servidores de un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f54b5-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="f54b5-296">Por lo general, DNS RR solo habilita la distribución de carga, pero no habilita la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="f54b5-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="f54b5-297">Por ejemplo, si la conexión a la dirección IP devuelta por la consulta de DNS A y AAAA (si está usando direccionamiento IPv6) produce un error, se producirá un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="f54b5-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="f54b5-298">Por tanto, el round robin de DNS por sí solo es menos fiable que el equilibrio de carga basado en DNS.</span><span class="sxs-lookup"><span data-stu-id="f54b5-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="f54b5-299">Puede usar el round robin de DNS junto con el equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="f54b5-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="f54b5-300">El equilibrio de carga de DNS se usa para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f54b5-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="f54b5-301">Equilibrio de carga de SIP de servidor a servidor a los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="f54b5-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="f54b5-302">Equilibrar la carga de aplicaciones de servicios de aplicaciones de comunicaciones unificadas (UCAS, Unified Communications Application Services), como Operador automático de conferencia, Grupo de respuesta y Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f54b5-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="f54b5-303">Impedir el establecimiento de nuevas conexiones con aplicaciones UCAS (proceso también conocido como "purga").</span><span class="sxs-lookup"><span data-stu-id="f54b5-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="f54b5-304">Equilibrar la carga de todo el tráfico de servidor a cliente entre clientes y servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="f54b5-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="f54b5-305">El equilibrio de carga de DNS no puede usarse para:</span><span class="sxs-lookup"><span data-stu-id="f54b5-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="f54b5-306">Tráfico web de cliente a servidor a servidores de director o front-end</span><span class="sxs-lookup"><span data-stu-id="f54b5-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="f54b5-307">Equilibrio de carga de DNS y tráfico federado:</span><span class="sxs-lookup"><span data-stu-id="f54b5-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="f54b5-308">Si una consulta SRV de DNS devuelve varios registros DNS, el servicio perimetral de acceso siempre elige el registro SRV de DNS con la prioridad numérica más baja y el peso numérico más alto.</span><span class="sxs-lookup"><span data-stu-id="f54b5-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="f54b5-309">El documento del equipo de la tarea de ingeniería de Internet "un RR de DNS para especificar la ubicación de los <http://www.ietf.org/rfc/rfc2782.txt> servicios (DNS SRV)" especifica que si hay varios registros SRV de DNS definidos, se usa primero la prioridad y luego el peso.</span><span class="sxs-lookup"><span data-stu-id="f54b5-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="f54b5-310">Por ejemplo, el registro A de SRV de DNS tiene un peso de 20 y una prioridad de 40 y el registro B de SRV de DNS tiene un peso de 10 y una prioridad de 50.</span><span class="sxs-lookup"><span data-stu-id="f54b5-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="f54b5-311">Se seleccionará el registro SRV de DNS A con prioridad 40.</span><span class="sxs-lookup"><span data-stu-id="f54b5-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="f54b5-312">Las siguientes reglas se aplican a la selección de registros SRV de DNS:</span><span class="sxs-lookup"><span data-stu-id="f54b5-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="f54b5-313">La prioridad se considera en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="f54b5-313">Priority is considered first.</span></span> <span data-ttu-id="f54b5-314">Un cliente debe intentar ponerse en contacto con el host de destino definido por el registro SRV de DNS con la prioridad con el número más bajo que pueda llegar.</span><span class="sxs-lookup"><span data-stu-id="f54b5-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="f54b5-315">Los destinos con la misma prioridad deben probarse en el orden definido por el campo weight.</span><span class="sxs-lookup"><span data-stu-id="f54b5-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="f54b5-316">El campo peso especifica un peso relativo para las entradas con la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="f54b5-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="f54b5-317">A los pesos más grandes se les debe dar una probabilidad proporcionalmente mayor de ser seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f54b5-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="f54b5-318">Los administradores de DNS deben usar Weight 0 cuando no hay ninguna selección de servidor que hacer.</span><span class="sxs-lookup"><span data-stu-id="f54b5-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="f54b5-319">En presencia de registros que contienen pesos mayores que 0, los registros con peso 0 deben tener una probabilidad muy pequeña de ser seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f54b5-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="f54b5-320">Si se devuelven varios registros SRV de DNS con la misma prioridad y el mismo peso, el servicio perimetral de acceso seleccionará el registro SRV que se recibió primero del servidor DNS.</span><span class="sxs-lookup"><span data-stu-id="f54b5-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

