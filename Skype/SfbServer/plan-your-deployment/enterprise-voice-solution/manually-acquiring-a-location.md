---
title: Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planificación de usuarios móviles en una implementación de E9-1-1 mediante proveedores de enlace troncal SIP, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: dd43d78b4c139b4fb30a0b4ba379d96150314332
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825430"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="db134-103">Definir la experiencia del usuario para adquirir manualmente una ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="db134-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="db134-104">Planificación de usuarios móviles en una implementación de E9-1-1 mediante proveedores de enlace troncal SIP, en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="db134-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="db134-p101">Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, se enrutará la llamada a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y después desviará la llamada al PSAP adecuado en función de la información proporcionada.</span><span class="sxs-lookup"><span data-stu-id="db134-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="db134-108">**¿Se debe pedir a los usuarios que especifiquen una ubicación cuando el servicio de información de ubicación no proporciona una automáticamente?**</span><span class="sxs-lookup"><span data-stu-id="db134-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="db134-109">Por ejemplo, ¿si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, se debe obligar al usuario a introducir una ubicación?</span><span class="sxs-lookup"><span data-stu-id="db134-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="db134-110">Puede configurar la opción **Ubicación requerida** en la directiva de ubicación para definir el comportamiento del cliente.</span><span class="sxs-lookup"><span data-stu-id="db134-110">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="db134-111">Si se establece este valor en No, no se pedirá al usuario una ubicación.</span><span class="sxs-lookup"><span data-stu-id="db134-111">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="db134-112">Si se establece este valor en Sí, se pedirá al usuario una ubicación, pero se puede descartar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="db134-112">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="db134-113">Establecer este valor en Aviso de declinación de responsabilidades significa que se pedirá al usuario una ubicación y se le mostrará un aviso de declinación de responsabilidades si intenta descartar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="db134-113">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="db134-114">En todos los casos, el usuario puede seguir usando el cliente como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="db134-114">In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="db134-115">Cuando un usuario escribe manualmente una ubicación, la ubicación se asigna a la dirección MAC de la puerta de enlace predeterminada de la red del cliente y se almacena en una tabla por usuario ubicada en el cliente.</span><span class="sxs-lookup"><span data-stu-id="db134-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="db134-116">Cuando el usuario vuelve a cualquier ubicación almacenada anteriormente, el cliente de Skype Empresarial se establece automáticamente en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="db134-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="db134-117">Solo puede modificar la ubicación actual del cliente, pero también puede eliminar cualquier ubicación almacenada en la tabla del usuario local.</span><span class="sxs-lookup"><span data-stu-id="db134-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

