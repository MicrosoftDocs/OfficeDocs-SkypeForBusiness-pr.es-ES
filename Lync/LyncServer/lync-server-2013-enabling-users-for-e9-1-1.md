---
title: 'Lync Server 2013: habilitar usuarios para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Habilitar usuarios para E9-1-1 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

Durante el registro del cliente, Lync Server usa una directiva de ubicación para configurar las E9-1-1 para los usuarios habilitados para voz empresarial. Esta directiva contiene la configuración que define cómo se implementa E9-1-1. Por ejemplo, la Directiva de ubicación contiene información como, por ejemplo, la cadena de marcado de emergencia y si un usuario debe o no especificar manualmente una ubicación si el servicio de información de ubicación no proporciona una automáticamente. Para obtener una definición completa de una directiva de ubicación, consulte [definir la Directiva de ubicación de Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server puede asignar una directiva de ubicación a los clientes en función de la subred o a los usuarios en función de una directiva global, por sitio o por usuario. Para ayudarte a decidir cómo habilitarás los usuarios, necesitas responder primero las siguientes preguntas.

  - **¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**  
    Puede asignar una ubicación a todos los usuarios de su empresa mediante una directiva de ubicación global. Sin embargo, si asigna una directiva de ubicación a un sitio de red de Lync Server y luego agrega subredes al sitio, puede limitar la compatibilidad de E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento de E9-1-1 en cada sitio.

<!-- end list -->

  - **¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**  
    Si deseas personalizar la asistencia de E9-1-1, puedes asignar directivas de ubicación directamente a usuarios o a objetos de contactos telefónicos de un área común específicos.

<!-- end list -->

  - **Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿tienen los clientes que seguir habilitados en E9-1-1?**  
    Si se asigna a los usuarios una directiva de ubicación global, de sitio o por usuario, se les puede requerir introducir manualmente una ubicación en el cliente si el cliente no se encuentra en una subred definida o si el servicio de información de ubicación no ha encontrado ninguna ubicación. Para obtener más información, vea [definir la experiencia de usuario para adquirir una ubicación de forma manual en Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

