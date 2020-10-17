---
title: 'Lync Server 2013: directrices para la integración de la mensajería unificada local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44f032f7dd7d11d70ac912b2005f3ad9f7ddad69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536927"
---
# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="218ec-102">Directrices para la integración de la mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="218ec-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="218ec-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="218ec-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="218ec-104">A continuación, se ofrecen instrucciones y procedimientos recomendados que se deben tener en cuenta al implementar la telefonía IP empresarial:</span><span class="sxs-lookup"><span data-stu-id="218ec-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="218ec-105">La mensajería unificada (MU) de Exchange solo admite IPv6 si también usa UCMA 4.</span><span class="sxs-lookup"><span data-stu-id="218ec-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="218ec-106">Implemente un servidor Standard Edition de Lync Server 2013 o un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="218ec-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="218ec-107">Para obtener más información acerca de la instalación, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="218ec-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="218ec-108">Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.</span><span class="sxs-lookup"><span data-stu-id="218ec-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="218ec-109">Implemente los roles de servidor buzón de Exchange en cada bosque de mensajería unificada (MU) de Exchange en el que desee habilitar a los usuarios para la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="218ec-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="218ec-110">Para obtener más información acerca de la instalación de los roles de servidor de Exchange, consulte la documentación de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="218ec-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="218ec-111">Cuando se instala la mensajería unificada (UM) de Exchange, se configura para usar un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="218ec-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="218ec-112">Sin embargo, el certificado autofirmado no permite que Lync Server 2013 y la mensajería unificada de Exchange confíen entre sí, por lo que es necesario solicitar un certificado independiente a una entidad de certificación en la que confían ambos servidores.</span><span class="sxs-lookup"><span data-stu-id="218ec-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="218ec-113">Si Lync Server 2013 y mensajería unificada de Exchange están instalados en bosques distintos, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013 y en el bosque de Lync Server 2013 para confiar en cada bosque de Exchange.</span><span class="sxs-lookup"><span data-stu-id="218ec-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="218ec-114">Además, establezca la configuración de mensajería unificada de Exchange de los usuarios en los objetos de usuario del bosque de Lync Server 2013, normalmente mediante un script o una herramienta entre bosques, como Identity Lifecycle Manager (ILM).</span><span class="sxs-lookup"><span data-stu-id="218ec-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="218ec-115">Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="218ec-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="218ec-116">Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.</span><span class="sxs-lookup"><span data-stu-id="218ec-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="218ec-117">Si usa una versión de mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordine los nombres de los planes de marcado de URI de SIP de mensajería unificada de Exchange y los planes de marcado de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="218ec-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="218ec-118">Implementación de servidores redundantes de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="218ec-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="218ec-119">Le recomendamos que implemente un mínimo de dos servidores en los que se ejecutan los servicios de mensajería unificada de Exchange para cada plan de marcado URI del SIP de mensajería unificada de Exchange que configure para su organización.</span><span class="sxs-lookup"><span data-stu-id="218ec-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="218ec-120">Además de proporcionar capacidad ampliada, la implementación de servidores redundantes proporciona alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="218ec-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="218ec-121">En el caso de que se produzca un error en el servidor, Lync Server 2013 se puede configurar para que conmute por error a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="218ec-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="218ec-122">Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="218ec-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="218ec-123">**Ejemplo 1: resistencia de la mensajería unificada de Exchange**</span><span class="sxs-lookup"><span data-stu-id="218ec-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="218ec-124">![Ejemplo 1 de mensajería unificada de Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Ejemplo 1 de mensajería unificada de Exchange")</span><span class="sxs-lookup"><span data-stu-id="218ec-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="218ec-125">En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín.</span><span class="sxs-lookup"><span data-stu-id="218ec-125">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="218ec-126">En el caso de una interrupción de la mensajería unificada de Exchange en Tukwila, los registros A de sistema de nombres de dominio (DNS) para los servidores 1 y 2 deben configurarse para que apunten a los servidores 3 y 4, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="218ec-126">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="218ec-127">En el caso de una interrupción de la mensajería unificada de Exchange en Dublin, los registros A de DNS para los servidores 3 y 4 deben configurarse para que apunten a los servidores 1 y 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="218ec-127">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="218ec-128">En el Ejemplo 1, debe asignar también uno de los siguientes certificados a cada servidor de mensajería unificada de Exchange:</span><span class="sxs-lookup"><span data-stu-id="218ec-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="218ec-129">Use un certificado con un carácter comodín en el Nombre alternativo de sujeto (SAN).</span><span class="sxs-lookup"><span data-stu-id="218ec-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="218ec-130">Coloque el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores de mensajería unificada de Exchange en el SAN.</span><span class="sxs-lookup"><span data-stu-id="218ec-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="218ec-131">**Ejemplo 2: resistencia de la mensajería unificada de Exchange**</span><span class="sxs-lookup"><span data-stu-id="218ec-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="218ec-132">![Ejemplo 2 de mensajería unificada de Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Ejemplo 2 de mensajería unificada de Exchange")</span><span class="sxs-lookup"><span data-stu-id="218ec-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="218ec-p106">En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.</span><span class="sxs-lookup"><span data-stu-id="218ec-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="218ec-136">Para obtener más información acerca de cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, consulte "integrar la mensajería unificada de Exchange 2013 con Lync Server" en [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .</span><span class="sxs-lookup"><span data-stu-id="218ec-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="218ec-137">Para obtener más información acerca de cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, consulte:</span><span class="sxs-lookup"><span data-stu-id="218ec-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="218ec-138">"Habilitar mensajería unificada en Exchange 2010" en [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418) .</span><span class="sxs-lookup"><span data-stu-id="218ec-138">"Enable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="218ec-139">"Deshabilitar la mensajería unificada en Exchange 2010" en [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416) .</span><span class="sxs-lookup"><span data-stu-id="218ec-139">"Disable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="218ec-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="218ec-140">See Also</span></span>


[<span data-ttu-id="218ec-141">Proceso de implementación para la integración de la mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="218ec-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

