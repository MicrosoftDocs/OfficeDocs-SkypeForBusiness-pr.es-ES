---
title: 'Lync Server 2013: configurar la compatibilidad de Federación para un dominio de Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="da9ab-102">Configurar la compatibilidad de Federación para un dominio de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da9ab-102">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da9ab-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="da9ab-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="da9ab-104">La Federación con un cliente de Microsoft Lync Online 2010 requiere que complete los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="da9ab-104">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="da9ab-105">Configure la compatibilidad del dominio del cliente de Lync Online 2010 (por ejemplo, contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="da9ab-105">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="da9ab-106">Según se especifica en la sección [requisitos previos para federar con un cliente de Lync Online en Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) de esta documentación, debe haber habilitado la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="da9ab-106">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="da9ab-107">Habilitar la Federación requiere especificar el método que se va a usar para controlar el acceso de los dominios federados.</span><span class="sxs-lookup"><span data-stu-id="da9ab-107">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="da9ab-108">Si ha configurado su organización para usar la detección, agregar el dominio a la lista de permitidos de la organización es opcional.</span><span class="sxs-lookup"><span data-stu-id="da9ab-108">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="da9ab-109">Si no ha habilitado la detección de dominios, debe agregar el nombre de dominio del cliente de Lync Online a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="da9ab-109">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="da9ab-110">Puede Agregar un nombre de dominio con el panel de control de Lync Server o ejecutando el cmdlet **New-CSAllowedDomain** .</span><span class="sxs-lookup"><span data-stu-id="da9ab-110">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="da9ab-111">Para obtener detalles sobre el uso del panel de control de Lync Server, incluido el descubrimiento de dominios, consulte [administrar proveedores federados SIP para su organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="da9ab-111">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="da9ab-112">Para obtener más información sobre cómo usar el cmdlet **New-CSAllowedDomain** para agregar un dominio, vea [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="da9ab-112">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da9ab-113">Un cliente de Lync Online puede tener varios dominios.</span><span class="sxs-lookup"><span data-stu-id="da9ab-113">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="da9ab-114">Si desea federar con más de uno de los dominios, debe configurar la compatibilidad para cada dominio con el que desee admitir la Federación, y el administrador del cliente de Lync Online debe habilitar la Federación de cada uno de los dominios que se van a federar.</span><span class="sxs-lookup"><span data-stu-id="da9ab-114">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="da9ab-115">Configure la compatibilidad para el proveedor de hospedaje del dominio de cliente de Lync Online 2010 con el que desea federar.</span><span class="sxs-lookup"><span data-stu-id="da9ab-115">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="da9ab-116">Use el procedimiento de esta sección para configurar la compatibilidad con el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="da9ab-116">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da9ab-117">Este paso solo es necesario para la Federación con un dominio de un cliente de Lync Online, no para la Federación con cualquier dominio que se implemente localmente en la ubicación de un socio federado.</span><span class="sxs-lookup"><span data-stu-id="da9ab-117">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="da9ab-118">Para configurar la compatibilidad con un proveedor de hospedaje</span><span class="sxs-lookup"><span data-stu-id="da9ab-118">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="da9ab-119">Desde un servidor front-end, inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="da9ab-119">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="da9ab-120">Ejecute el cmdlet **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="da9ab-120">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="da9ab-121">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da9ab-121">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="da9ab-122">En el ejemplo anterior se definen los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="da9ab-122">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="da9ab-123">**Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando.</span><span class="sxs-lookup"><span data-stu-id="da9ab-123">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="da9ab-124">Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor con dicho valor de Identity.</span><span class="sxs-lookup"><span data-stu-id="da9ab-124">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="da9ab-125">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="da9ab-125">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="da9ab-126">Este valor no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="da9ab-126">This value cannot be modified.</span></span> <span data-ttu-id="da9ab-127">Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.</span><span class="sxs-lookup"><span data-stu-id="da9ab-127">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="da9ab-128">**VerificationLevel** especifica cómo (o si) se comprueban los mensajes enviados desde un proveedor de hospedaje para asegurarse de que se han enviado desde ese proveedor.</span><span class="sxs-lookup"><span data-stu-id="da9ab-128">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="da9ab-p107">\*\*Habilitada \*\* indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como \*\*True \*\*.</span><span class="sxs-lookup"><span data-stu-id="da9ab-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="da9ab-131">\*\*EnabledSharedAddressSpace \*\* indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).</span><span class="sxs-lookup"><span data-stu-id="da9ab-131">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="da9ab-132">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da9ab-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="da9ab-133">Si es \*\*False \*\*, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="da9ab-133">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="da9ab-134">**IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da9ab-134">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="da9ab-135">Para obtener más información sobre el uso de este cmdlet, vea [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="da9ab-135">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

