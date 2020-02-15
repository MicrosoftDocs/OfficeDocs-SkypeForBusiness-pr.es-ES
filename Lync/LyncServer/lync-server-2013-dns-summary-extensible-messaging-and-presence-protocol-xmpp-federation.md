---
title: Resumen de DNS-Federación del protocolo extensible de mensajería y presencia (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e9aa17374de29c2b7f1f144b45322d075164ab4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="f1984-102">Resumen de DNS-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1984-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1984-103">_**Última modificación del tema:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="f1984-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="f1984-104">Para configurar el protocolo extensible de mensajería y presencia (XMPP) para la implementación, debe crear dos registros del sistema de nombres de dominio (DNS) en un servidor DNS externo que resuelva los registros en el servicio perimetral de acceso del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="f1984-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="f1984-105">Resumen DNS para el protocolo XMPP(Extensible Messaging y Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="f1984-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1984-106">Ubicación/tipo/puerto</span><span class="sxs-lookup"><span data-stu-id="f1984-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f1984-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="f1984-107">FQDN</span></span></th>
<th><span data-ttu-id="f1984-108">Dirección IP/Registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="f1984-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="f1984-109">Enruta a/Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1984-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1984-110">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="f1984-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="f1984-111">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="f1984-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f1984-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f1984-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f1984-113">Interfaz externa de proxy XMPP en el servicio perimetral de acceso o el grupo de servidores perimetrales. Repita los pasos necesarios para todos los dominios SIP internos con los usuarios habilitados para Lync donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio en la que se encuentra el usuario o la Directiva de usuario aplicada al Usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="f1984-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="f1984-114">También debe configurarse un dominio XMPP permitido en la Directiva de socios federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="f1984-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="f1984-115">Vea los temas en <strong>vea también</strong> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1984-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1984-116">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="f1984-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f1984-117">xmpp.contoso.com (por ejemplo)</span><span class="sxs-lookup"><span data-stu-id="f1984-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="f1984-118">Dirección IP del servicio perimetral de acceso en el servidor perimetral o el grupo de servidores perimetrales que hospedan el proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="f1984-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="f1984-119">Señala el servicio perimetral de acceso o el grupo de servidores perimetrales que hospeda el servicio de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="f1984-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="f1984-120">Generalmente, el registro SRV que crea llevará a este registro de host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="f1984-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1984-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1984-121">See Also</span></span>


[<span data-ttu-id="f1984-122">Configuración de la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1984-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="f1984-123">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1984-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

