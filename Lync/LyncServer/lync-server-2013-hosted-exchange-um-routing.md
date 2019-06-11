---
title: 'Lync Server 2013: Enrutamiento de mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="253db-102">Enrutamiento de mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="253db-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="253db-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="253db-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="253db-104">La aplicación de enrutamiento de mensajería unificada de Exchange se ejecuta en el servidor front-end para enrutar llamadas, ya sea a una implementación local de mensajería unificada (UM) de Microsoft Exchange Server o a un servicio de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="253db-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="253db-105">La aplicación de enrutamiento ExUM</span><span class="sxs-lookup"><span data-stu-id="253db-105">The ExUM Routing Application</span></span>

<span data-ttu-id="253db-106">La aplicación Lync Server 2013 Exchange UM Routing usa información de la configuración de la cuenta de usuario y de los parámetros de la Directiva de voz hospedada para determinar cómo enrutar las llamadas para la mensajería de voz hospedada, como se muestra en el siguiente diagrama.</span><span class="sxs-lookup"><span data-stu-id="253db-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="253db-107">**Ejemplo de implementación mixta enrutamiento de mensajería unificada de Exchange**</span><span class="sxs-lookup"><span data-stu-id="253db-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="253db-108">![Implementación de mensajería unificada de Exchange de Lync Server local] (images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Implementación de mensajería unificada de Exchange de Lync Server local")</span><span class="sxs-lookup"><span data-stu-id="253db-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="253db-109">El enrutamiento de MU de Exchange se puede configurar para que enrute las llamadas a los usuarios que están habilitados para la mensajería unificada de Exchange local para los usuarios que están habilitados para la mensajería unificada de Exchange hospedada o para una combinación de ambas.</span><span class="sxs-lookup"><span data-stu-id="253db-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="253db-110">Por ejemplo, supongamos que el buzón de la compañía y el servicio MU de Exchange están alojados en una implementación de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="253db-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="253db-111">La información de dirección del proxy de la cuenta de usuario de Roy proporciona la información que la aplicación de enrutamiento de ExUM usa para enrutar las llamadas a un servidor local de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="253db-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="253db-112">El buzón de Alice y el servicio MU de Exchange se encuentran en el centro de datos de un proveedor de servicios de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="253db-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="253db-113">El enrutamiento de las llamadas de mensajería unificada de Exchange es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="253db-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="253db-114">Los valores establecidos en el atributo msExchUCVoiceMailSettings de la cuenta de usuario de Alice indican a la aplicación de enrutamiento de ExUM que compruebe los detalles de enrutamiento en una directiva de correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="253db-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="253db-115">El valor del atributo msExchUCVoiceMailSettings puede ser establecido por el proveedor de servicios de Exchange o el administrador de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="253db-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="253db-116">En el ejemplo que se muestra en el diagrama anterior, el administrador de Lync Server 2013 estableció el valor (CsHostedVoiceMail = 1) para habilitar el correo de voz hospedado para Alice.</span><span class="sxs-lookup"><span data-stu-id="253db-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="253db-117">Para obtener más información sobre este atributo, consulte <A href="lync-server-2013-hosted-exchange-user-management.md">Administración de usuarios de Exchange hospedado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="253db-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="253db-118">La Directiva de correo de voz hospedada que se asigna a la cuenta de usuario de Alice proporciona detalles de enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="253db-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="253db-119">Destino es el proveedor de servicios de mensajería unificada de Exchange hospedado (LS. ExUm. \<hostedExchangeServer\>. com en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="253db-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="253db-120">Las organizaciones se identifican por los identificadores de inquilino, que son los FQDN de enrutamiento de los mensajes SIP para los inquilinos de Exchange Server que se encuentran en LS. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com y Corp.litwareinc.com en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="253db-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="253db-121">El FQDN de Exchange Online es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="253db-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="253db-122">Para obtener más información, consulte [directivas de correo de voz hospedado en Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="253db-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="253db-123">Si el atributo msExchUCVoiceMailSettings y la configuración de la dirección proxy de UM están presentes en una cuenta de usuario, el atributo msExchUCVoiceMailSettings tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="253db-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

