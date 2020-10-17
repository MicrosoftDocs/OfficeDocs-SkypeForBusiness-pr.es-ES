---
title: 'Lync Server 2013: arquitectura de integración de mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c2c16350ff111f31eb52a73290b1dbcddc9e580
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512587"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="ad0d2-102">Arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad0d2-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad0d2-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="ad0d2-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="ad0d2-104">La aplicación Lync Server 2013 ExUM de enrutamiento admite la integración con una implementación de mensajería unificada (UM) de Exchange local, con mensajería unificada de Exchange hospedada por un proveedor de servicios o con una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="ad0d2-105">En el siguiente diagrama se muestran las tres posibilidades.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="ad0d2-106">**Integración con una instalación de Exchange UM local y dos proveedores Exchange hospedados**</span><span class="sxs-lookup"><span data-stu-id="ad0d2-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="ad0d2-107">![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")</span><span class="sxs-lookup"><span data-stu-id="ad0d2-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="ad0d2-108">Se admiten los siguientes modos:</span><span class="sxs-lookup"><span data-stu-id="ad0d2-108">The following modes are supported:</span></span>

  - <span data-ttu-id="ad0d2-109">**Implementación local:** Lync Server 2013 y la mensajería unificada de Exchange se implementan en servidores locales de la empresa.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="ad0d2-110">**Implementación entre locales:** Lync Server 2013 se implementa en servidores locales de la empresa y la mensajería unificada de Exchange se hospeda en las instalaciones de un proveedor de servicios en línea, como un centro de datos de Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="ad0d2-111">**Implementación mixta:** La implementación de Lync Server 2013 tiene algunos buzones de usuario alojados en servidores de Exchange locales dentro de su empresa y algunos buzones de correo hospedados en un centro de datos de servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad0d2-112">La instalación mixta se puede usar a modo de solución transitoria durante la evaluación y migración por fases de usuarios a la mensajería unificada de Exchange o como solución permanente si opta por mantener algunos servicios de la mensajería unificada de Exchange de usuarios de forma local después de trasladar otros.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="ad0d2-113">Espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="ad0d2-113">Shared SIP Address Space</span></span>

<span data-ttu-id="ad0d2-114">Para integrar Lync Server 2013 con una implementación local de mensajería unificada de Exchange, debe conceder el permiso de Lync Server 2013 para leer los objetos de servicios de dominio de Active Directory UM de Exchange.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="ad0d2-115">Sin embargo, este enfoque no funciona para la integración con la mensajería unificada de Exchange, ya que Lync Server 2013 y mensajería unificada de Exchange se instalan en bosques independientes que no tienen ninguna confianza entre ellos.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="ad0d2-116">Para integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido*.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="ad0d2-117">En esta configuración, el mismo espacio de direcciones de dominio SIP está disponible para Lync Server 2013 y para el proveedor de servicios de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad0d2-118">El uso del espacio de direcciones SIP compartido es similar al método usado en un entorno entre locales de Lync Server 2013, en el que algunos usuarios están hospedados en la implementación local y otros están hospedados en una implementación hospedada (como Lync Online).</span><span class="sxs-lookup"><span data-stu-id="ad0d2-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="ad0d2-119">El dominio SIP se divide entre ellos.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-119">The SIP domain is split between them.</span></span> <span data-ttu-id="ad0d2-120">Al integrar Lync Server 2013 con mensajería unificada de Exchange hospedada, asegúrese de incluir el proveedor de servicios de mensajería unificada de Exchange en el espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="ad0d2-121">Para configurar el espacio de direcciones SIP compartido para la integración con un proveedor de servicios de mensajería unificada de Exchange, deberá configurar su servidor perimetral de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="ad0d2-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="ad0d2-122">Configure el servidor perimetral para la federación ejecutando el **Set-CsAccessEdgeConfiguration** cmdlet y estableciendo los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="ad0d2-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="ad0d2-123">**UseDnsSrvRouting** especifica que los servidores perimetrales confiarán en los registros DNS SRV al enviar y recibir solicitudes de federación.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="ad0d2-p105">**AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con usuarios en una situación de dominio dividido.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="ad0d2-126">**EnablePartnerDiscovery** especifica si Lync Server 2013 usará registros DNS para intentar detectar dominios asociados que no aparecen en la lista de dominios permitidos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="ad0d2-127">Si es false, Lync Server 2013 se federe solo con los dominios que se encuentran en la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="ad0d2-128">Este parámetro es necesario si se usa el enrutamiento del servicio DNS.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="ad0d2-129">En la mayoría de las instalaciones, el valor se establece en False para evitar la apertura de la federación a todos los socios.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="ad0d2-130">Replique el almacén de administración central en el servidor perimetral y Compruebe la replicación.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="ad0d2-131">Para obtener más información, consulte [exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="ad0d2-132">Configure un *proveedor de hospedaje* en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** y estableciendo los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="ad0d2-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="ad0d2-133">**Identidad** especifica un identificador de valor de cadena único para el proveedor de hospedaje que se está creando, como, por ejemplo, **Mensajería unificada de Exchange hospedada**.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="ad0d2-p108">**Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Debe estar establecido en **True**.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="ad0d2-p109">**EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido. Debe estar establecido en **True**.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-p109">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="ad0d2-138">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="ad0d2-139">Debe estar establecido en **False**.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="ad0d2-140">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) del servidor proxy que usa el proveedor de hospedaje, como, por ejemplo, **proxyserver.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="ad0d2-141">Póngase en contacto con el proveedor de hospedaje para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="ad0d2-142">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-142">This value cannot be modified.</span></span> <span data-ttu-id="ad0d2-143">Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="ad0d2-144">**IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="ad0d2-145">Debe estar establecido en **False**.</span><span class="sxs-lookup"><span data-stu-id="ad0d2-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

