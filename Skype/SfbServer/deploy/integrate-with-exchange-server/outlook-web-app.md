---
title: Configurar la integración entre local Skype para Business Server y Outlook Web App
ms.reviewer: ''
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
ms.openlocfilehash: 3bd5131fcdba3d3253021c711910b18f46e93ce4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216651"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a><span data-ttu-id="1f45c-103">Configurar la integración entre local Skype para Business Server y Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="1f45c-103">Configure integration between on-premises Skype for Business Server and Outlook Web App</span></span>

<span data-ttu-id="1f45c-104">**Resumen:** Integrar Skype para Business Server y Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="1f45c-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>

<span data-ttu-id="1f45c-105">Los clientes que usen local Skype para las implementaciones de Business Server pueden configurar interoperabilidad con Microsoft Outlook Web App en Microsoft Exchange Online en un modo de implementación híbrida.</span><span class="sxs-lookup"><span data-stu-id="1f45c-105">Customers who are using on-premises Skype for Business Server deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="1f45c-106">Las características de interoperabilidad incluyen el inicio de sesión único y la integración de mensajería instantánea (MI) y presencia en la interfaz de Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="1f45c-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="1f45c-107">Para habilitar esta integración, debe configurar el servidor perimetral en su Skype local para la implementación de Business Server al completar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f45c-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span>

- <span data-ttu-id="1f45c-108">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="1f45c-108">Configure a shared SIP address space</span></span>

- <span data-ttu-id="1f45c-109">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="1f45c-109">Configure a hosting provider on the Edge Server</span></span>

- <span data-ttu-id="1f45c-110">Comprobar la replicación del almacén de Administración Central actualizado</span><span class="sxs-lookup"><span data-stu-id="1f45c-110">Verify replication of the updated Central Management store</span></span>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="1f45c-111">Configurar un espacio de direcciones SIP compartido</span><span class="sxs-lookup"><span data-stu-id="1f45c-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="1f45c-112">Para integrar local Skype para Business Server con Exchange Online, debe configurar un espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="1f45c-112">To integrate on-premises Skype for Business Server with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="1f45c-113">El mismo espacio de dirección de dominio SIP es compatible con Skype para Business Server y el servicio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1f45c-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>

<span data-ttu-id="1f45c-114">Mediante el Skype para Shell de administración de servidor empresarial, configure el servidor perimetral para la federación ejecutando el cmdlet **Set-CSAccessEdgeConfiguration** , mediante los parámetros mostrados en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1f45c-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="1f45c-115">El parámetro **AllowFederatedUsers** especifica si los usuarios internos pueden comunicarse con usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="1f45c-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="1f45c-116">Esta propiedad también determina si los usuarios internos pueden comunicarse con los usuarios en un escenario de espacio de direcciones SIP compartido con Skype para Business Server y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1f45c-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>

