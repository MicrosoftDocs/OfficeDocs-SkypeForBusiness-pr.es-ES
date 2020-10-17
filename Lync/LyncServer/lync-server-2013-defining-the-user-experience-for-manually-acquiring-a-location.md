---
title: Definir la experiencia del usuario para adquirir manualmente una ubicación
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
ms.openlocfilehash: 0fa9c7242351417c4ea82ed7ce6183963bc9730e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504477"
---
# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Si un cliente está ubicado fuera de la red, o en una subred indefinida, puede introducir manualmente una ubicación. No obstante, durante una llamada de emergencia, se enrutará la llamada a un distribuidor del centro de respuesta de llamadas de emergencia (ECRC) E9-1-1 nacional y/o regional antes de enrutarla a un punto de respuesta de seguridad pública (PSAP). El distribuidor del ECRC preguntará la ubicación verbalmente a la persona que realice la llamada y después desviará la llamada al PSAP adecuado en función de la información proporcionada.

  - **¿Se debe pedir a los usuarios que escriban una ubicación cuando el servicio de información de ubicación no proporcione automáticamente uno?**  
    Por ejemplo, ¿si un cliente se encuentra en una subred no definida, en casa, en una cafetería o en cualquier otro lugar fuera de la red, se debe obligar al usuario a introducir una ubicación?
    
    Puede configurar el valor de **Ubicación requerida** en la Directiva de ubicación para definir el comportamiento del cliente. Si este valor se establece en no, no se pedirá al usuario una ubicación. Si se establece este valor en Yes, se pedirá al usuario una ubicación, pero puede descartar el mensaje. Si se establece este valor en la declinación de responsabilidades, se pedirá al usuario una ubicación y se le mostrará un aviso de declinación de responsabilidades si intentan omitir el mensaje. En todos los casos, el usuario puede seguir usando el cliente de la forma habitual.

Cuando un usuario introduce una ubicación, esta se asigna, en función de la dirección MAC de la puerta de enlace predeterminada de la red del cliente, y se almacena en una tabla de usuarios locales ubicada en el cliente. Cuando el cliente vuelve a cualquier ubicación almacenada previamente, se define automáticamente en dicha ubicación. Los usuarios también pueden seleccionar manualmente cualquier ubicación que esté almacenada en la tabla de usuarios locales y administrar las entradas existentes.

<div>


> [!NOTE]
> Solo puede modificar la ubicación actual del cliente, pero también puede eliminar cualquier ubicación que esté almacenada en la tabla de usuarios locales.



</div>

</div>

<span> </span>

</div>

</div>

</div>

