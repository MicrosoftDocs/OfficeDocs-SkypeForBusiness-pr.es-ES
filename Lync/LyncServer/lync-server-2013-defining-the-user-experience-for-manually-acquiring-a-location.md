---
title: Definir la experiencia de usuario para la adquisición manual de una ubicación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5913547ab7d5030ca40070de36b4deb1f6a89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="685ab-102">Definir la experiencia de usuario para la adquisición manual de una ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="685ab-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="685ab-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="685ab-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="685ab-p101">Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, la llamada se enrutará a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y, después, desviará la llamada al PSAP adecuado en función de la información proporcionada.</span><span class="sxs-lookup"><span data-stu-id="685ab-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="685ab-107">**¿Se debe pedir a los usuarios que especifiquen una ubicación cuando el servicio de información de ubicación no los proporcione automáticamente?**</span><span class="sxs-lookup"><span data-stu-id="685ab-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="685ab-108">Por ejemplo, si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, ¿se debe obligar al usuario a especificar una ubicación?</span><span class="sxs-lookup"><span data-stu-id="685ab-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="685ab-p102">Puede configurar el valor de **Ubicación obligatoria** en la directiva de ubicación para definir el comportamiento del cliente. Si este valor se establece en No, no se pedirá al usuario una ubicación. Si se define en Sí, se pedirá al usuario una ubicación, pero este puede anular la solicitud. Si se define en Declinación de responsabilidades, se pedirá al usuario una ubicación y se le mostrará una declinación de responsabilidades si intenta anular la solicitud. En todos los casos, el usuario puede continuar usando el cliente de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="685ab-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="685ab-114">Cuando un usuario especifica una ubicación manualmente, esta se asigna a la dirección MAC de la puerta de enlace predeterminada de la red del cliente y se almacena en una tabla de usuarios locales ubicada en el cliente.</span><span class="sxs-lookup"><span data-stu-id="685ab-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="685ab-115">Cuando el usuario vuelve a una ubicación previamente almacenada, el cliente de Lync se establece automáticamente en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="685ab-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="685ab-116">Solo puede modificar la ubicación actual del cliente, pero también puede eliminar cualquier ubicación que esté almacenada en la tabla de usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="685ab-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