<span data-ttu-id="1f45c-117">Para obtener información detallada sobre el uso de la Skype para Shell de administración de servidor empresarial, vea [Skype para Shell de administración de servidor empresarial](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="1f45c-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell](../../manage/management-shell.md).</span></span>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="1f45c-118">Configurar un proveedor de hospedaje en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="1f45c-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="1f45c-119">Mediante el Skype para Shell de administración de negocio Server, configure un proveedor de hospedaje en el servidor perimetral ejecutando el cmdlet **New-CsHostingProvider** , mediante los parámetros en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f45c-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="1f45c-120">Si utiliza Office 365 operado por 21Vianet en China, reemplace el valor del parámetro ProxyFqdn de este ejemplo ("exap.um.outlook.com") por el FQDN del servicio operado por 21Vianet: "exap.um.partner.outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="1f45c-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span> <span data-ttu-id="1f45c-121">Si usa Office 365 GCC alta, reemplace el valor para el parámetro ProxyFqdn en este ejemplo ("exap.um.outlook.com") con el FQDN de GCC alta: "exap.um.office365.us".</span><span class="sxs-lookup"><span data-stu-id="1f45c-121">If you are using Office 365 GCC High, replace the value for the ProxyFqdn parameter in this example ("exap.um.outlook.com") with the FQDN for GCC High: “exap.um.office365.us”.</span></span>

- <span data-ttu-id="1f45c-122">**Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando (por ejemplo, "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="1f45c-122">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="1f45c-123">Los valores que contienen espacios deben aparecer en comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="1f45c-123">Values that contain spaces must be in double quotes.</span></span>

- <span data-ttu-id="1f45c-124">\*\*Habilitada \*\* indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada.</span><span class="sxs-lookup"><span data-stu-id="1f45c-124">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="1f45c-125">Este parámetro debe estar configurado en True.</span><span class="sxs-lookup"><span data-stu-id="1f45c-125">This must be set to True.</span></span>

- <span data-ttu-id="1f45c-126">**EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="1f45c-126">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="1f45c-127">Este parámetro debe estar configurado en True.</span><span class="sxs-lookup"><span data-stu-id="1f45c-127">This must be set to True.</span></span>

- <span data-ttu-id="1f45c-128">**HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Office Communications Server o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="1f45c-128">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="1f45c-129">Este parámetro debe estar configurado en False.</span><span class="sxs-lookup"><span data-stu-id="1f45c-129">This must be set to False.</span></span>

- <span data-ttu-id="1f45c-130">**ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1f45c-130">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="1f45c-131">Para Exchange Online, el FQDN es exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1f45c-131">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

- <span data-ttu-id="1f45c-132">**IsLocal** indica si el servidor proxy utilizado por el proveedor de hospedaje está dentro de su Skype de topología de servidores de negocio.</span><span class="sxs-lookup"><span data-stu-id="1f45c-132">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="1f45c-133">Este parámetro debe estar configurado en False.</span><span class="sxs-lookup"><span data-stu-id="1f45c-133">This must be set to False.</span></span>

- <span data-ttu-id="1f45c-134">**VerificationLevel** Indica el nivel de comprobación permitido para los mensajes que se envían a y desde el proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="1f45c-134">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="1f45c-135">Especifique **UseSourceVerification**, que depende del nivel de comprobación incluido en mensajes enviados desde el proveedor de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1f45c-135">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="1f45c-136">Si no se especifica este nivel, el mensaje se rechazará como no se puede comprobar.</span><span class="sxs-lookup"><span data-stu-id="1f45c-136">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="1f45c-137">Comprobar la replicación del almacén de administración central actualizada</span><span class="sxs-lookup"><span data-stu-id="1f45c-137">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="1f45c-138">Los cambios realizados mediante el uso de los cmdlets en las secciones anteriores se aplican automáticamente al servidor perimetral y suele tardar menos de un minuto para replicar.</span><span class="sxs-lookup"><span data-stu-id="1f45c-138">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="1f45c-139">Puede validar el estado de la replicación y, a continuación, confirme que se han aplicado los cambios en el servidor perimetral mediante el uso de los cmdlets siguientes.</span><span class="sxs-lookup"><span data-stu-id="1f45c-139">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="1f45c-140">Para comprobar la replicación de las actualizaciones, en un servidor interno de su Skype para la implementación de Business Server, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1f45c-140">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>

```
Get-CsManagementStoreReplicationStatus
```
<span data-ttu-id="1f45c-141">Compruebe si el valor de actualizados se está mostrando en TRUE para todas las réplicas.</span><span class="sxs-lookup"><span data-stu-id="1f45c-141">Check if UpToDate value is showing TRUE for all Replicas.</span></span>

<span data-ttu-id="1f45c-142">Para confirmar que se han aplicado los cambios, en el servidor perimetral, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1f45c-142">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>

```
Get-CsHostingProvider -LocalStore
```
<span data-ttu-id="1f45c-143">Comprobar si la información que se muestra coincide con los cambios confirmados en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="1f45c-143">Double check if the information shown matches the changes committed in the previous steps.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f45c-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f45c-144">See also</span></span>

[<span data-ttu-id="1f45c-145">Especificación de Skype para Business Server en MU de Exchange hospedado del correo de voz de los usuarios</span><span class="sxs-lookup"><span data-stu-id="1f45c-145">Providing Skype for Business Server users voice mail on hosted Exchange UM</span></span>](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[<span data-ttu-id="1f45c-146">Hospedado integración mensajería unificada de Exchange en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="1f45c-146">Hosted Exchange Unified Messaging integration in Skype for Business Server</span></span>](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
