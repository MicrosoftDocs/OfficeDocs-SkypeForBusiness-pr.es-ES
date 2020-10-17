---
title: Configuración de la integración de Lync Server local con Exchange Online
description: Configuración de la integración de Lync Server local con Exchange Online.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c612bcdcdf4803bd6f9f2b38f1f9bb7dbad016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553942"
---
# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="ec90a-103">Configuración de la integración de Lync Server 2013 local con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ec90a-103">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec90a-104">_**Última modificación del tema:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="ec90a-104">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="ec90a-105">Los clientes que usan las implementaciones locales de Lync Server 2013 pueden configurar la interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange online en un modo de implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="ec90a-105">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="ec90a-106">Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ec90a-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="ec90a-107">Para habilitar esta integración, debe configurar el servidor perimetral en su implementación local de Lync Server llevando a cabo las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="ec90a-107">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="ec90a-108">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="ec90a-108">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="ec90a-109">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ec90a-109">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="ec90a-110">Comprobar la replicación del almacén de administración central actualizado</span><span class="sxs-lookup"><span data-stu-id="ec90a-110">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="ec90a-111">Si Lync Server 2013 está integrado en Exchange Online, un usuario que está intentando iniciar sesión en mensajería instantánea desde OWA se considera un usuario remoto o externo.</span><span class="sxs-lookup"><span data-stu-id="ec90a-111">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="ec90a-112">En este escenario, este usuario debe tener asignada una directiva de acceso externo que tenga la siguiente opción seleccionada:</span><span class="sxs-lookup"><span data-stu-id="ec90a-112">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="ec90a-113">**Habilitar comunicaciones con usuarios remotos**</span><span class="sxs-lookup"><span data-stu-id="ec90a-113">**Enable communications with remote users**</span></span>

<span data-ttu-id="ec90a-114">Habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Lync Server a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="ec90a-114">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="ec90a-115">Para obtener más información, consulte [administrar la Directiva de acceso externo en Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ec90a-115">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="ec90a-116">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="ec90a-116">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="ec90a-117">Para integrar Lync Server 2013 local con Exchange Online, debe configurar un espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="ec90a-117">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="ec90a-118">Lync Server y el servicio de Exchange Online admiten el mismo espacio de direcciones de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="ec90a-118">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="ec90a-119">Mediante el shell de administración de Lync Server, configure el servidor perimetral para la Federación ejecutando el cmdlet **set-CSAccessEdgeConfiguration** , usando los parámetros que se muestran en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ec90a-119">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="ec90a-120">**AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="ec90a-120">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="ec90a-121">Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Lync Server y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ec90a-121">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="ec90a-122">Para obtener más información sobre cómo usar el shell de administración de Lync Server, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ec90a-122">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ec90a-123">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ec90a-123">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="ec90a-124">Use el shell de administración de Lync Server para configurar un proveedor de hospedaje en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="ec90a-124">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="ec90a-125">Para ello, ejecute el cmdlet **New-CsHostingProvider** con los parámetros del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec90a-125">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="ec90a-126">Si usa Office 365 ofrecido por 21Vianet en China, reemplace el valor del parámetro <STRONG>ProxyFqdn</STRONG> en este ejemplo ("EXAP.um.Outlook.com") por el FQDN para el servicio ofrecido por 21Vianet: "EXAP.um.Partner.Outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="ec90a-126">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="ec90a-127">**Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="ec90a-127">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="ec90a-128">Los valores que contienen espacios deben estar entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="ec90a-128">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="ec90a-129">**Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ec90a-129">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ec90a-130">Debe establecerse en **true**.</span><span class="sxs-lookup"><span data-stu-id="ec90a-130">This must be set to **True**.</span></span>

  - <span data-ttu-id="ec90a-131">**EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="ec90a-131">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ec90a-132">Debe establecerse en **true**.</span><span class="sxs-lookup"><span data-stu-id="ec90a-132">This must be set to **True**.</span></span>

  - <span data-ttu-id="ec90a-133">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec90a-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="ec90a-134">Debe establecerse en **false**.</span><span class="sxs-lookup"><span data-stu-id="ec90a-134">This must be set to **False**.</span></span>

  - <span data-ttu-id="ec90a-135">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="ec90a-135">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="ec90a-136">Para Exchange Online, el FQDN es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ec90a-136">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="ec90a-137">**IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec90a-137">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="ec90a-138">Debe establecerse en **false**.</span><span class="sxs-lookup"><span data-stu-id="ec90a-138">This must be set to **False**.</span></span>

  - <span data-ttu-id="ec90a-139">**VerificationLevel** indica el nivel de comprobación permitido para los mensajes que se envían a y desde el proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="ec90a-139">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="ec90a-140">Especifique **UseSourceVerification**.</span><span class="sxs-lookup"><span data-stu-id="ec90a-140">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="ec90a-141">Esta opción se basa en el nivel de comprobación que se incluye en los mensajes que se envían desde el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="ec90a-141">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="ec90a-142">Si no se especifica este nivel, el mensaje se rechazará como no comprobable.</span><span class="sxs-lookup"><span data-stu-id="ec90a-142">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="ec90a-143">Comprobar la replicación del almacén de administración central actualizada</span><span class="sxs-lookup"><span data-stu-id="ec90a-143">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="ec90a-144">Los cambios que realizó mediante los cmdlets de las secciones anteriores se aplican automáticamente al servidor perimetral y generalmente tardan menos de un minuto en replicarse.</span><span class="sxs-lookup"><span data-stu-id="ec90a-144">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="ec90a-145">Puede comprobar el estado de replicación y que los cambios se aplicaron a su servidor perimetral mediante los siguientes cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ec90a-145">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="ec90a-146">Para comprobar las actualizaciones de replicación en un servidor interno de la implementación de Lync Server, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ec90a-146">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="ec90a-147">Para comprobar que se han aplicado los cambios, ejecute el siguiente cmdlet en el servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="ec90a-147">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ec90a-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec90a-148">See Also</span></span>


[<span data-ttu-id="ec90a-149">Suministro de correo de voz de los usuarios de Lync Server 2013 en mensajería unificada de Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="ec90a-149">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="ec90a-150">Integración de mensajería unificada de Exchange hospedada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec90a-150">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
