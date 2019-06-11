---
title: 'Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="2e3cc-102">Resumen DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3cc-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e3cc-103">_**Última modificación del tema:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="2e3cc-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="2e3cc-104">Los registros del sistema de nombres de dominio (DNS) que se requerirán para definir una federación con Office Communications Server o los socios de Lync Server se determinan mediante la decisión de permitir la detección automática de DNS de su dominio por parte de otros asociados de la perspectiva.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="2e3cc-105">Si publicas el \_sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="2e3cc-106">\* \<Nombre\> de dominio SIP\* SRV, cualquier otro dominio federado puede "descubrir" su Federación.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="2e3cc-107">Puede controlar qué dominios federados pueden comunicarse con usted mediante la configuración permite dominios y dominios bloqueados en el panel de control de Lync Server, o estableciendo la configuración de dominios permitidos o bloqueados mediante el shell de administración de Lync Server y el \*\* Get\*\*, **set**, **New**, **Remove-CsAllowedDomain** y **-CsBlockedDomain** cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="2e3cc-108">Para obtener más información sobre cómo configurar estas opciones de configuración y el uso de los cmdlets de PowerShell, consulte **temas relacionados** al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="2e3cc-109">La tabla de Resumen de registros DNS muestra las entradas necesarias para una federación abierta o reconocible.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="2e3cc-110">Si no desea implementar la detección de Federación, puede decidir no configurar la \_sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="2e3cc-111">Registro de *nombre\> de dominio de SIP. \<*</span><span class="sxs-lookup"><span data-stu-id="2e3cc-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2e3cc-112">Hay escenarios específicos en los que debe tener el _sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="2e3cc-113"><EM> &lt;Nombre&gt; de dominio SIP</EM> SRV, pero no desea tener una federación que se pueda descubrir.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="2e3cc-114">Una de estas instancias es donde ha implementado la movilidad para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="2e3cc-115">El centro de notificaciones de inserción de movilidad (PNCH) es un tipo especial de Federación que se usa para clientes móviles de Microsoft Lync en Apple iPhone o iPad con el cliente móvil Lync 2010 o Windows Phone usando los clientes móviles Lync 2010 Mobile o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="2e3cc-116">_Sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="2e3cc-117"><EM> &lt;Nombre&gt; de dominio SIP</EM> El registro SRV se usa en el caso de la movilidad y la notificación push.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="2e3cc-118">Para mitigar este problema y controlar su detectabilidad, desactive la opción <STRONG>Habilitar detección de dominios asociados</STRONG> para desactivar la detección.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="2e3cc-119">Para configurar el protocolo de presencia y mensajería extensible (XMPP) para su implementación, debe crear dos registros del sistema de nombres de dominio (DNS) en un servidor DNS externo que resuelva los registros para el servicio perimetral de acceso de su servidor perimetral o de grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="2e3cc-120">Al configurar el sistema de nombres de dominio (DNS) para la conectividad de mensajería instantánea pública, verá que la configuración que admite usuarios externos admite la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="2e3cc-121">Si ya ha configurado el servidor perimetral o el grupo Edge, debe tener los registros DNS necesarios para admitir la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="2e3cc-122">Resumen DNS: Federación SIP, incluida la conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="2e3cc-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e3cc-123">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="2e3cc-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2e3cc-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="2e3cc-124">FQDN</span></span></th>
<th><span data-ttu-id="2e3cc-125">Dirección IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="2e3cc-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="2e3cc-126">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="2e3cc-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e3cc-127">DNS externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="2e3cc-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-128">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2e3cc-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2e3cc-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-130">Servicio perimetral de acceso interfaz externa necesaria para la detección automática de DNS de su Federación a otros posibles socios de Federación, y se conoce como "dominios SIP permitidos" (denominada Federación mejorada en versiones anteriores). Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="2e3cc-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="2e3cc-131">Este registro SRV es necesario para la movilidad y el centro de enrutamiento de notificaciones de inserción.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="2e3cc-132">En los casos en que haya más de un dominio SIP, cree y publique un registro SRV para cada dominio que vaya a tener clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="2e3cc-133">Es posible que el servicio de notificaciones de inserción y el servicio de notificaciones push de Apple no funcionen según lo esperado si no hay un registro SRV explícito para cada dominio SIP compatible con la implementación.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="2e3cc-134">Resumen de DNS: Protocolo de presencia y mensajería extensible (XMPP)</span><span class="sxs-lookup"><span data-stu-id="2e3cc-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e3cc-135">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="2e3cc-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2e3cc-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="2e3cc-136">FQDN</span></span></th>
<th><span data-ttu-id="2e3cc-137">Dirección IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="2e3cc-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="2e3cc-138">Se asigna a/comentarios</span><span class="sxs-lookup"><span data-stu-id="2e3cc-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e3cc-139">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="2e3cc-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-140">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2e3cc-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2e3cc-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-142">Interfaz externa de proxy XMPP en el servicio perimetral de acceso o grupo perimetral. Repita el procedimiento según sea necesario para todos los dominios SIP internos con los usuarios habilitados para Lync donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio donde se encuentra el usuario o la Directiva de usuario aplicada al Usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="2e3cc-143">También se debe configurar un dominio XMPP permitido en la Directiva del socio XMPP federado.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="2e3cc-144">Vea temas en <strong>vea también</strong> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e3cc-145">DNS externo/A</span><span class="sxs-lookup"><span data-stu-id="2e3cc-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-146">xmpp.contoso.com (por ejemplo)</span><span class="sxs-lookup"><span data-stu-id="2e3cc-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-147">Dirección IP del servicio perimetral de acceso en el servidor perimetral o grupo perimetral que aloja el proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="2e3cc-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="2e3cc-148">Señala el servicio perimetral de Access o el grupo de límites que alberga el servicio de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="2e3cc-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="2e3cc-149">Normalmente, el registro SRV que cree apuntará a este registro de host (A o AAAA).</span><span class="sxs-lookup"><span data-stu-id="2e3cc-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2e3cc-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e3cc-150">See Also</span></span>


[<span data-ttu-id="2e3cc-151">Configurar la federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3cc-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="2e3cc-152">Configurar las notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3cc-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="2e3cc-153">Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3cc-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="2e3cc-154">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3cc-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="2e3cc-155">Determinar los requisitos DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3cc-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="2e3cc-156">Administrar dominios federados SIP para la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3cc-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

