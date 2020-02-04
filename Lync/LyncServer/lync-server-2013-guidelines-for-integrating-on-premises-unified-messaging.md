---
title: 'Lync Server 2013: Instrucciones para integrar mensajería unificada local y Lync Server'
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
ms.openlocfilehash: 3f3e57245f0a8edf5b545f9a67547e6be6f63399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="86635-102">Instrucciones para integrar mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86635-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86635-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="86635-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="86635-104">Los siguientes procedimientos recomendados e instrucciones debe tenerse en cuenta cuando implemente Telefonía IP empresarial:</span><span class="sxs-lookup"><span data-stu-id="86635-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86635-105">La mensajería unificada de Exchange (UM) solo admite IPv6 si también usa UCMA 4.</span><span class="sxs-lookup"><span data-stu-id="86635-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="86635-106">Implementar un servidor de Lync Server 2013 Standard Edition o un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="86635-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="86635-107">Para obtener más información acerca de la instalación, consulte [implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="86635-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="86635-108">Colabore con los administradores de Exchange para confirmar las tareas que realizará cada uno y así garantizar una integración correcta y homogénea.</span><span class="sxs-lookup"><span data-stu-id="86635-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="86635-109">Implemente los roles de servidor de buzón de Exchange en cada bosque de mensajería unificada (UM) de Exchange donde desee habilitar usuarios para la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="86635-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="86635-110">Para obtener más información sobre la instalación de los roles de servidor de Exchange, consulte la documentación de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86635-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="86635-111">Cuando se instala mensajería unificada de Exchange (UM), se configura para usar un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="86635-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="86635-112">El certificado autofirmado, sin embargo, no permite que Lync Server 2013 y la mensajería unificada de Exchange confíen entre sí, razón por la cual es necesario solicitar un certificado independiente de una entidad emisora de certificados en la que confíen ambos servidores.</span><span class="sxs-lookup"><span data-stu-id="86635-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="86635-113">Si Lync Server 2013 y mensajería unificada de Exchange se instalan en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013 y en el bosque de Lync Server 2013 para confiar en cada uno de los bosques de Exchange.</span><span class="sxs-lookup"><span data-stu-id="86635-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="86635-114">Además, establezca la configuración de mensajería unificada de los usuarios en los objetos de usuario del bosque de Lync Server 2013, generalmente usando una secuencia de comandos o una herramienta entre bosques, como Identity Lifecycle Manager (ILM).</span><span class="sxs-lookup"><span data-stu-id="86635-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="86635-115">Si es necesario, instale la Consola de administración de Exchange de modo que administre los servidores de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="86635-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="86635-116">Obtenga números de teléfono válidos para Outlook Voice Access y el operador automático.</span><span class="sxs-lookup"><span data-stu-id="86635-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="86635-117">Si usa una versión de mensajería unificada de Exchange anterior a Microsoft Exchange Server 2010 Service Pack 1 (SP1), los nombres de coordenadas de los planes de marcado de URI del SIP de mensajería unificada de Exchange y los planes de marcado de voz de empresa.</span><span class="sxs-lookup"><span data-stu-id="86635-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="86635-118">Implementación de servidores redundantes de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="86635-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86635-119">Se recomienda implementar un mínimo de dos servidores en los que se ejecuten los servicios de mensajería unificada de Exchange para cada plan de marcado de URI del SIP de Exchange que configure para su organización.</span><span class="sxs-lookup"><span data-stu-id="86635-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="86635-120">Además de ofrecer más capacidad, implementar servidores redundantes también proporciona una alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="86635-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="86635-121">En el caso de que se produzca un error de servidor, Lync Server 2013 se puede configurar para que realice la conmutación por error a otro servidor.</span><span class="sxs-lookup"><span data-stu-id="86635-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="86635-122">Los siguientes ejemplos de configuraciones ofrecen resistencia a la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="86635-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="86635-123">**Ejemplo 1: Resistencia de la mensajería unificada de Exchange**</span><span class="sxs-lookup"><span data-stu-id="86635-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="86635-124">![Ejemplo 1 de Mensajería unificada de Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Ejemplo 1 de Mensajería unificada de Exchange")</span><span class="sxs-lookup"><span data-stu-id="86635-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="86635-p105">En el Ejemplo 1, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, los registros de sistemas de nombre de dominio (DNS) A de los servidores 1 y 2 deben estar configurados para apuntar, respectivamente, a los servidores 3 y 4. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Dublín, los registros DNS A de los servidores 3 y 4 deben estar configurados para apuntar, respectivamente, a los servidores 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="86635-p105">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86635-128">En el Ejemplo 1, debe asignar también uno de los siguientes certificados a cada servidor de mensajería unificada de Exchange:</span><span class="sxs-lookup"><span data-stu-id="86635-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="86635-129">Use un certificado con un carácter comodín en el Nombre alternativo de sujeto (SAN).</span><span class="sxs-lookup"><span data-stu-id="86635-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="86635-130">Ponga el nombre de dominio completo (FQDN) de cada uno de los cuatro servidores de mensajería unificada de Exchange en el SAN.</span><span class="sxs-lookup"><span data-stu-id="86635-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="86635-131">**Ejemplo 2: Resistencia de la mensajería unificada de Exchange**</span><span class="sxs-lookup"><span data-stu-id="86635-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="86635-132">![Ejemplo 2 de Mensajería unificada de Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Ejemplo 2 de Mensajería unificada de Exchange")</span><span class="sxs-lookup"><span data-stu-id="86635-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="86635-p106">En el Ejemplo 2, en condiciones normales de funcionamiento, los servidores de mensajería unificada de Exchange 1 y 2 están habilitados en el centro de datos de Tukwila, y los servidores de mensajería unificada de Exchange 3 y 4 están habilitados en el centro de datos de Dublín. Los cuatro servidores están incluidos en el plan de marcado URI del SIP de los usuarios de Tukwila; sin embargo, los servidores 3 y 4 están deshabilitados. En el caso de que se produzca una interrupción de la mensajería unificada de Exchange en Tukwila, por ejemplo, los servidores 1 y 2 de mensajería unificada de Exchange deben deshabilitarse y los servidores 3 y 4 de mensajería unificada de Exchange deben habilitarse para que el tráfico de mensajería unificada de Exchange de Tukwila se enrute a los servidores de Dublín.</span><span class="sxs-lookup"><span data-stu-id="86635-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="86635-136">Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Exchange 2013, consulte "integrar la mensajería unificada [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)de Exchange 2013 con Lync Server" en.</span><span class="sxs-lookup"><span data-stu-id="86635-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="86635-137">Para obtener más información sobre cómo habilitar o deshabilitar la mensajería unificada en Microsoft Exchange Server 2010, consulte:</span><span class="sxs-lookup"><span data-stu-id="86635-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="86635-138">"Habilitar mensajería unificada en Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)en.</span><span class="sxs-lookup"><span data-stu-id="86635-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="86635-139">"Deshabilitar mensajería unificada en Exchange 2010 [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)" en.</span><span class="sxs-lookup"><span data-stu-id="86635-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86635-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="86635-140">See Also</span></span>


[<span data-ttu-id="86635-141">Proceso de implementación de la integración de la mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86635-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

