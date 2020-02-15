---
title: 'Lync Server 2013: enrutamiento de mensajería unificada de Exchange hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57efdcebe52f9b32f30c22ebcbf107d3cd9d8a7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="db092-102">Enrutamiento de mensajería unificada de Exchange hospedado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db092-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db092-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="db092-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="db092-104">La aplicación de enrutamiento de mensajería unificada de Exchange se ejecuta en el servidor front-end para enrutar las llamadas, ya sea para una implementación local de mensajería unificada de Microsoft Exchange Server (MU) o para el servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="db092-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="db092-105">La aplicación ExUM Routing</span><span class="sxs-lookup"><span data-stu-id="db092-105">The ExUM Routing Application</span></span>

<span data-ttu-id="db092-106">La aplicación Lync Server 2013 Exchange UM Routing usa información de la configuración de la cuenta de usuario y de los parámetros de la Directiva de correo de voz hospedado para determinar cómo enrutar las llamadas para la mensajería de voz hospedada, tal como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="db092-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="db092-107">**Ejemplo de implementación combinada del enrutamiento UM de Exchange**</span><span class="sxs-lookup"><span data-stu-id="db092-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="db092-108">![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")</span><span class="sxs-lookup"><span data-stu-id="db092-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="db092-109">El enrutamiento de mensajería unificada de Exchange se puede configurar para enrutar llamadas a los usuarios que están habilitados para la mensajería unificada de Exchange local, a los usuarios que están habilitados para la mensajería unificada de Exchange hospedada o a una combinación de los dos.</span><span class="sxs-lookup"><span data-stu-id="db092-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="db092-110">Por ejemplo, supongamos que el buzón de correo de la compañía y el servicio de mensajería unificada de Exchange están hospedados en una implementación local de Exchange.</span><span class="sxs-lookup"><span data-stu-id="db092-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="db092-111">La información de dirección proxy de la cuenta de usuario de Roy proporciona la información que la aplicación de enrutamiento de ExUM usa para enrutar las llamadas a un servidor de mensajería unificada de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="db092-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="db092-112">El buzón de Alice y el servicio de mensajería unificada de Exchange se encuentran en el centro de datos de un proveedor de servicios de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="db092-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="db092-113">El enrutamiento de sus llamadas de mensajería unificada de Exchange se configura de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="db092-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="db092-114">Los valores establecidos en el atributo msExchUCVoiceMailSettings de la cuenta de usuario de Alicia le dice a la aplicación ExUM Routing que compruebe los detalles de enrutamiento en una directiva de correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="db092-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db092-115">El valor del atributo msExchUCVoiceMailSettings puede establecerse por el proveedor de servicios de Exchange o el administrador de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db092-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="db092-116">En el ejemplo que se muestra en el diagrama anterior, el administrador de Lync Server 2013 estableció el valor (CsHostedVoiceMail = 1) para habilitar el correo de voz hospedado en Alicia.</span><span class="sxs-lookup"><span data-stu-id="db092-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="db092-117">Para obtener más información sobre este atributo, consulte <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange User Management in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="db092-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="db092-118">La directiva de correo de voz hospedado que se ha asignado a la cuenta de usuario de Alicia proporciona la siguiente información de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="db092-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="db092-119">Destination es el proveedor de servicios de mensajería unificada de Exchange hospedado (LS. ExUm. \<hostedExchangeServer\>. com en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="db092-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="db092-120">Las organizaciones se identifican por los identificadores de inquilino, que son los FQDN de enrutamiento de los mensajes SIP para los inquilinos de Exchange Server que se encuentran en LS. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com y Corp.litwareinc.com en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="db092-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="db092-121">El FQDN para Exchange Online es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="db092-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="db092-122">Para obtener más información, consulte [directivas de correo de voz hospedado en Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="db092-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db092-123">Si tanto el atributo msExchUCVoiceMailSettings como la configuración de la dirección proxy de mensajería unificada están presentes en una cuenta de usuario, el atributo msExchUCVoiceMailSettings tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="db092-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

