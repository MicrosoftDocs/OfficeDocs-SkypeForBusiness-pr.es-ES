---
title: Configurar el servidor perimetral para la integración con mensajería unificada de Exchange hospedada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91002410e4079abf62a3931f4fbbb3f5dadb3acb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="39f53-102">Configurar el servidor perimetral para la integración con mensajería unificada de Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="39f53-102">Configure the Edge Server for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39f53-103">_**Última modificación del tema:** 2015-01-23_</span><span class="sxs-lookup"><span data-stu-id="39f53-103">_**Topic Last Modified:** 2015-01-23_</span></span>

<span data-ttu-id="39f53-104">Para proporcionar a los usuarios de Lync Server 2013 las funciones de correo de voz en la mensajería unificada (UM) de Exchange hospedada, debe realizar las siguientes tareas de configuración en el servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="39f53-104">To provide your Lync Server 2013 users with voice mail capabilities on hosted Exchange Unified Messaging (UM), you must perform the following configuration tasks on the Edge Server:</span></span>

  - <span data-ttu-id="39f53-105">Configure el servidor perimetral para la federación.</span><span class="sxs-lookup"><span data-stu-id="39f53-105">Configure the Edge Server for federation.</span></span>

  - <span data-ttu-id="39f53-106">Replicar los datos del almacén de administración central en el servidor perimetral y comprobar la replicación.</span><span class="sxs-lookup"><span data-stu-id="39f53-106">Replicate Central Management store data to the Edge Server and verify the replication.</span></span>

  - <span data-ttu-id="39f53-107">Crear un proveedor de hospedaje en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="39f53-107">Create a hosting provider on the Edge Server.</span></span>

<span data-ttu-id="39f53-108">Para obtener más información, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="39f53-108">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="39f53-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="39f53-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="39f53-110">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="39f53-110">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="39f53-111">Debe crear un registro SRV de DNS externo para el servicio Exchange de hospedaje antes de realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="39f53-111">You must create an external DNS SRV record for the hosting Exchange service before you perform these steps.</span></span> <span data-ttu-id="39f53-112">Para obtener más información, vea <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">crear un registro SRV de DNS para la integración con mensajería unificada de Exchange hospedado</A>.</span><span class="sxs-lookup"><span data-stu-id="39f53-112">For details, see <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Create a DNS SRV record for integration with hosted Exchange UM</A>.</span></span>



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a><span data-ttu-id="39f53-113">Para configurar el servidor perimetral para la federación.</span><span class="sxs-lookup"><span data-stu-id="39f53-113">To configure the Edge Server for federation</span></span>

