---
title: Modelo de usuario de conferencia de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1049ff2d11d76e78661636972c812cc6c9c731f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Modelo de usuario de conferencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Una parte fundamental del modelo de usuario de conferencia de Lync Server es el tamaño de la reunión. Después de recopilar datos de los diversos puntos de datos (como se describe en la sección anterior), determinamos lo siguiente:

  - La mayoría de las reuniones son en realidad reuniones de colaboración pequeñas con un promedio de cuatro a seis participantes

  - Aproximadamente el 80 por ciento de reuniones tienen menos de 20 participantes.

  - el 99,98% de las reuniones tienen menos de 100 participantes.

Además del tamaño de la reunión, el modelo de usuario de conferencia también tiene en cuenta varios factores, como:

  - **Reuniones simultáneas**   ¿cuántos usuarios se espera que estén en las reuniones al mismo tiempo?

  - **Mezcla de medios**   ¿qué tipos de medios están disponibles y se espera que usen los usuarios en las reuniones?

  - ****   ¿Los tipos de usuario son usuarios internos, usuarios remotos, usuarios federados o usuarios anónimos?

  - **Tiempo de impulso**   de la reunión ¿cuánto tiempo tardan los usuarios de una reunión en unirse a una reunión?

Para obtener más información sobre el modelo de usuario, consulte [modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

Para determinar el número de reuniones y usuarios que se van a usar para las pruebas, hicimos lo siguiente:

  - Se ha tomado el número total de usuarios de una organización (por ejemplo, 80.000 usuarios) y se ha multiplicado por la tasa de simultaneidad de la reunión (por ejemplo, el 5% de todos los usuarios) para determinar el número total de usuarios que se espera que estén en las reuniones al mismo tiempo (en este ejemplo , 4000 usuarios).

  - Dividimos el número total de usuarios entre el número de servidores de Lync Server 2013, front-end de la implementación (por ejemplo, 8 servidores) para determinar el número estimado de participantes de la reunión por servidor front-end (en este ejemplo, 500 usuarios por servidor front-end).

  - Divide el número de usuarios por servidor front-end por el tamaño medio de la reunión (por ejemplo, 4 usuarios) para determinar el número promedio estimado de reuniones por servidor front-end (en este ejemplo, 125 reuniones por servidor front-end).

  - Para obtener la carga por medio de cada servidor front-end, se estimó la combinación de medios. Por ejemplo, suponiendo que el 75% de las reuniones necesite algo más que el soporte de audio y el 50% de esas reuniones requieran un uso compartido de aplicaciones, un promedio de 47 reuniones y 188 usuarios se conectan simultáneamente a cada servidor front-end para el uso compartido de aplicaciones.

  - Se probaron varios tamaños de reunión (basados en nuestro modelo de usuario de hasta 250 usuarios en un grupo compartido) para garantizar la escalabilidad del servidor.

</div>

<span> </span>

</div>

</div>

</div>

