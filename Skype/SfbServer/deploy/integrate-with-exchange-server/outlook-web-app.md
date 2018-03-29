---
title: Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumen: Integrar Skype para Business Server y Outlook Web App.'
ms.openlocfilehash: 4ac4d6a71f8006e813d09631f8ccf28742940ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-2015-and-outlook-web-app"></a><span data-ttu-id="0d756-103">Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="0d756-103">Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App</span></span>
 
<span data-ttu-id="0d756-104">**Resumen:** Integrar Skype para Business Server y Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="0d756-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>
  
<span data-ttu-id="0d756-105">Los clientes que utilizan Skype local para implementaciones de servidor de negocios 2015 pueden configurar interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange Online en un modo de implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="0d756-105">Customers who are using on-premises Skype for Business Server 2015 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="0d756-106">Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="0d756-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="0d756-107">Para habilitar esta integración, debe configurar el servidor perimetral en su Skype local para la implementación de Business Server realizando las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0d756-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span> 
  
- <span data-ttu-id="0d756-108">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="0d756-108">Configure a shared SIP address space</span></span>
    
- <span data-ttu-id="0d756-109">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="0d756-109">Configure a hosting provider on the Edge Server</span></span>
    
- <span data-ttu-id="0d756-110">Comprobar la replicación del almacén de Administración Central actualizado</span><span class="sxs-lookup"><span data-stu-id="0d756-110">Verify replication of the updated Central Management store</span></span>
    
## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="0d756-111">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="0d756-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="0d756-112">Para integrar Skype locales para el año 2015 de servidor empresariales con Exchange Online, debe configurar un espacio de direcciones compartido de SIP.</span><span class="sxs-lookup"><span data-stu-id="0d756-112">To integrate on-premises Skype for Business Server 2015 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="0d756-113">El mismo espacio de dirección de dominio SIP es compatible con Skype para Business Server y el servicio en línea de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0d756-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>
  
<span data-ttu-id="0d756-114">Mediante el Skype para negocios de Shell de administración de servidor, configure el servidor perimetral para la federación ejecutando el cmdlet **Set-CSAccessEdgeConfiguration** , con los parámetros que se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d756-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="0d756-115">**AllowFederatedUsers** parámetro especifica si se permiten que los usuarios internos comunicarse con usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="0d756-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="0d756-116">Esta propiedad también determina si los usuarios internos puedan comunicarse con usuarios en un escenario de espacio de direcciones compartido SIP con Skype para Business Server y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d756-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>
    
<span data-ttu-id="0d756-117">Para obtener más información acerca de cómo utilizar el Skype para negocios de Shell de administración de servidor, vea [Skype para el Shell de administración de negocio servidor 2015](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="0d756-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server 2015 Management Shell](../../manage/management-shell.md).</span></span>
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="0d756-118">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="0d756-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="0d756-119">Utilizando el Skype para negocios de Shell de administración de servidor, configurar un proveedor de hospedaje en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** , utilizando los parámetros en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d756-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="0d756-120">Si utiliza Office 365 operado por 21Vianet en China, reemplace el valor del parámetro **ProxyFqdn** de este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="0d756-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the **ProxyFqdn** parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>
  
- <span data-ttu-id="0d756-121">**Identidad** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="0d756-121">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="0d756-122">Los valores que contienen espacios deben aparecer en comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="0d756-122">Values that contain spaces must be in double quotes.</span></span>
    
- <span data-ttu-id="0d756-123">**Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada.</span><span class="sxs-lookup"><span data-stu-id="0d756-123">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="0d756-124">Este parámetro debe estar configurado en True.</span><span class="sxs-lookup"><span data-stu-id="0d756-124">This must be set to True.</span></span>
    
- <span data-ttu-id="0d756-125">**EnabledSharedAddressSpace** indica si se utilizará el proveedor de hospedaje en un escenario de espacio de direcciones compartido de SIP.</span><span class="sxs-lookup"><span data-stu-id="0d756-125">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="0d756-126">Este parámetro debe estar configurado en True.</span><span class="sxs-lookup"><span data-stu-id="0d756-126">This must be set to True.</span></span>
    
- <span data-ttu-id="0d756-127">**HostsOCSUsers** indica si se utiliza el proveedor de hospedaje para hospedar Office Communications Server o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d756-127">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="0d756-128">Este parámetro debe estar configurado en False.</span><span class="sxs-lookup"><span data-stu-id="0d756-128">This must be set to False.</span></span>
    
- <span data-ttu-id="0d756-129">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) del servidor proxy utilizado por el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="0d756-129">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="0d756-130">Para Exchange Online, el FQDN es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0d756-130">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>
    
- <span data-ttu-id="0d756-131">**IsLocal** indica si el servidor proxy utilizado por el proveedor de hospedaje está dentro de su Skype para la topología de servidores de empresa.</span><span class="sxs-lookup"><span data-stu-id="0d756-131">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="0d756-132">Este parámetro debe estar configurado en False.</span><span class="sxs-lookup"><span data-stu-id="0d756-132">This must be set to False.</span></span>
    
- <span data-ttu-id="0d756-133">**VerificationLevel** Indica el nivel de comprobación permitido para los mensajes que se envían a y desde el proveedor alojado.</span><span class="sxs-lookup"><span data-stu-id="0d756-133">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="0d756-134">Especifique **UseSourceVerification**, que se basa en el nivel de comprobación que se incluye en los mensajes enviados desde el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="0d756-134">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="0d756-135">Si no se especifica este nivel, se rechazará el mensaje como no comprobable.</span><span class="sxs-lookup"><span data-stu-id="0d756-135">If this level is not specified, the message will be rejected as being unverifiable.</span></span>
    
## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="0d756-136">Comprobar la replicación del almacén de administración central actualizada</span><span class="sxs-lookup"><span data-stu-id="0d756-136">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="0d756-137">Los cambios realizados mediante los cmdlets en las secciones anteriores se aplican automáticamente en el servidor perimetral y normalmente tardan menos de un minuto para replicar.</span><span class="sxs-lookup"><span data-stu-id="0d756-137">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="0d756-138">Puede validar el estado de la replicación y, a continuación, confirme que los cambios se aplicaron a su servidor perimetral utilizando los siguientes cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0d756-138">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>
  
<span data-ttu-id="0d756-139">Para comprobar las actualizaciones de replicación en un servidor interno en su Skype para la implementación de Business Server, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d756-139">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>
  
```
Get-CsManagementStoreReplicationStatus
```

<span data-ttu-id="0d756-140">Para confirmar que se han aplicado los cambios en el servidor perimetral, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d756-140">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a><span data-ttu-id="0d756-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d756-141">See also</span></span>

#### 

[<span data-ttu-id="0d756-142">Proporcionar Skype para Business Server 2015 correo en MU de Exchange alojado de voz de los usuarios</span><span class="sxs-lookup"><span data-stu-id="0d756-142">Providing Skype for Business Server 2015 users voice mail on hosted Exchange UM</span></span>](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[<span data-ttu-id="0d756-143">Alojado Exchange integración de mensajería unificada en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d756-143">Hosted Exchange Unified Messaging integration in Skype for Business Server 2015</span></span>](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)