1.  <span data-ttu-id="39f53-114">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="39f53-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="39f53-p102">Ejecute el cmdlet Set-CsAccessEdgeConfiguration para configurar el servidor para la federación. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39f53-p102">Run the Set-CsAccessEdgeConfiguration cmdlet to configure the server for federation. For example, run:</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    <span data-ttu-id="39f53-117">En el ejemplo anterior se definen los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="39f53-117">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="39f53-118">**UseDnsSrvRouting** especifica que los servidores perimetrales confiarán en los registros DNS SRV al enviar y recibir solicitudes de federación.</span><span class="sxs-lookup"><span data-stu-id="39f53-118">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="39f53-p103">**AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados. Esta propiedad también determina si los usuarios internos pueden comunicarse con usuarios en una situación de dominio dividido.</span><span class="sxs-lookup"><span data-stu-id="39f53-p103">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="39f53-121">**EnablePartnerDiscovery** especifica si Lync Server usará registros DNS para intentar detectar dominios asociados que no aparecen en la lista de dominios permitidos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39f53-121">**EnablePartnerDiscovery** specifies whether Lync Server will use DNS records to try to discover partner domains not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="39f53-122">Si es false, Lync Server 2013 solo se federarse con los dominios que se encuentran en la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="39f53-122">If False, Lync Server 2013 will only federate with domains found on the allowed domains list.</span></span> <span data-ttu-id="39f53-123">Este parámetro es necesario si se usa el enrutamiento del servicio DNS.</span><span class="sxs-lookup"><span data-stu-id="39f53-123">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="39f53-124">En la mayoría de las instalaciones, el valor se establece en False para evitar la apertura de la federación a todos los socios.</span><span class="sxs-lookup"><span data-stu-id="39f53-124">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a><span data-ttu-id="39f53-125">Para replicar los datos en el servidor perimetral y comprobar la replicación.</span><span class="sxs-lookup"><span data-stu-id="39f53-125">To replicate data to the Edge Server and verify the replication</span></span>

  - <span data-ttu-id="39f53-126">Compruebe que la replicación de datos en el servidor perimetral se haya completado.</span><span class="sxs-lookup"><span data-stu-id="39f53-126">Verify that the replication to the Edge Server is complete.</span></span> <span data-ttu-id="39f53-127">Para consultar el procedimiento, consulte [Verify Connectivity between Internal Servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="39f53-127">For the procedure, see [Verify connectivity between internal servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span></span>

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="39f53-128">Para crear un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="39f53-128">To create a hosting provider on the Edge Server</span></span>

1.  <span data-ttu-id="39f53-129">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="39f53-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="39f53-130">Ejecute el cmdlet **New-CsHostingProvider** para configurar el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="39f53-130">Run the **New-CsHostingProvider** cmdlet to configure the hosting provider.</span></span> <span data-ttu-id="39f53-131">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39f53-131">For example, run:</span></span>
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="39f53-132">En el ejemplo anterior se definen los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="39f53-132">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="39f53-p107">**Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear, en este ejemplo es **Fabrikam.com**. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor con dicho valor de Identity.</span><span class="sxs-lookup"><span data-stu-id="39f53-p107">**Identity** specifies a unique string value identifier for the hosting provider you are creating, in this example, **Fabrikam.com**. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="39f53-p108">**Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True**.</span><span class="sxs-lookup"><span data-stu-id="39f53-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="39f53-137">**EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).</span><span class="sxs-lookup"><span data-stu-id="39f53-137">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="39f53-138">Antes de establecer <CODE>EnableSharedAddressSpace</CODE> en true, intente resolver el registro SRV de Federación internamente.</span><span class="sxs-lookup"><span data-stu-id="39f53-138">Before you set <CODE>EnableSharedAddressSpace</CODE> to True, try to resolve the Federation SRV record internally.</span></span> <span data-ttu-id="39f53-139">Si este registro no se puede resolver internamente, debe crear los registros _sipfederationtls. _tcp. &lt;domain&gt; y _sip. _tls. &lt;dominio&gt; en el DNS interno.</span><span class="sxs-lookup"><span data-stu-id="39f53-139">If this record cannot be resolved internally, then you need to create the records, _sipfederationtls._tcp.&lt;domain&gt; and _sip._tls.&lt;domain&gt; in the internal DNS.</span></span> <span data-ttu-id="39f53-140">Estos registros deben apuntar a la dirección IP externa de la interfaz de acceso del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="39f53-140">These records should point to the external IP address of the Access Interface of the Edge Server.</span></span>

        
        </div>
    
      - <span data-ttu-id="39f53-141">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39f53-141">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="39f53-142">Si es **False**, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="39f53-142">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="39f53-p111">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje, que en este ejemplo es **proxyserver.fabrikam.com**. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.</span><span class="sxs-lookup"><span data-stu-id="39f53-p111">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, in this example, **proxyserver.fabrikam.com**. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="39f53-146">**IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39f53-146">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span>
    
      - <span data-ttu-id="39f53-147">**VerficationLevel** indica el nivel de comprobación permitido para los mensajes enviados a y desde el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="39f53-147">**VerficationLevel** indicates the allowed verification level for messages sent to and from the hosted provider.</span></span> <span data-ttu-id="39f53-148">Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="39f53-148">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="39f53-149">Si no se especifica el nivel, se rechazará el mensaje como no verificable.</span><span class="sxs-lookup"><span data-stu-id="39f53-149">If this level is not specified, then the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="39f53-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="39f53-150">See Also</span></span>


[<span data-ttu-id="39f53-151">Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral</span><span class="sxs-lookup"><span data-stu-id="39f53-151">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[<span data-ttu-id="39f53-152">Comprobar la conectividad entre servidores internos y servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39f53-152">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


<span data-ttu-id="39f53-153">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="39f53-153">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

