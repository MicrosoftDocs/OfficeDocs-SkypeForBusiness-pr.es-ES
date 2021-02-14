---
title: Expansor de configuración de tronco
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:'
ms.openlocfilehash: 43cce7d0e61cf2e2c4f5fa6e4bcb845fd63fbc03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807540"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="7535c-103">Expansor de configuración de tronco</span><span class="sxs-lookup"><span data-stu-id="7535c-103">Trunk Settings Expander</span></span>

<span data-ttu-id="7535c-104">Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7535c-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="7535c-105">**Nombre del tronco** es una entrada obligatoria e identifica de manera exclusiva el tronco SIP en la implementación.</span><span class="sxs-lookup"><span data-stu-id="7535c-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="7535c-106">**Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC que se haya definido en la implementación.</span><span class="sxs-lookup"><span data-stu-id="7535c-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="7535c-p101">**Puerto de escucha de la puerta de enlace IP/RTC**: indica qué puerto TCP/IP usará la puerta de enlace para escuchar solicitudes. El valor puede variar según el proveedor de la puerta de enlace; sin embargo, el valor predeterminado es el puerto 5067.</span><span class="sxs-lookup"><span data-stu-id="7535c-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="7535c-p102">**Protocolo de transporte SIP**: el protocolo usado puede ser TCP o TLS. TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.</span><span class="sxs-lookup"><span data-stu-id="7535c-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="7535c-113">**Servidor de mediación asociado:** seleccione un servidor de mediación existente de la implementación para asociarlo con el tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="7535c-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="7535c-114">Solo el tronco raíz se puede asociar a un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7535c-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="7535c-115">**Puerto del servidor de mediación** asociado: un valor necesario, que se establece en el valor en el que el servidor de mediación está configurado para escuchar.</span><span class="sxs-lookup"><span data-stu-id="7535c-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Expansor de configuración de tronco](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="7535c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7535c-117">See also</span></span>

[<span data-ttu-id="7535c-118">Lista de comprobación de implementación de enlace troncal SIP</span><span class="sxs-lookup"><span data-stu-id="7535c-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="7535c-119">Componentes y topologías del tronco SIP</span><span class="sxs-lookup"><span data-stu-id="7535c-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
