---
title: 'Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública'
description: 'Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40013b8346cc049f844a827b21bef81a66f6950
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572766"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="778ac-103">Resumen de DNS: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ac-103">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="778ac-104">_**Última modificación del tema:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="778ac-104">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="778ac-105">Los registros del sistema de nombres de dominio (DNS) que se requerirán para definir una federación con Office Communications Server o los socios de Lync Server se determinan mediante la decisión de permitir la detección automática de DNS de su dominio por parte de otros asociados de perspectiva.</span><span class="sxs-lookup"><span data-stu-id="778ac-105">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="778ac-106">Si publica el \_ sipfederationtls. \_ TPC.</span><span class="sxs-lookup"><span data-stu-id="778ac-106">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="778ac-107">*\<SIP domain name\>* Registro SRV, cualquier otro dominio federado SIP podrá "detectar" su Federación.</span><span class="sxs-lookup"><span data-stu-id="778ac-107">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="778ac-108">Puede controlar qué dominios federados pueden comunicarse con usted mediante la configuración de dominios y dominios bloqueados en el panel de control de Lync Server o mediante la configuración de los dominios permitidos o bloqueados mediante el shell de administración de Lync Server y los cmdlets **Get**, **set**, **New**, **Remove-CsAllowedDomain** y **-CsBlockedDomain** de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="778ac-108">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="778ac-109">Para obtener información adicional acerca de cómo configurar estas opciones y el uso de los cmdlets de PowerShell, vea **temas relacionados** al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="778ac-109">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="778ac-110">La tabla de resumen de registros de DNS muestra las entradas necesarias para una federación abierta o que se pueda detectar.</span><span class="sxs-lookup"><span data-stu-id="778ac-110">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="778ac-111">Si no desea implementar la detección de Federación, puede decidir no configurar la \_ sipfederationtls. \_ TPC.</span><span class="sxs-lookup"><span data-stu-id="778ac-111">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="778ac-112">*\<SIP domain name\>* registro.</span><span class="sxs-lookup"><span data-stu-id="778ac-112">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="778ac-113">Hay escenarios específicos en los que debe tener _sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="778ac-113">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="778ac-114">Registro SRV del <EM> &lt; &gt; nombre de dominio SIP</EM> , pero no desea tener una Federación reconocible.</span><span class="sxs-lookup"><span data-stu-id="778ac-114"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="778ac-115">Una de estas instancias es donde se ha implementado la movilidad para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="778ac-115">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="778ac-116">El centro de notificaciones de inserción de movilidad (PNCH) es un tipo especial de Federación que se usa para clientes móviles de Microsoft Lync en Apple iPhone o iPad mediante el cliente móvil de Lync 2010 o Windows Phone con los clientes móviles de Lync 2010 Mobile o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="778ac-116">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="778ac-117">_Sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="778ac-117">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="778ac-118">Registro del <EM> &lt; nombre &gt; de dominio SIP</EM> se usa en el caso de la movilidad y la notificación de inserción.</span><span class="sxs-lookup"><span data-stu-id="778ac-118"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="778ac-119">Para mitigar este problema y controlar la detectabilidad, desactive la opción <STRONG>Habilitar detección de dominio de socio</STRONG> para desactivar la detección.</span><span class="sxs-lookup"><span data-stu-id="778ac-119">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="778ac-120">Para configurar el protocolo extensible de mensajería y presencia (XMPP) para la implementación, debe crear dos registros del sistema de nombres de dominio (DNS) en un servidor DNS externo que resuelva los registros en el servicio perimetral de acceso del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="778ac-120">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="778ac-121">Cuando configure el sistema de nombres de dominio (DNS) para la conectividad de mensajería instantánea pública, verá que la configuración que admite usuarios externos admitirá la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="778ac-121">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="778ac-122">Si ya ha configurado el servidor perimetral o el grupo de servidores perimetrales, debe tener los registros DNS necesarios para admitir la conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="778ac-122">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="778ac-123">Resumen de DNS-Federación SIP, incluida la conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="778ac-123">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="778ac-124">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="778ac-124">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="778ac-125">FQDN</span><span class="sxs-lookup"><span data-stu-id="778ac-125">FQDN</span></span></th>
<th><span data-ttu-id="778ac-126">Dirección IP/Registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="778ac-126">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="778ac-127">Enruta a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="778ac-127">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="778ac-128">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="778ac-128">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="778ac-129">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="778ac-129">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="778ac-130">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="778ac-130">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="778ac-131">La interfaz externa del servicio perimetral de acceso es necesaria para la detección automática de DNS de la Federación a otros posibles asociados de Federación y se conoce como "dominios SIP permitidos" (denominada Federación mejorada en versiones anteriores). Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="778ac-131">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="778ac-132">Este registro SRV es necesario para la movilidad y la notificación de inserción clearinghouse.</span><span class="sxs-lookup"><span data-stu-id="778ac-132">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="778ac-133">En los casos en que haya más de un dominio SIP, cree y publique un registro SRV para cada dominio que vaya a tener clientes móviles de Lync.</span><span class="sxs-lookup"><span data-stu-id="778ac-133">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="778ac-134">Es posible que el servicio de notificación de inserción y el servicio de notificación de inserción de Apple no funcionen según lo esperado si no hay un registro SRV explícito para cada dominio SIP que admita la implementación.</span><span class="sxs-lookup"><span data-stu-id="778ac-134">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="778ac-135">Resumen de DNS-protocolo extensible de mensajería y presencia (XMPP)</span><span class="sxs-lookup"><span data-stu-id="778ac-135">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="778ac-136">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="778ac-136">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="778ac-137">FQDN</span><span class="sxs-lookup"><span data-stu-id="778ac-137">FQDN</span></span></th>
<th><span data-ttu-id="778ac-138">Dirección IP/Registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="778ac-138">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="778ac-139">Enruta a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="778ac-139">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="778ac-140">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="778ac-140">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="778ac-141">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="778ac-141">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="778ac-142">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="778ac-142">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="778ac-143">Interfaz externa de proxy XMPP en el servicio perimetral de acceso o el grupo de servidores perimetrales. Repita los pasos necesarios para todos los dominios SIP internos con los usuarios habilitados para Lync, donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio donde se encuentra el usuario o la Directiva de usuario que se aplica al usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="778ac-143">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="778ac-144">También debe configurarse un dominio XMPP permitido en la Directiva de socios federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="778ac-144">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="778ac-145">Vea los temas en <strong>vea también</strong> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="778ac-145">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="778ac-146">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="778ac-146">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="778ac-147">xmpp.contoso.com (por ejemplo)</span><span class="sxs-lookup"><span data-stu-id="778ac-147">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="778ac-148">Dirección IP del servicio perimetral de acceso en el servidor perimetral o el grupo de servidores perimetrales que hospedan el proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="778ac-148">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="778ac-149">Señala el servicio perimetral de acceso o el grupo de servidores perimetrales que hospeda el servicio de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="778ac-149">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="778ac-150">Generalmente, el registro SRV que crea llevará a este registro de host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="778ac-150">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="778ac-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="778ac-151">See Also</span></span>


[<span data-ttu-id="778ac-152">Configuración de la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ac-152">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="778ac-153">Configuración de notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ac-153">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="778ac-154">Habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ac-154">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="778ac-155">Escenarios para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ac-155">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="778ac-156">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ac-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="778ac-157">Administrar dominios federados SIP para la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ac-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

