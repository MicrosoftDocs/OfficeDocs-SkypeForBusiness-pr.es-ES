---
title: Configuración de la integración de Lync Server local con Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae1ba45ace830f33b239bf2f8ead1a75fcee3417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="e6531-102">Configuración de la integración de Lync Server 2013 local con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e6531-102">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6531-103">_**Última modificación del tema:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="e6531-103">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="e6531-104">Los clientes que usan las implementaciones locales de Lync Server 2013 pueden configurar la interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange online en modo de implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="e6531-104">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="e6531-105">Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="e6531-105">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="e6531-106">Para habilitar esta integración, debe configurar el servidor perimetral en la implementación de Lync Server local completando las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e6531-106">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="e6531-107">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="e6531-107">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="e6531-108">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e6531-108">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="e6531-109">Comprobar la replicación del almacén de administración central actualizado</span><span class="sxs-lookup"><span data-stu-id="e6531-109">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="e6531-110">Si Lync Server 2013 está integrado en Exchange Online, un usuario que está intentando iniciar sesión en mensajería instantánea desde OWA se considera un usuario remoto o externo.</span><span class="sxs-lookup"><span data-stu-id="e6531-110">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="e6531-111">En este escenario, este usuario debe tener una directiva de acceso externo asignada que tenga la siguiente opción seleccionada:</span><span class="sxs-lookup"><span data-stu-id="e6531-111">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="e6531-112">**Habilitar las comunicaciones con usuarios remotos**</span><span class="sxs-lookup"><span data-stu-id="e6531-112">**Enable communications with remote users**</span></span>

<span data-ttu-id="e6531-113">Habilite esta opción si quiere que los usuarios de su organización que estén fuera del firewall, como teletrabajadores y usuarios que viajan, puedan conectarse a Lync Server a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="e6531-113">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="e6531-114">Para obtener más información, vea [administrar la Directiva de acceso externo en Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e6531-114">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="e6531-115">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="e6531-115">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="e6531-116">Para integrar Lync Server local 2013 con Exchange Online, debe configurar un espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="e6531-116">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="e6531-117">El mismo espacio de direcciones de dominio SIP es compatible con Lync Server y el servicio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6531-117">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="e6531-118">Con el shell de administración de Lync Server, configure el servidor perimetral para la Federación ejecutando el cmdlet **set-CSAccessEdgeConfiguration** , usando los parámetros que se muestran en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6531-118">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="e6531-119">\*\*AllowFederatedUsers \*\* especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="e6531-119">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="e6531-120">Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Lync Server y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e6531-120">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="e6531-121">Para obtener más información sobre cómo usar el shell de administración de Lync Server, consulte [consola de administración de Lync server 2013](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="e6531-121">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="e6531-122">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e6531-122">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="e6531-123">Use el shell de administración de Lync Server para configurar un proveedor de hospedaje en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="e6531-123">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="e6531-124">Para ello, ejecute el cmdlet **New-CsHostingProvider** con los parámetros del siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e6531-124">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="e6531-125">Si utiliza Office 365 operado por 21Vianet en China, reemplace el valor del parámetro <STRONG>ProxyFqdn</STRONG> de este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="e6531-125">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="e6531-126">**Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="e6531-126">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="e6531-127">Los valores que contienen espacios deben ir entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="e6531-127">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="e6531-128">\*\*Habilitada \*\* indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e6531-128">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="e6531-129">Debe establecerse en **true**.</span><span class="sxs-lookup"><span data-stu-id="e6531-129">This must be set to **True**.</span></span>

  - <span data-ttu-id="e6531-130">**EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="e6531-130">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="e6531-131">Debe establecerse en **true**.</span><span class="sxs-lookup"><span data-stu-id="e6531-131">This must be set to **True**.</span></span>

  - <span data-ttu-id="e6531-132">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6531-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="e6531-133">Debe establecerse en **false**.</span><span class="sxs-lookup"><span data-stu-id="e6531-133">This must be set to **False**.</span></span>

  - <span data-ttu-id="e6531-134">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="e6531-134">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="e6531-135">Para Exchange Online, el FQDN es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e6531-135">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="e6531-136">**IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6531-136">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="e6531-137">Debe establecerse en **false**.</span><span class="sxs-lookup"><span data-stu-id="e6531-137">This must be set to **False**.</span></span>

  - <span data-ttu-id="e6531-138">**VerificationLevel** indica el nivel de comprobación permitido para los mensajes que se envían al proveedor hospedado y desde él.</span><span class="sxs-lookup"><span data-stu-id="e6531-138">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="e6531-139">Especifique **UseSourceVerification**.</span><span class="sxs-lookup"><span data-stu-id="e6531-139">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="e6531-140">Esta opción se basa en el nivel de comprobación que está incluido en los mensajes que se envían desde el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="e6531-140">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="e6531-141">Si no se especifica este nivel, el mensaje se rechazará como no verificable.</span><span class="sxs-lookup"><span data-stu-id="e6531-141">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="e6531-142">Comprobar la replicación del almacén de administración central actualizada</span><span class="sxs-lookup"><span data-stu-id="e6531-142">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="e6531-143">Los cambios que realizó usando los cmdlets de las secciones anteriores se aplican automáticamente al servidor perimetral y generalmente tardan menos de un minuto en replicarse.</span><span class="sxs-lookup"><span data-stu-id="e6531-143">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="e6531-144">Puede comprobar el estado de replicación y que se aplicaron los cambios a su servidor perimetral mediante los cmdlets siguientes.</span><span class="sxs-lookup"><span data-stu-id="e6531-144">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="e6531-145">Para comprobar las actualizaciones de replicación en un servidor interno de la implementación de Lync Server, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e6531-145">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="e6531-146">Para comprobar que se han aplicado los cambios, ejecute el siguiente cmdlet en el servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="e6531-146">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6531-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6531-147">See Also</span></span>


[<span data-ttu-id="e6531-148">Proporcionar correo de voz a usuarios de Lync Server 2013 en la mensajería unificada de Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="e6531-148">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="e6531-149">Integración de la mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6531-149">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

