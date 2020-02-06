---
title: Expansor de configuración de tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:'
ms.openlocfilehash: aa3c8dd622e64bcd063e84d1f6e19278af9a6cff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819152"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="4c7d6-103">Expansor de configuración de tronco</span><span class="sxs-lookup"><span data-stu-id="4c7d6-103">Trunk Settings Expander</span></span>

<span data-ttu-id="4c7d6-104">Para editar o modificar la configuración de un tronco SIP, efectúe las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c7d6-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="4c7d6-105">**Nombre de tronco** es una entrada obligatoria e identifica de manera exclusiva el tronco SIP en la implementación.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="4c7d6-106">**Puerta de enlace RTC asociada**: seleccione una puerta de enlace RTC que se haya definido en la implementación.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="4c7d6-p101">**Puerto de escucha para la puerta de enlace IP/RTC**: indica qué puerto TCP/IP usará la puerta de enlace para escuchar solicitudes. El valor predeterminado es el puerto 5067, si bien este puede variar según el proveedor de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="4c7d6-p102">**Protocolo de transporte SIP**: el protocolo usado puede ser TCP o TLS. TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="4c7d6-113">**Servidor de mediación asociado**: Seleccione un servidor de mediación existente de la implementación para asociarlo con el tronco del SIP.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="4c7d6-114">Solo se puede asociar el tronco raíz con un servidor de mediación de Lync Server 2010 o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-114">Only the root trunk can be associated with a Lync Server 2010 or Lync Server 2013 Mediation Server.</span></span>

 <span data-ttu-id="4c7d6-115">**Puerto de servidor de mediación asociado**: un valor obligatorio, se establece en el valor en el que el servidor de mediación está configurado para escuchar.</span><span class="sxs-lookup"><span data-stu-id="4c7d6-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Expansor de configuración de tronco](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="4c7d6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c7d6-117">See also</span></span>

[<span data-ttu-id="4c7d6-118">Lista de comprobación de implementación de Troncalización SIP</span><span class="sxs-lookup"><span data-stu-id="4c7d6-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="4c7d6-119">Componentes y topologías para Troncalización SIP</span><span class="sxs-lookup"><span data-stu-id="4c7d6-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
