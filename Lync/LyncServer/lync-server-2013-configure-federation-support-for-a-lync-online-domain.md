---
title: 'Lync Server 2013: configurar la compatibilidad con la Federación para un dominio de Lync Online'
description: 'Lync Server 2013: configurar la compatibilidad con la Federación para un dominio de Lync Online.'
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
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553306"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="11c11-103">Configurar la compatibilidad de Federación para un dominio de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c11-103">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c11-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="11c11-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="11c11-105">Para federar con un cliente de Microsoft Lync Online 2010, es necesario completar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="11c11-105">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="11c11-106">Configure la compatibilidad para el dominio del cliente de Lync Online 2010 (por ejemplo, contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="11c11-106">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="11c11-107">Como se especifica en la sección [requisitos previos para federar con un cliente de Lync Online en Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) de esta documentación, debe haber habilitado la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="11c11-107">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="11c11-108">Para ello, se debe especificar el método que se usará para controlar el acceso por dominios federados.</span><span class="sxs-lookup"><span data-stu-id="11c11-108">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="11c11-109">Si configuró su organización para que use detección, es opcional agregar el dominio a la lista permitida de su organización.</span><span class="sxs-lookup"><span data-stu-id="11c11-109">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="11c11-110">Si no ha habilitado la detección de dominios, debe agregar el nombre de dominio del cliente de Lync Online a la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="11c11-110">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="11c11-111">Puede Agregar un nombre de dominio mediante el panel de control de Lync Server o mediante la ejecución del cmdlet **New-CSAllowedDomain** .</span><span class="sxs-lookup"><span data-stu-id="11c11-111">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="11c11-112">Para obtener información detallada sobre cómo usar el panel de control de Lync Server, incluida la habilitación de la detección de dominios, vea [Manage SIP Federated Providers for your Organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="11c11-112">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="11c11-113">Para obtener información detallada sobre cómo usar el cmdlet **New-CSAllowedDomain** para agregar un dominio, consulte [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="11c11-113">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11c11-114">Un cliente de Lync Online puede tener varios dominios.</span><span class="sxs-lookup"><span data-stu-id="11c11-114">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="11c11-115">Si desea federarse con más de uno de los dominios, debe configurar la compatibilidad para cada dominio con el que desee admitir la Federación, y el administrador del cliente de Lync Online debe habilitar la Federación para cada uno de los dominios que se va a federar.</span><span class="sxs-lookup"><span data-stu-id="11c11-115">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="11c11-116">Configure la compatibilidad para el proveedor de hospedaje del dominio de cliente de Lync Online 2010 con el que quiera federar.</span><span class="sxs-lookup"><span data-stu-id="11c11-116">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="11c11-117">Use el procedimiento de esta sección para configurar la compatibilidad para el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="11c11-117">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11c11-118">Este paso solo es necesario para la Federación con un dominio de un cliente de Lync Online, no para la Federación con ningún dominio implementado localmente en la ubicación de un socio federado.</span><span class="sxs-lookup"><span data-stu-id="11c11-118">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="11c11-119">Para configurar compatibilidad para un proveedor de hospedaje</span><span class="sxs-lookup"><span data-stu-id="11c11-119">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="11c11-120">En un servidor front-end, inicie el shell de administración de Lync Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="11c11-120">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="11c11-121">Ejecute el cmdlet de **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="11c11-121">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="11c11-122">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11c11-122">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="11c11-123">En el ejemplo anterior se definen los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="11c11-123">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="11c11-p105">**Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor existente con dicho valor de Identity.</span><span class="sxs-lookup"><span data-stu-id="11c11-p105">**Identity** specifies a unique string value identifier for the hosting provider that you are creating. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="11c11-p106">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, usted tendrá que eliminar y volver a crear la entrada de dicho proveedor.</span><span class="sxs-lookup"><span data-stu-id="11c11-p106">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="11c11-129">**VerificationLevel** indica de qué manera se comprueban (y si se comprueban) los mensajes enviados desde un proveedor de hospedaje para asegurar que se enviaron realmente desde dicho proveedor.</span><span class="sxs-lookup"><span data-stu-id="11c11-129">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="11c11-p107">**Enabled** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True**.</span><span class="sxs-lookup"><span data-stu-id="11c11-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="11c11-132">**EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).</span><span class="sxs-lookup"><span data-stu-id="11c11-132">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="11c11-133">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11c11-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="11c11-134">Si es **False**, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="11c11-134">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="11c11-135">**IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11c11-135">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="11c11-136">Para obtener información detallada sobre cómo usar este cmdlet, vea [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="11c11-136">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

