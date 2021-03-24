---
title: Configurar la integración entre Skype Empresarial Server local y Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumen: integrar Skype Empresarial Server y Outlook Web App.'
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109696"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="79e76-103">Configurar la integración entre Skype Empresarial Server local y Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="79e76-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="79e76-104">**Resumen:** Integrar Skype Empresarial Server y Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="79e76-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="79e76-105">Los clientes que usan implementaciones locales de Skype Empresarial Server pueden configurar la interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange Online en un modo de implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="79e76-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="79e76-106">Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="79e76-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="79e76-107">Para habilitar esta integración, debe configurar el servidor perimetral en la implementación local de Skype Empresarial Server completando las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="79e76-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="79e76-108">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="79e76-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="79e76-109">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="79e76-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="79e76-110">Comprobar la replicación del almacén de administración central actualizado</span><span class="sxs-lookup"><span data-stu-id="79e76-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="79e76-111">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="79e76-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="79e76-112">Para integrar Skype Empresarial Server local con Exchange Online, debe configurar un espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="79e76-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="79e76-113">El mismo espacio de direcciones de dominio SIP es compatible con Skype Empresarial Server y el servicio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="79e76-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="79e76-114">Con el Shell de administración de Skype Empresarial Server, configure el servidor perimetral para la federación ejecutando el cmdlet **Set-CSAccessEdgeConfiguration,** con los parámetros que se muestran en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="79e76-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="79e76-115">El parámetro **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="79e76-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="79e76-116">Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Skype Empresarial Server y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="79e76-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="79e76-117">Para obtener más información acerca del uso del Shell de administración de Skype Empresarial Server, vea Shell de administración [de Skype Empresarial Server](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="79e76-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="79e76-118">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="79e76-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="79e76-119">Con el Shell de administración de Skype Empresarial Server, configure un proveedor de hospedaje en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider,** usando los parámetros del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="79e76-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="79e76-120">Si usa Microsoft 365 u Office 365 operado por 21Vianet en China, reemplace el valor del parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="79e76-120">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="79e76-121">Si usa Microsoft 365 u Office 365 GCC High, reemplace el valor del parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") por el FQDN de GCC High: "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="79e76-121">If you are using Microsoft 365 or Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="79e76-122">**Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="79e76-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="79e76-123">Los valores que contienen espacios deben aparecer en comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="79e76-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="79e76-124">**Habilitada** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada.</span><span class="sxs-lookup"><span data-stu-id="79e76-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="79e76-125">Este parámetro debe estar configurado en True.</span><span class="sxs-lookup"><span data-stu-id="79e76-125">This must be set to True.</span></span>

- <span data-ttu-id="79e76-126">**EnabledSharedAddressSpace** indica si se usará el proveedor de hospedaje en un escenario de espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="79e76-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="79e76-127">Este parámetro debe estar configurado en True.</span><span class="sxs-lookup"><span data-stu-id="79e76-127">This must be set to True.</span></span>

- <span data-ttu-id="79e76-128">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="79e76-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="79e76-129">Este parámetro debe estar configurado en False.</span><span class="sxs-lookup"><span data-stu-id="79e76-129">This must be set to False.</span></span>

- <span data-ttu-id="79e76-130">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="79e76-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="79e76-131">Para Exchange Online, el FQDN es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="79e76-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="79e76-132">**IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está contenido en la topología de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="79e76-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="79e76-133">Este parámetro debe estar configurado en False.</span><span class="sxs-lookup"><span data-stu-id="79e76-133">This must be set to False.</span></span>

- <span data-ttu-id="79e76-134">**VerificationLevel** Indica el nivel de comprobación permitido para los mensajes que se envían al proveedor hospedado y desde este.</span><span class="sxs-lookup"><span data-stu-id="79e76-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="79e76-135">Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="79e76-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="79e76-136">Si no se especifica este nivel, el mensaje se rechazará por no serverificable.</span><span class="sxs-lookup"><span data-stu-id="79e76-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="79e76-137">Comprobar la replicación del almacén de administración central actualizada</span><span class="sxs-lookup"><span data-stu-id="79e76-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="79e76-138">Los cambios realizados mediante el uso de los cmdlets de las secciones anteriores se aplican automáticamente al servidor perimetral y, por lo general, tardar menos de un minuto en replicarse.</span><span class="sxs-lookup"><span data-stu-id="79e76-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="79e76-139">Puede validar el estado de replicación y, a continuación, confirmar que los cambios se aplicaron al servidor perimetral mediante los cmdlets siguientes.</span><span class="sxs-lookup"><span data-stu-id="79e76-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="79e76-140">Para comprobar las actualizaciones de replicación, en un servidor interno de la implementación de Skype Empresarial Server, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="79e76-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```powershell
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="79e76-141">Compruebe si el valor UpToDate muestra TRUE para todas las réplicas.</span><span class="sxs-lookup"><span data-stu-id="79e76-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="79e76-142">Para confirmar que se aplicaron los cambios, en el servidor perimetral, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="79e76-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```powershell
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="79e76-143">Compruebe doblemente si la información mostrada coincide con los cambios confirmados en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="79e76-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="79e76-144">Ver también</span><span class="sxs-lookup"><span data-stu-id="79e76-144">See also</span></span>

[<span data-ttu-id="79e76-145">Proporcionar correo de voz de usuarios de Skype Empresarial Server en mensajería unificada hospedada de Exchange</span><span class="sxs-lookup"><span data-stu-id="79e76-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[<span data-ttu-id="79e76-146">Integración de mensajería unificada de Exchange hospedada en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="79e76-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)