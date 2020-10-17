---
title: 'Lync Server 2013: habilitar usuarios para E9-1-1'
description: 'Lync Server 2013: habilitar usuarios para E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba29406dc0d7a1140c83a1a9d271afca5d6b0c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546446"
---
# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Habilitación de usuarios para E9-1-1 en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

Durante el registro de clientes, Lync Server usa una directiva de ubicación para configurar las propiedades de E9-1-1 para los usuarios habilitados para Enterprise Voice. Esta directiva contiene la configuración que define cómo se implementa E9-1-1. Por ejemplo, la Directiva de ubicación contiene información como la cadena de marcado de emergencia y si un usuario debe o no especificar manualmente una ubicación si el servicio de información de ubicación no proporciona uno automáticamente. Para obtener una definición completa de una directiva de ubicación, consulte [Defining The location Policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server puede asignar una directiva de ubicación a los clientes en función de la subred o a los usuarios en función de una directiva global, por sitio o por usuario. Para ayudarle a decidir cómo habilitará los usuarios, debe responder en primer lugar las siguientes preguntas.

  - **¿Piensa habilitar todos los usuarios o limitar la compatibilidad a zonas geográficas específicas de la empresa?**  
    Puede asignar una ubicación a todos los usuarios de la empresa mediante una directiva de ubicación global. Sin embargo, al asignar una directiva de ubicación a un sitio de red de Lync Server y, a continuación, agregar subredes al sitio, puede limitar la compatibilidad con E9-1-1 a ubicaciones seleccionadas dentro de la empresa y especificar el comportamiento de enrutamiento E9-1-1 en cada sitio.

<!-- end list -->

  - **¿Piensa habilitar usuarios individuales a través de una directiva de usuario?**  
    Puede asignar directivas de ubicación directamente a usuarios específicos u objetos de contactos telefónicos de un área común si desea personalizar la compatibilidad con E9-1-1.

<!-- end list -->

  - **Cuando los clientes se desplazan fuera de la red o se encuentran en una subred no definida en la red, ¿deben los clientes seguir habilitados en E9-1-1?**  
    Si los usuarios tienen asignada una directiva de ubicación global, de sitio o por usuario, se les puede requerir especificar manualmente una ubicación en el cliente si el cliente no se encuentra en una subred definida o si el servicio de información de ubicación no ha encontrado ninguna ubicación. Para obtener más información, consulte [definir la experiencia de usuario para adquirir manualmente una ubicación en Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

