---
title: Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planeación para usuarios móviles en una implementación de E9-1-1 mediante proveedores de enlace troncal SIP, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 8682ba47e3543cc39b1fc793c587040a7821f8c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891353"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="cf39f-103">Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="cf39f-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="cf39f-104">Planeación para usuarios móviles en una implementación de E9-1-1 mediante proveedores de enlace troncal SIP, en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cf39f-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cf39f-p101">Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, la llamada se enrutará a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y, después, desviará la llamada al PSAP adecuado en función de la información proporcionada.</span><span class="sxs-lookup"><span data-stu-id="cf39f-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="cf39f-108">**¿Los usuarios se deben pedir para especificar una ubicación cuando no se proporciona automáticamente por el servicio de información de ubicación?**</span><span class="sxs-lookup"><span data-stu-id="cf39f-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="cf39f-109">Por ejemplo, si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, ¿se debe obligar al usuario a especificar una ubicación?</span><span class="sxs-lookup"><span data-stu-id="cf39f-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="cf39f-p102">Puede configurar el valor de **Ubicación obligatoria** en la directiva de ubicación para definir el comportamiento del cliente. Si este valor se establece en No, no se pedirá al usuario una ubicación. Si se define en Sí, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en Declinación de responsabilidades, se pedirá al usuario una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede continuar usando el cliente de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="cf39f-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="cf39f-115">Cuando un usuario escribe manualmente una ubicación, la ubicación está asignada a la dirección MAC de la puerta de enlace predeterminada de la red del cliente y se almacena en una tabla por usuario que se encuentra en el cliente.</span><span class="sxs-lookup"><span data-stu-id="cf39f-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="cf39f-116">Cuando el usuario vuelve a cualquier ubicación previamente almacenado, el Skype para clientes empresariales se establece automáticamente a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="cf39f-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cf39f-117">Puede modificar sólo en la ubicación actual del cliente, pero también puede eliminar cualquier ubicación almacenada en la tabla del usuario local.</span><span class="sxs-lookup"><span data-stu-id="cf39f-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

