---
title: Definir la experiencia de usuario para adquirir manualmente una ubicación en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planificación para usuarios móviles en una implementación de E9-1-1 mediante proveedores de Troncalización SIP, en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 6a22883fb5f028288ab3fab0246d6c2b3b693987
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server-2015"></a><span data-ttu-id="d7b86-103">Definir la experiencia de usuario para adquirir manualmente una ubicación en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d7b86-103">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d7b86-104">Planificación para usuarios móviles en una implementación de E9-1-1 mediante proveedores de Troncalización SIP, en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7b86-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d7b86-p101">Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, la llamada se enrutará a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y, después, desviará la llamada al PSAP adecuado en función de la información proporcionada.</span><span class="sxs-lookup"><span data-stu-id="d7b86-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="d7b86-108">**¿Deben pedirá a los usuarios introducir una ubicación cuando no se proporciona automáticamente por el servicio de información de ubicación?**</span><span class="sxs-lookup"><span data-stu-id="d7b86-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="d7b86-109">Por ejemplo, si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, ¿se debe obligar al usuario a especificar una ubicación?</span><span class="sxs-lookup"><span data-stu-id="d7b86-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="d7b86-p102">Puede configurar el valor de **Ubicación obligatoria** en la directiva de ubicación para definir el comportamiento del cliente. Si este valor se establece en No, no se pedirá al usuario una ubicación. Si se define en Sí, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en Declinación de responsabilidades, se pedirá al usuario una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede continuar usando el cliente de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="d7b86-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="d7b86-115">Cuando un usuario introduce manualmente una ubicación, la ubicación está asignada a la dirección MAC de la puerta de enlace predeterminada de la red del cliente y se almacena en una tabla de usuario ubicada en el cliente.</span><span class="sxs-lookup"><span data-stu-id="d7b86-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="d7b86-116">Cuando el usuario vuelve a cualquier ubicación almacenado previamente, el Skype para Business client se establece automáticamente a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="d7b86-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d7b86-117">Puede modificar sólo en la ubicación actual de su cliente, pero también puede eliminar cualquier ubicación almacenada en la tabla del usuario local.</span><span class="sxs-lookup"><span data-stu-id="d7b86-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

